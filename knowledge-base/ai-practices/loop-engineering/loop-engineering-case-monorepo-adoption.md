---
requires_approve: true
last_updated: 2026-07-22
---

# How-to: a loop engineering adoption plan for a fullstack monorepo


A practical plan for moving to loops for a specific setup:

> **Context.** A single monorepo: Node.js frontend + backend + PostgreSQL. Everything comes up in
> `docker-compose` and is deployed to environments (dev/stage/…). We need the agent to be able to
> bring up the containers itself, spin up a headless browser (Playwright) for the frontend, run
> the tests, and iterate until green.

> **Accuracy caveats.** (1) The syntax of Claude Code commands (`/goal`, `/loop`, `/schedule`)
> is changing fast in 2026 — before leaving anything unattended, check against
> `code.claude.com/docs`. (2) What follows is an assembly of practices from field guides
> (Developers Digest, Gaffer, Osmani), not from a single canonical source. Verify package
> versions and flags.

---

## 0. What the goal of the transition sounds like (in one sentence)

> Stop being the person who types the next prompt. Build a **harness** in the repository in which
> the agent, given a feature spec, writes the code itself, brings up the environment in Docker,
> runs unit + e2e (Playwright headless), fixes based on feedback from an **independent verifier**,
> and stops on a green build or on an iteration/budget limit — with a PR as the output.

The key idea of the whole discipline: **writing the loop is easy; the hard part is the verifier
inside it.** Without independent verification, the loop doesn't save labor — it produces the wrong
result faster.

---

## 1. Three "verbs": goal / loop / routine

The most common mistake is lumping three different modes into one word. Separate them right away:

| Verb | What it means | Claude Code | Where it fits in your process |
|--------|-----------|-------------|----------------------|
| **Goal** | work until the goal is reached, then stop | `/goal <condition>` | "get the feature to green tests and a clean lint" |
| **Loop** | repeat while I'm nearby and watching | `/loop [interval] <task>` | "keep spinning build-test-fix while I triage the next task" |
| **Routine** | work while I'm away | `/schedule <cron/webhook>` | "at night, run through open PRs, fix broken CI" |

What matters about `/goal` is not that it "spins," but **who decides what counts as done**: after
each turn Claude Code sends the condition + the transcript to a separate small judge model (Haiku
by default), which returns yes/no with a reason. That is the "worker doesn't grade its own work."

Rule: start with `/loop` (by hand, under your eyes) → once you trust the verifier, move to `/goal`
(stops on its own by the condition) → once you trust the budget, move durable things to `/schedule`.

---

## 2. What to set up in the repository (the harness foundation)

Loop engineering per Osmani = 6 bricks: **automations, worktrees, skills, connectors,
sub-agents, memory**. Below is how each one maps onto your monorepo.

### 2.1 `CLAUDE.md` (repo root) — the agent's "constitution"
What to put in it:
- how to bring up the stack: `docker compose -f docker-compose.yml -f docker-compose.test.yml up -d`;
- how to apply migrations and seeds; how to wait for Postgres readiness (healthcheck);
- check commands: `npm run lint`, `npm run typecheck`, `npm test`, `npm run test:e2e`;
- boundaries: what must not be touched (prod-environment migrations, secrets, `main`), what may be;
- the service port map and the port-isolation rule for parallel worktrees.

### 2.2 Skills (`.claude/skills/…`) — procedural knowledge written down once
Separate skill files for repeatable procedures, so the agent doesn't "guess":
- `spin-up-stack` — bring up the `test` compose profile, wait for the healthcheck, apply migrations;
- `run-e2e` — install the browsers (`npx playwright install --with-deps chromium`), bring up the
  frontend, run `npx playwright test`, collect the report (junit/html);
- `db-reset` — recreate the ephemeral test DB for the current worktree;
- `open-pr` — commit to a `claude/` branch, PR with a description and a link to the test report.

