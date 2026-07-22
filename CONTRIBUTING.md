# Contributing

This repo is maintained AI-first: the operational source of truth for every rule is [CLAUDE.md](CLAUDE.md) — both humans and AI assistants follow it. This page is the short human entry point; when in doubt, CLAUDE.md wins.

## Repo map

| Folder | Purpose |
|---|---|
| [knowledge-base/](knowledge-base/) | All final artifacts: curated source lists, practice groups ([ai-practices/](knowledge-base/ai-practices/)), tools docs. |
| [principles/](principles/) | The repo's principles: the CTO's verbatim theses (vision, collaboration, conventions, backlog) + the [consultant stance](principles/consultant-stance.md). |
| [research/](research/) | Research workbench — one subfolder per topic; results are promoted into knowledge-base/ on completion. |
| [docs/](docs/) | Planning home: approved designs in `docs/specs/`, execution plans in [docs/plans/](docs/plans/). |
| `.claude/agents/` | Working definitions of the personal AI team (Claude Code subagents) — described in [principles/using-ai-agents.md](principles/using-ai-agents.md). |

## How work happens

- Trust: a new or changed doc carries the technical `requires_approve` marker; the CTO deletes it on approval. No marker → approved ground truth; marker → useful context. Duties and details: [CLAUDE.md](CLAUDE.md).
- Non-trivial work goes brainstorming → spec in `docs/specs/` → plan in [docs/plans/](docs/plans/) → execution, always in atomic quanta.
- All format and structure rules — languages, text style, naming, linking, landings, research lifecycle, planning — live in [principles/repo-conventions.md](principles/repo-conventions.md) (single source).

## References

- [CLAUDE.md](CLAUDE.md) — full operating guide (source of truth)
- [principles/repo-conventions.md](principles/repo-conventions.md) — conventions in the CTO's own words
- [principles/vision-ai-assisted-cto.md](principles/vision-ai-assisted-cto.md) — why this repo exists
- [docs/README.md](docs/README.md) — planning home
