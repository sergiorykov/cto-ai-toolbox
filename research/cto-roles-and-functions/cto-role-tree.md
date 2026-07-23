---
requires_approve: true
last_updated: 2026-07-23
---

# CTO role tree

Who expects what from the CTO of an SMB/SME tech company (up to 250 people, up to 100 in IT), which instruments close each expectation, and how much of each instrument the AI team can already carry. Consumers: the CTO (self-assessment, re-contracting) **and the AI team** — agents triage requests against these branches.

**Levels:** [S] startup (≤30 in IT) · [G] scale-up (30–60) · [E] established SME (60–100). Scale frameworks (SAFe, LeSS, release trains) are out of scope at this size.

**AI leverage per instrument:** [AI] carryable by the AI team today, CTO reviews · [AI+H] AI produces the artifact, the human carries the trust/judgment part · [H] irreducibly human.

**Vision stance.** The canon this tree draws on (Fournier: "executive first, technologist second") resolves the contradiction *stakeholders demand an executive ↔ the CTO stays a hardcore IC* by delegation and giving up the craft. This repo resolves it differently: the artifact-shaped executive work is offloaded to AI, so the CTO keeps technical depth ([vision](../../principles/vision-ai-assisted-cto.md)). Where the tree cites the canon, read it through this stance — the AI-leverage marks show where the trade-off dissolves.

## How to enter this tree

- First find which audience's trust is the binding constraint right now (Goldratt) — work that branch this quarter, consciously de-prioritize the rest.
- Default entry set — the tenure-critical five: **1.2** (delivery trust), **1.8** (no surprises), **2.5** (no thrash), **4.2** (capacity honesty), **4.7** (executive behavior).
- Everything marked [AI] is backlog for the [AI team](../../principles/using-ai-agents.md) — set it up once, review on cadence.

## 1. Business — CEO, founders, board

