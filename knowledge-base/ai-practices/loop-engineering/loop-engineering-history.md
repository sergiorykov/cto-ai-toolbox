# Background: Names, Articles, Repositories

Chronology of how the term "loop engineering" emerged, key people, primary sources, and repositories


## How the term emerged (chronology)

The term crystallized over a few days in early June 2026 — three voices from different corners
of the AI coding world articulated the same idea almost simultaneously.

- **~June 6–7, 2026** — **Peter Steinberger** (creator of OpenClaw, the most-starred new
  repository in GitHub history at the time) publishes a post: "You should no longer prompt
  coding agents — you should design loops that prompt your agents." The post gathered ~5 million
  views in less than a day.
- **June 7, 2026** — the next day, **Addy Osmani** (engineering lead of Google Chrome) gives
  the practice a name and structure in the essay **"Loop Engineering"** on addyosmani.com. Later
  (June 22) republished in O'Reilly Radar.
- **Around the same time** — **Boris Cherny** (head of Claude Code at Anthropic) formulates the
  same thing from the inside: "I no longer prompt Claude. I have loops running that prompt Claude
  and decide what to do. My job is to write loops." The thesis was voiced in his talk (including
  at the Meta @Scale conference).

Bottom line: **Steinberger** supplied the provocation, **Osmani** supplied the name and anatomy,
**Cherny** supplied the confirmation "from inside" the lab. The term was then picked up by
O'Reilly, TechCrunch, The New Stack, Pragmatic Engineer, and dozens of blogs.

## Key people

| Name | Role | Contribution to the term |
|------|------|--------------------------|
| **Peter Steinberger** | Creator of OpenClaw, ex-PSPDFKit/Nutrient | The "stop prompting, design loops" provocation; the viral trigger post |
| **Addy Osmani** | Eng lead, Google Chrome; O'Reilly author | Named and structured the practice; the "5 components" of a loop |
| **Boris Cherny** | Head of Claude Code, Anthropic | "I write loops, not prompts"; validation from industry |
| **Cat Wu** | Claude Code product, Anthropic | Joint explanations of agentic loops (The Neuron) |
| **Gergely Orosz** | Pragmatic Engineer | Breakdown / critical review of the term for a broad engineering audience |
| **Max Kanat-Alexander** | Distinguished engineer | Skeptic: the "loop" may turn out to be a temporary hack until the harness improves |

## Primary sources (originals)

- Addy Osmani — "Loop Engineering" (personal blog): https://addyosmani.com/blog/loop-engineering/
- Addy Osmani in O'Reilly Radar: https://www.oreilly.com/radar/loop-engineering/
- Addy Osmani (Substack "Elevate"): https://addyo.substack.com/p/loop-engineering
- The New Stack — Boris Cherny's statement: https://thenewstack.io/loop-engineering/
- Paweł Huryn's post with the quote and Cherny's 16-minute video (X): https://x.com/PawelHuryn/status/2069363303952818474
- Addy Osmani's LinkedIn post "Designing Loops for Coding Agents": https://www.linkedin.com/posts/addyosmani_ai-softwareengineering-programming-activity-7469999258658791425-cTvy

## Repositories (GitHub)

| Repository | What it offers |
|------------|----------------|
| [cobusgreyling/loop-engineering](https://github.com/cobusgreyling/loop-engineering) | Patterns, starters, and a CLI (`loop-audit`, `loop-init`, `loop-cost`); inspired by Osmani and Cherny |
| [dlmastery/loop_engineer](https://github.com/dlmastery/loop_engineer) | Skill pack for Claude Code: self-prompting loops (automations, worktrees, memory, subagents, connectors) + templates |
| [ChaoYue0307/awesome-loop-engineering](https://github.com/ChaoYue0307/awesome-loop-engineering) | Curated field guide: separates loop engineering from prompt/context/harness engineering; loop contracts, examples |
| [AI-Builder-Club/loop-engineer-template](https://github.com/AI-Builder-Club/loop-engineer-template) | Starter template for a "loop engineer" agent: triggers itself, picks up work, verifies, logs |
| [walkinglabs/learn-harness-engineering](https://github.com/walkinglabs/learn-harness-engineering) | Tutorial on harness engineering "from 0 to 1" (an adjacent discipline) |
| [github.com/topics/agent-loops](https://github.com/topics/agent-loops) | Topic hub of related projects |

## The term in the context of skill evolution

Prompt engineering (2023) → context engineering (2024–25) → **loop engineering / harness
engineering (2026)**. The idea: the bottleneck shifted from *prompt wording* to *loop design* —
the trigger, topology, verifier, and stopping rules that decide what the agent does next and
when it stops.

## References

- https://valentinaalto.medium.com/introducing-loop-engineering-ac7a6098bb10
- https://addyosmani.com/blog/loop-engineering/
- https://www.oreilly.com/radar/loop-engineering/
- https://thenewstack.io/loop-engineering/
- https://newsletter.pragmaticengineer.com/p/what-is-loop-engineering
- https://x.com/PawelHuryn/status/2069363303952818474
