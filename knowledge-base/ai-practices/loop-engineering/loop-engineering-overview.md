---
requires_approve: true
last_updated: 2026-07-22
---

# Overview: Meaning and Trend

What loop engineering is, the anatomy of a loop per Osmani, where the trend is heading, and the main risks


## The meaning in two paragraphs

**Loop engineering** is the discipline of designing the cycle (loop) inside which an AI agent
operates, instead of writing every prompt by hand. Previously the "bottleneck" was prompt
wording (prompt engineering), then gathering the right context (context engineering). By early
2026 the models had become good enough, and the bottleneck shifted once again: now it matters
more to design the **loop** — what the agent does between tool calls, when it checks its own
work, and how it decides it is done.

The key shift is in the human's role. You are no longer the agent, nor the author of prompts;
you are the **architect of the system that runs both**. Boris Cherny (Claude Code, Anthropic)
puts it literally: "I don't prompt Claude — I have loops running that prompt Claude and decide
what to do; my job is to write loops." In practice this means hundreds of agent instances
working in parallel: they read GitHub Issues, scan feedback, triage Slack, and themselves
escalate what to do next.

## Definition (working)

> Loop engineering is the design of a control system that **prompts, verifies, and stops**
> AI agents in production. A loop starts from a trigger, pursues a **verifiable** goal, uses
> tools and memory, evaluates progress, and iterates until a stopping condition.

The simplest unit of useful agent work: **do → check the result → decide whether to continue
or stop**. All the craft lies in making the check *real*, and in defining *when to stop*.

## Anatomy of a loop — the "5 (+1) components" per Addy Osmani

1. **Automations** — scheduled tasks: they find and triage work on their own, without a human initiator.
2. **Worktrees** — isolated working directories: several agents work in parallel without getting
   in each other's way in the same files.
3. **Skills** — documented procedural knowledge: written down once, so the agent does not have
   to be retaught the same thing.
4. **Connectors** — integrations via the Model Context Protocol (MCP): they give the agent access
   to real tools and systems.
5. **Sub-agents** — a separate verifier agent: the "doer" does not grade its own work.
6. **Memory (+1)** — a markdown file, a Linear board, and the like: it lives outside a single
   conversation and stores what has been done and what comes next.

The academic formulation (arXiv 2607.00038) calls this a **loop specification** — a bounded,
reusable artifact of five parts: *trigger, goal, verification step, stopping rule, and memory*.

## Where this is heading (trend)

- **A new skill hierarchy.** Engineers who design loops and verification systems are overtaking
  those still polishing individual prompts. Prompt → context → **loop / harness engineering**.
- **Agents as long-lived executors, not chat assistants.** Coding agents are turning from
  interactive helpers into background systems "that ship while you sleep."
- **Verification is the product.** "In any loop, the bottleneck is the verifier, not the model."
  Generation has become cheap; the loop runs at the speed of its *verifying* half. The gold
  standard is deterministic verification (tests, types, compiler, linter) that the model cannot
  "talk its way past."
- **Loops win where verification is cheap.** Code with tests/builds is the ideal case;
  creative/fuzzy tasks with no objective grader are a poor one.
- **Cost shifting.** Token bills are coming back under the guise of an "agentic workflow budget."
  At API prices, loops get expensive fast — hence per-run budget limits, iteration caps, human
  checkpoints, and grader agents that "kill" the loop before it overspends.
- **An open debate about the term's longevity.** Skeptics (e.g., Max Kanat-Alexander) believe the
  "loop" is a temporary crutch until harnesses learn to do the same thing from a single prompt.
  That is, loop engineering may be absorbed into harness engineering.

## Main risks (one line each)

- **Self-approving loop / loopmaxxing** — when the same model both does the work and grades it:
  the score goes up, quality does not. "The loop adds a mirror instead of a critic."
- **Reward hacking** — the agent optimizes a proxy metric rather than the task; especially when
  the generator and the judge share context.
- **Runaway cost** — without a stopping rule, the loop burns tokens on a task it has already
  failed twice.

## References

- https://addyosmani.com/blog/loop-engineering/
- https://www.oreilly.com/radar/loop-engineering/
- https://thenewstack.io/loop-engineering/
- https://newsletter.pragmaticengineer.com/p/what-is-loop-engineering
- https://techcrunch.com/2026/06/22/the-ai-world-is-getting-loopy/
- https://arxiv.org/abs/2607.00038
- https://bdtechtalks.com/2026/06/22/ai-loop-engineering/
- https://agentautopsies.substack.com/p/loopmaxxing