- **1.1 A technology strategy the business can read — and see itself in.** [S] a 2-page memo the CEO co-signs; [E] a maintained doc reviewed yearly with the board.
  - Closes [AI+H]: written strategy as diagnosis → guiding policies → coherent actions ([Larson](https://lethain.com/eng-strategies/)); every policy mapped to a business goal; an internal tech radar to make bets explicit; a [Wardley map](https://learnwardleymapping.com/) behind build/buy narratives.
- **1.2 Predictable delivery: commitments made are commitments kept.** [S] variance forgiven; [E] the #1 trust currency.
  - Closes [AI+H]: quarterly roadmap agreed with product/GTM before the quarter ([planning](https://lethain.com/planning/)); [DORA four keys](https://dora.dev/) as the internal health dashboard (not a board metric); week-by-week decomposition over phase plans; fixed appetite over open estimates.
- **1.3 Engineering spend is legible and defensible.** Existential at [G], when payroll becomes the largest line item.
  - Closes [AI+H]: annual financial plan owned jointly with the CFO; functional allocation as % of capacity (product / KTLO / platform) — the single most persuasive "where the money goes" artifact; cloud cost in COGS against margin targets.
- **1.4 Technology risk managed before it becomes a board incident.** [S] "don't get breached"; [E] certifiable compliance.
  - Closes [AI+H]: [Latacora's SOC2 Starting Seven](https://www.latacora.com/blog/2020/03/12/the-soc-starting/) as the adoption order; tested backups + DR runbook with a yearly restore drill; a one-page risk register reviewed quarterly with the CEO.
- **1.5 The org survives losing any one person — including the CTO.** Sharpest at [S], where the CTO is the bus factor.
  - Closes [AI+H]: bus-factor map per critical system; runbooks and ADRs so knowledge lives in artifacts; succession planning for the CTO's own seat ([An Elegant Puzzle](https://lethain.com/elegant-puzzle/)); regrettable-attrition target that is low but nonzero.
- **1.6 Due-diligence readiness on demand.** Latent at [S], standing at any [E] contemplating raise/exit.
  - Closes [AI]: living DD artifacts (architecture diagram, license/SBOM inventory, IP assignment, tech-debt register, incident log); [AKF's TDD checklist](https://akfpartners.com/growth-blog/technical-due-diligence-checklists) as an annual self-audit; a pre-built data room.
- **1.7 Build-vs-buy discipline — engineers build only what differentiates.**
  - Closes [AI+H]: Wardley evolution classification; a 1-page decision memo per call (TCO incl. maintenance headcount, exit cost); annual revisit — yesterday's build is today's SaaS line item ([Larson](https://lethain.com/build-vs-buy/)).
- **1.8 Tech translated into business language — and no surprises.** The unmet expectation that most often ends CTO tenure.
  - Closes [AI+H]: audience-split reporting ([measuring the org](https://lethain.com/measuring-engineering-organizations/)); a monthly one-page engineering update (shipped impact, risks, asks); bad news early, with options; private alignment with the CEO before contentious debates.
- **1.9 Yearly goals that ladder into company goals.**
  - Closes [AI+H]: three-layer cadence — annual financial plan → rolling functional allocation → quarterly roadmap ([planning](https://lethain.com/planning/)); 3–5 engineering-owned yearly goals traceable to company objectives; a shared definition of success agreed with the CEO in the [first 90 days](https://lethain.com/first-ninety-days-cto-vpe/).

## 2. Engineering leadership — EMs, delivery managers, architects, leads

- **2.1 Clear org structure with explicit ownership.**
  - Closes [AI+H]: one team map in [Team Topologies](https://teamtopologies.com/key-concepts) vocabulary; a [Team API](https://github.com/TeamTopologies/Team-API-template) per team; sizing rules — 6–8 engineers per manager, grow-to-8-then-bud ([Larson](https://lethain.com/sizing-engineering-teams/)); [E] cognitive-load checks before adding scope.
- **2.2 A written technical strategy that survives contact with deadlines.** Leads need guardrails, not per-project rulings.
  - Closes [AI+H]: strategy doc authored with a 3–5 person working group; [ADRs](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions) in version control; an internal [tech radar](https://www.thoughtworks.com/radar/byor) bounding tool choices.
- **2.3 Explicit decision rights and a working escalation path.** Delivery managers feel its absence first.
  - Closes [AI+H]: a [DRI](https://handbook.gitlab.com/handbook/people-group/directly-responsible-individuals/) named per significant decision; a standing RFC/spec review forum; escalations treated as policy inputs — [work the policy, not the exceptions](https://lethain.com/work-policy-not-exceptions/). [S] CTO is default DRI; [E] DRI pushed down or the CTO becomes the bottleneck.
- **2.4 A career ladder that covers the leads themselves.**
  - Closes [AI+H]: parallel IC/management tracks (borrow [Dropbox's framework](https://dropbox.github.io/dbx-career-framework/), benchmark via [progression.fyi](https://progression.fyi/)); the [engineer/manager pendulum](https://charity.wtf/2017/05/11/the-engineer-manager-pendulum/) legitimized; [E] calibration sessions.
- **2.5 Prioritization sanity — stable plans, no thrash.**
  - Closes [H]: fixed functional allocation percentages changed only through explicit re-planning; the CTO absorbs exec-level churn instead of relaying it; "changing your allocation feels like progress, but each change is disruptive" ([Larson](https://lethain.com/planning/)).
- **2.6 Air cover, sponsorship, defended resourcing.**
  - Closes [H]: [sponsorship over mentorship](https://larahogan.me/blog/what-sponsorship-looks-like/) — visible projects, names said in exec rooms; headcount defended at exec level; disagree privately, back publicly.
- **2.7 Leadership rituals that share real context, not status theatre.**
  - Closes [AI+H]: [Larson's meeting stack](https://lethain.com/eng-org-meetings/) scaled to size — weekly leadership working session, spec + incident reviews anchored on documents, monthly forums and eng Q&A; [S] the weekly session + Q&A suffices; a peer ["Manager Voltron"](https://larahogan.me/blog/manager-voltron/) encouraged.
- **2.8 A CTO who represents engineering at the executive table and translates both ways.**
  - Closes [H]: a seat where strategy is set, kept deliberately ([Fournier](https://www.elidedbranches.com/2015/02/cto.html) — read через the vision stance above); the why behind commitments brought back in writing; the stage transition ([S] hands-on → [G] org-builder → [E] strategist) noticed and re-contracted explicitly — with AI leverage bending the curve toward staying technical.

## 3. Line engineers — developers, QA, DevOps

- **3.1 Clear written technical direction — "I know where we're going and why".** [S] a one-pager; [E] undocumented strategy = teams on conflicting assumptions.
  - Closes [AI+H]: the engineering strategy (1.1/2.2) published internally; an ADR log so decisions are auditable, not relitigated; a "how we choose tech" policy with a boring-tech default.
- **3.2 A voice in decisions before they're final.** Critical at [G], when the CTO leaves the room.
  - Closes [AI+H]: a lightweight [RFC process](https://blog.pragmaticengineer.com/scaling-engineering-teams-via-writing-things-down-rfcs/) — short doc, selective approvers, open comment window; CTO comments in the open, no private vetoes.
- **3.3 Working developer experience — fast feedback loops, low cognitive load.**
  - Closes [AI+H]: quarterly [DevEx survey](https://getdx.com/report/devex-productivity/) (feedback loops, cognitive load, flow) + system metrics; [DORA capabilities](https://dora.dev/capabilities/) as the improvement backlog; a ring-fenced % of capacity for DevEx work. [S] the CTO fixes tooling personally; [G] first dedicated platform capacity.
- **3.4 Protected focus time — priorities don't flip mid-sprint.**
  - Closes [H]: [maker's-schedule](https://www.paulgraham.com/makersschedule.html) norms (no-meeting blocks, office hours over drive-by pings); a "swap, don't add" rule mid-iteration; the why always relayed when priorities genuinely change.
- **3.5 Fair, transparent grades and market-sane compensation.** QA especially sensitive to dev-shaped ladders.
  - Closes [AI+H]: adapt an open framework (75 ladders at [progression.fyi](https://progression.fyi/); [Dropbox's](https://dropbox.github.io/dbx-career-framework/) covers QA/SRE tracks); benchmark via [levels.fyi](https://www.levels.fyi/) — US-skewed, sanity-check against the local market (ru sources in `ru/`); "not a promotion checklist" stated explicitly; cross-team calibration.
- **3.6 A real senior IC growth path — staff-plus without becoming a manager.**
  - Closes [AI+H]: [StaffEng archetypes](https://staffeng.com/guides/) to define what Staff means here; promotion packets + sponsorship; designated staff projects. [S] the title may not exist, but staff-scope work does.
- **3.7 Technically credible leadership — "the CTO still understands our work".**
  - Closes [H]: CTO on the RFC/design-review rotation; spikes off the critical path; [pendulum](https://charity.wtf/2017/05/11/the-engineer-manager-pendulum/) — and per the vision stance, AI leverage is what lets the CTO stay closer to the code than the canon assumes at every level.
- **3.8 Psychological safety around incidents — "an outage won't be pinned on me".** One scapegoating episode poisons a ≤100-person org.
  - Closes [H]: [blameless postmortems](https://sre.google/sre-book/postmortem-culture/) focused on systemic causes; action items tracked to done; the CTO publicly praises strong postmortems and never asks "who"; near-miss reporting rewarded.

## 4. C-level peers — CPO, CFO, COO, CMO, HR

- **4.1 CPO: engineers in discovery, not a ticket queue behind a wall.** [S] the CTO sits in the product trio personally; [G]/[E] every team has a tech lead with real discovery time.
  - Closes [H]: product trio (PM + design + tech lead) as the discovery unit ([SVPG](https://www.svpg.com/what-makes-a-great-cto/), [Product Talk](https://www.producttalk.org/)); engineers in customer interviews; feasibility prototypes.
- **4.2 CPO/CMO/CEO: dates they can build launches on — capacity honesty.**
  - Closes [AI+H]: [high-integrity commitments](https://www.svpg.com/managing-commitments-in-an-agile-team/) — only the delivering team commits, after enough discovery; commitments rare and tracked; a published capacity split renegotiated openly.
- **4.3 CFO: forecastable spend, capitalization without a fight.** [S] one page of numbers; [E] a full planning cycle.
  - Closes [AI+H]: the annual triad — P&L by function, budget, headcount plan ([Larson](https://lethain.com/planning/)); [capitalization criteria](https://lethain.com/capitalize-engineering-costs/) agreed with finance early; monthly variance review.
- **4.4 COO/CFO: a disciplined vendor portfolio, not SaaS sprawl.**
  - Closes [AI]: build-vs-buy memo comparing the vendor against what you'd realistically build today; a vendor register (owner, cost, renewal); quarterly scorecards; [renegotiate before renewal](https://lethain.com/renegotiate-first-vendor-contract/).
- **4.5 COO/CMO/CS: predictable incident communication in business language.** [S] the CTO narrates personally; [E] a system does it.
  - Closes [AI+H]: severity levels with comms SLAs; a comms lead separate from the fixer; a stakeholder channel/status page — peers never learn from customers first ([incident.io](https://incident.io/blog/incident-communication-best-practices)).
- **4.6 HR: an executable hiring plan, legible grades, early retention signals.**
  - Closes [AI+H]: joint hiring plan checked against actual recruiting capacity; public ladder mapped to comp bands; structured loops with scorecards; attrition review with named flight risks — not an annual surprise.
- **4.7 All peers: executive behavior — first team, one voice, shared language.** Hardest for founder-CTOs at [S].
  - Closes [H]: [peers as the first team](https://lethain.com/first-team/) (standing 1:1s, non-zero-sum resourcing); [disagree and commit](https://www.aboutamazon.com/about-us/leadership-principles) — conflict inside the room, one voice outside; [extract the kernel](https://lethain.com/extract-the-kernel/) from "specifically wrong" peer ideas; everything translated into risk, cost, time, revenue — never velocity charts.

## 5. The company's future — what the CTO originates unprompted

No stakeholder explicitly asks for these; their absence only becomes visible in retrospect. This branch is where the [vision](../../principles/vision-ai-assisted-cto.md) lives — and the acceptance test is the [research backlog](../../principles/research-backlog.md): every heavy research there must land in one of these expectations.

- **5.1 Technology foresight — fast immersion into technologies and trends to plan the future.**
  - Closes [AI+H]: standing radar duty (tech-scout agent over the radar/technology sources); quarterly radar delta reviewed against IT strategy; dated, sourced immersion briefs instead of hunches.
- **5.2 AI-era opportunity and risk scouting for the company and its market.**
  - Closes [AI+H]: heavy researches on demand (e.g. "how Unity AI changes game development — risks and opportunities"); risk-officer + biz-strategist agents producing priced scenarios; an explicit AI adoption stance revisited on cadence.
- **5.3 Platform and infrastructure stewardship — the estate nobody asks about until it fails.**
  - Closes [AI+H]: deliberate platform decisions at SMB scale (e.g. deployment topology without k8s); paved-road tooling; infra bus-factor tracked like any other risk (1.5).
- **5.4 Personal technical craft — the hardcore-IC core of the role.**
  - Closes [H]: staying on the technical critical path with AI leverage ([loop engineering](../../knowledge-base/ai-practices/loop-engineering/README.md)); building the personal AI team itself; prototype spikes; the craft is what makes 3.7 credible and 5.1–5.3 possible.

## 6. Function map — what the role consists of

The cross-source synthesis of CTO course curricula, books and company playbooks (per-source taxonomies: [cto-role-sources.md](cto-role-sources.md)). Each function names the expectations it serves.

1. **Technology strategy & architecture** — strategy, radar, build-vs-buy, ADRs, tech debt (1.1, 1.7, 2.2, 3.1)
2. **Org design** — structure, topologies, sizing, ownership, succession (1.5, 2.1)
3. **People & talent** — hiring, ladders, compensation, staff-plus, growing leaders (2.4, 2.6, 3.5, 3.6, 4.6)
4. **Delivery & engineering process** — planning cadence, delivery metrics, DevEx, RFC/decision process, quality (1.2, 1.9, 2.3, 2.5, 3.2, 3.3, 3.4)
5. **Operations, reliability & security** — incidents, postmortems, security baseline, continuity, platform stewardship (1.4, 3.8, 4.5, 5.3)
6. **Business partnership & executive operations** — product partnership, budget/capitalization, vendors, DD readiness, exec communication (1.3, 1.6, 1.8, 4.1–4.6)
7. **Culture & communication** — values, psychological safety, handbook-first knowledge (2.7, 3.8, 4.7)
8. **Data, AI & technology foresight** — data for decisions, AI stance, trend scouting (5.1, 5.2)
9. **Self-management & craft** — energy, staying technical, the pendulum, personal development (2.8, 3.7, 5.4)

## References

Inline above; the full annotated source base: [cto-role-sources.md](cto-role-sources.md), Russian sources in `ru/`. Challenge memo that shaped sections "Vision stance", "How to enter" and branch 5: git history of this research.