### 2.3 Sub-agents — the maker/verifier pattern (the heart of the loop)
Two different agents (preferably **different models** — then "two sets of weights" must agree):
- **maker** — writes code against the spec;
- **verifier** — with fresh context, checks the diff against the spec + tests, catches what the
  maker "forgave" itself. Doesn't let the task close until it agrees.

The anti-pattern that kills this: the **self-approving loop** — when one model both does and
grades; it will "delete the failing test and call the task done."

### 2.4 Connectors (MCP) — the agent's hands and eyes
The minimal set for your stack:
- **Playwright MCP** — a live browser exposed as tools (`browser_navigate`, `browser_click`,
  `browser_snapshot` — reads the accessibility tree, not pixels):
  `claude mcp add playwright npx @playwright/mcp@latest` (better to pin the version for
  reproducibility). Docker/CI details — section 4.
- **GitHub MCP/CLI** — Issues, PRs, CI statuses as part of the chain.
- **Postgres MCP** (opt.) — so the verifier can check the DB state after a scenario.

> Distinguish: **Playwright CLI** (`npx playwright test`) — your regression suite in CI;
> **Playwright MCP** — the agent drives the browser live (self-QA, bug reproduction, spec
> generation). You need both.

### 2.5 Worktrees — parallelism without collisions
Each agent gets its own git branch and its own directory (`git worktree`), so parallel fixes
don't clobber each other. Critical for your case: **each worktree gets its own compose project and
its own ports/DB** (see 4.3), otherwise the agents will fight over 5432/the web port.

### 2.6 Hooks — an automatic verifier at the commit point
A `post-commit` git hook that runs review/tests and feeds the findings back into the fix loop
while the context is "warm." Plus stop-hooks, so the loop doesn't finish before green.

### 2.7 Memory — state beyond a single conversation
A `markdown` file (or a board in Linear/Asana): what's done, what's next, which tests were flaky.
Without this, every CI run looks "new," and the agent re-investigates an already triaged flake.

### 2.8 Budget/caps — before you walk away
Every `/goal` gets a clause "or stop after N turns"; every `/schedule` gets a daily spend ceiling.
"A loop without a ceiling will happily spend all your tokens."

---

## 3. The verification ladder for your stack (from cheap to expensive)

The verifier must be **cheaper and more reliable** than the action being checked. Order of
application:

1. **Deterministic, free** — `tsc`/typecheck, `eslint`, compilation, `docker build`.
2. **Unit tests** — `npm test` (Jest/Vitest), a fast signal for the backend and frontend utilities.
3. **Integration** — the API against a Postgres brought up in compose (a real DB, not a mock).
4. **E2E** — Playwright headless against the running frontend: checks user scenarios.
5. **Model-as-judge / human gate** — only for what cannot be checked deterministically
   (UX wording, architectural decisions); more expensive and more fragile, put it last.

Rule: the lower on the ladder you catch the error, the cheaper the loop. E2E is not the first line
of defense but the last automatic one.

---

## 4. Docker + Playwright + Postgres: specifics

### 4.1 A separate compose profile for tests
Create a `docker-compose.test.yml` that brings up: `db` (Postgres with a `healthcheck`),
`backend`, `frontend`, and an `e2e` job container on the official Playwright image
(`mcr.microsoft.com/playwright` — browsers and system deps are already inside, so you don't hit
`error while loading shared libraries`).

Example skeleton (adapt to your services):

```yaml
# docker-compose.test.yml
services:
  db:
    image: postgres:16
    environment:
      POSTGRES_PASSWORD: test
      POSTGRES_DB: app_test
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U postgres -d app_test"]
      interval: 3s
      retries: 20
  backend:
    build: ./backend
    depends_on:
      db: { condition: service_healthy }
    environment:
      DATABASE_URL: postgres://postgres:test@db:5432/app_test
  frontend:
    build: ./frontend
    depends_on: [backend]
  e2e:
    image: mcr.microsoft.com/playwright:v1.latest  # pin the exact version!
    depends_on: [frontend]
    working_dir: /work
    volumes: [".:/work"]
    command: ["npx", "playwright", "test", "--reporter=line,junit,html"]
```

