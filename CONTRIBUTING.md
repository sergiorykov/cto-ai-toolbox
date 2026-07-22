---
requires_approve: true
last_updated: 2026-07-22
---

# Contributing

This repo is maintained AI-first: the operational source of truth for every rule is [CLAUDE.md](CLAUDE.md) — both humans and AI assistants follow it. This page is the short human entry point; when in doubt, CLAUDE.md wins.

## Repo map

| Folder | Purpose |
|---|---|
| [knowledge-base/](knowledge-base/) | All final artifacts: curated source lists, practice groups ([ai-practices/](knowledge-base/ai-practices/)), tools docs. |
| [principles/](principles/) | The repo's principles: the CTO's verbatim theses (vision, collaboration, conventions, backlog) + the [consultant stance](principles/consultant-stance.md). |
| [research/](research/) | Research workbench — one subfolder per topic; results are promoted into knowledge-base/ on completion. |
| [docs/](docs/) | Planning home: approved designs in `docs/specs/`, execution plans in [docs/plans/](docs/plans/). |
| `.claude/agents/` | Working definitions of the personal AI team (Claude Code subagents) — see the team table below. |

## Personal AI team

Agents with different skills, plugged in per request — to validate, challenge and conduct researches. The working definitions live in [.claude/agents/](.claude/agents/); Claude Code picks them up automatically, or invoke one explicitly ("use the challenger agent on this").

| Agent | Role in one line |
|---|---|
| [research-analyst](.claude/agents/research-analyst.md) | Deep multi-source research; produces overview/specific/case docs |
| [challenger](.claude/agents/challenger.md) | Adversarial partner: attacks assumptions, meanings and vision-fit |
| [systems-mapper](.claude/agents/systems-mapper.md) | Models the system: constraints, feedback loops, leverage points |
| [tech-scout](.claude/agents/tech-scout.md) | Fast immersion into technologies and trends; radar duty |
| [validator](.claude/agents/validator.md) | Verifies facts, links and claims; prepares docs for approval |
| [biz-strategist](.claude/agents/biz-strategist.md) | Business lens: P&L, discovery, market, IT-strategy alignment |
| [org-designer](.claude/agents/org-designer.md) | Org structure, team topologies, grades, competency matrices |
| [risk-officer](.claude/agents/risk-officer.md) | Risk lens: pre-mortems, risk registers, AI risks |

## How work happens

- Trust: a new or changed doc carries the technical `requires_approve` marker; the CTO deletes it on approval. No marker → approved ground truth; marker → useful context. Duties and details: [CLAUDE.md](CLAUDE.md).
- Non-trivial work goes brainstorming → spec in `docs/specs/` → plan in [docs/plans/](docs/plans/) → execution, always in atomic quanta.
- All format and structure rules — languages, text style, naming, linking, landings, research lifecycle, planning — live in [principles/repo-conventions.md](principles/repo-conventions.md) (single source).

## References

- [CLAUDE.md](CLAUDE.md) — full operating guide (source of truth)
- [principles/repo-conventions.md](principles/repo-conventions.md) — conventions in the CTO's own words
- [principles/vision-ai-assisted-cto.md](principles/vision-ai-assisted-cto.md) — why this repo exists
- [docs/README.md](docs/README.md) — planning home
