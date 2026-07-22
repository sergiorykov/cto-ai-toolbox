---
title: cto-ai-toolbox
description: Landing page — living practices and tools amplifying a CTO, with a map of the repo
last_updated: 2026-07-22
approved_by:
approved_when:
---

# cto-ai-toolbox

AI agents/skills for day to day job as a CTO.

Living practices and tools that amplify a CTO — a knowledge base built so that **any CTO can take a doc and implement it**. The core idea: the CTO is a hardcore Individual Contributor first, and AI (tools + a personal team of AI agents with different skills) is what lets one person pass through the cognitive complexity of any task — closing blind spots across business, development, org design, risks and IT strategy. Full intent: [Vision of AI-assisted CTO](personal/vision-ai-assisted-cto.md).

**Trust model:** every doc carries `approved_by` / `approved_when` frontmatter. Only docs approved by the CTO are ground truth; everything else is useful-but-unapproved context. Rules of the repo: [CLAUDE.md](CLAUDE.md).

## Map

| Folder | What's inside |
|---|---|
| [personal/](personal/) | The CTO's own theses: vision, collaboration principles, conventions, research backlog. Verbatim, never synthesized. |
| [knowledge-base/](knowledge-base/) | All final artifacts: curated source lists (EN base + RU enrichment), AI practices ([ai-practices/](knowledge-base/ai-practices/)), tools docs. |
| [research/](research/) | Research workbench — one subfolder per topic; results are promoted into knowledge-base/ on completion. |
| [docs/](docs/) | Planning home: specs and plans for all researches and tasks, plus the consultant stance. |
| [agents/](agents/) | Personal AI team: specs of agents plugged in per request to validate, challenge and research. Installed as real Claude Code subagents in `.claude/agents/`. |

## References

- [CLAUDE.md](CLAUDE.md) — operating guide (conventions, trust model, lifecycle)
- [personal/vision-ai-assisted-cto.md](personal/vision-ai-assisted-cto.md) — Vision of AI-assisted CTO
- [knowledge-base/](knowledge-base/) — all final artifacts (source lists, practices, tools)
- [knowledge-base/ai-practices/loop-engineering/](knowledge-base/ai-practices/loop-engineering/) — loop engineering practice package