### 4.2 Browsers and headless
- In a container, headless is the default — do **not** force `--headed` (otherwise it "hangs,"
  waiting for a display).
- If you run Playwright on something other than the official image, install browsers with system
  deps: `npx playwright install --with-deps chromium` (without `--with-deps` you get cryptic
  library errors).
- Diagnostics for common CI failures:

| Symptom | Cause | Fix |
|---|---|---|
| `Executable doesn't exist` | browser binaries not installed | `npx playwright install --with-deps` |
| `error while loading shared libraries` | missing system deps | `--with-deps` or the `mcr.microsoft.com/playwright` image |
| Server fails to start | Node < 18 | a Node 18+ step before MCP |
| Hangs forever | waiting for a display | confirm headless, don't force `--headed` |

### 4.3 DB and port isolation per worktree (otherwise parallel loops fight)
- A unique `-p <project>` per worktree: `docker compose -p wt_${BRANCH} …` — its own networks and
  containers.
- Don't hardcode external ports; map them dynamically (or run e2e inside the compose network,
  addressing `frontend:PORT`, and then nothing needs to be exposed at all).
- A dedicated test DB per run (`app_test_${BRANCH}`) + the `db-reset` skill between runs.
- `storage state` for authenticated scenarios: once
  `npx playwright codegen --save-storage=auth.json …`, and from then on the agent starts already
  logged in.

### 4.4 Test memory (so the loop doesn't rediscover flakes)
By default, everything a run found dies with the job. Store reports between runs (junit/html as
CI artifacts, or a tool like Gaffer on top). Then, before "fixing," the verifier can ask: did this
test fail on `main` a week ago? is it flaky? — and not fix what doesn't need fixing.

---

## 5. End-to-end example: a feature development loop

Take the feature "add a status filter to the order list" (frontend + API + migration).

**Step 0. Turn the request into a strict goal (goal-meta-skill).** The highest-leverage trick is
to make the agent first rewrite the task into a precise goal: the end state, how it will verify,
what not to touch, when to stop.

```
/goal rewrite my request into a precise specification: end state, acceptance criteria,
how you will verify it (which tests), what must not be touched (stage/prod migrations, main),
and the stop condition. Confirm the specification, then execute.
```

**Step 1. Build-test-fix as a `/loop` (under your eyes).**

```
/loop bring up the test stack (docker compose -f docker-compose.test.yml up -d, wait for
the DB healthcheck, apply the migrations). Implement the next item of the plan: migration +
API endpoint + UI filter. After each change run typecheck, lint, unit. Feed every error back
as the next instruction and fix it. Stop when the build is green and the reviewer has nothing
to add.
```

**Step 2. E2E via Playwright (the last automatic line of defense).**

```
bring up the frontend in compose, and via Playwright MCP walk through the scenario: open the
order list, apply the "in processing" filter, verify that only orders in that status are shown
and the counter matches. If the scenario works — generate a spec in
tests/e2e/orders-filter.spec.ts and commit it.
```

**Step 3. An independent verifier subagent.**

```
/goal hand the diff to a separate verifier agent (a different model): check it against the
specification and the tests (unit + integration + e2e). Only a PASS from both sides counts as
done. Up to 5 rounds. Whatever the verifier rejects twice — escalate to me. Stop on the first
clean run or on the limit.
```

**Step 4. A streak, not a single green (for flake-sensitive places).**

```
/goal run e2e against realistic scenarios. Any failure resets the counter. Done only after
3 consecutive clean runs. One green is luck; a streak is reliability.
```

**Step 5. PR.** The `open-pr` skill: commit to `claude/orders-filter`, a PR with a description and
the junit/html report attached. A nightly `/schedule` routine can then fix broken CI on this PR by
itself.

---

## 6. Adoption plan by phases

**Phase 1 (2–3 days) — foundation, no autonomy.**
- Write `CLAUDE.md` (stack commands, boundaries, port map).
- Create `docker-compose.test.yml` + DB healthcheck + seeds.
- Hook up Playwright MCP, run one self-QA scenario by hand.
- Readiness criterion: on command, the agent brings up the stack and runs unit+e2e locally.

**Phase 2 (week 1) — the first loop, under your eyes.**
- Skills: `spin-up-stack`, `run-e2e`, `db-reset`, `open-pr`.
- Run build-test-fix as a `/loop` on one real, non-critical feature.
- Add a verifier subagent (a different model). Check that it actually rejects something.
- Criterion: one feature driven to green by the loop and a PR with minimal edits from you.

**Phase 3 (weeks 2–3) — isolation and parallelism.**
- Worktrees + compose project/port/DB isolation per branch.
- Test report storage (memory), stop/`post-commit` hooks.
- Move trusted loops from `/loop` to `/goal` with a turn cap.
- Criterion: 2–3 agents in parallel on different features with no DB/port collisions.

**Phase 4 (week 4+) — routines and budget.**
- `/schedule`: nightly run over open PRs, auto-fixing broken CI, rebasing stale ones.
- Daily spend ceilings; a FinOps review of the token bill.
- Adversarial review (one model reviews the other's PR) at the merge gate.
- Criterion: in the morning — finished/green PRs, the contentious left for you; the bill under
  the ceiling.

---

## 7. What matters to configure and where (summary)

| Component | Where | Why |
|---|---|---|
| `CLAUDE.md` | repo root | stack commands, boundaries, port map |
| Skills | `.claude/skills/` | `spin-up-stack`, `run-e2e`, `db-reset`, `open-pr` |
| Sub-agents | agent config | maker/verifier on different models |
| Playwright MCP | `claude mcp add playwright …` | a live browser for self-QA and spec generation |
| `docker-compose.test.yml` | repo root | an isolated test stack + DB healthcheck |
| Playwright CI job | `mcr.microsoft.com/playwright` image | headless e2e without fussing with system deps |
| Worktrees | `git worktree` + `compose -p` | parallel agents without collisions |
| Hooks | `.git/hooks` / `.claude/` | a verifier at the commit point, stop-hooks |
| Memory + test reports | md file / junit-html artifacts | don't rediscover flakes, remember progress |
| Budget caps | in the `/goal` condition, `/schedule` limit | protection against a runaway bill |

---

## 8. Anti-patterns (keep in mind)

- **Self-approving loop** — the maker is its own judge. Cured by an independent verifier (a
  different model).
- **An open loop without a verifier** — error compounding, "hallucinated progress," a doom loop
  (the agent repeats the same broken approach with cosmetic changes). The verifier closes the loop.
- **Runaway cost** — no cap → it burns tokens on a task it has already failed twice. Always a turn
  cap and a daily ceiling.
- **A shared DB/ports across parallel loops** — races and "flickering" failures. Isolate per
  worktree.
- **`--headed` in a container** — hangs waiting for a display. Headless only in CI.
- **Uploading reports only on success (`if: success`)** — you throw away exactly the data
  (failures) the next run needs. Upload with `if: always()`.

---

## 9. References

- Developers Digest — "The Definitive Guide to Loop Engineering in Claude Code and Codex"
  (the goal/loop/routine verbs, patterns, cost/verifier): https://www.developersdigest.tech/blog/loop-engineering-definitive-guide
- Gaffer — "Playwright MCP with Claude Code: Setup & CI Guide" (Docker/headless/CI, test memory):
  https://gaffer.sh/blog/playwright-mcp-claude-code-setup/
- Addy Osmani — "Loop Engineering" (the 6 bricks): https://addyosmani.com/blog/loop-engineering/
- Pawel Huryn — "Loop Engineering for PMs" (routine/workflow/loop + the "done" stop condition):
  https://www.productcompass.pm/p/loop-engineering-for-pms
- Playwright MCP: https://www.builder.io/blog/playwright-mcp-server-claude-code
- Forward Future Loop Library (ready-made, proofread loops): https://signals.forwardfuture.ai/loop-library/
- Official command docs (verify the syntax!): https://code.claude.com/docs
