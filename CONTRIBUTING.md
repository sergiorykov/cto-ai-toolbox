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
| [personal/](personal/) | The CTO's own theses (vision, principles, conventions, backlog) — verbatim, never enriched with synthesized content. |
| [research/](research/) | Research workbench — one subfolder per topic; results are promoted into knowledge-base/ on completion. |
| [docs/](docs/) | Planning home: approved designs in `docs/specs/`, execution plans in [docs/plans/](docs/plans/), the [consultant stance](docs/consultant-stance.md). |
| [agents/](agents/) | Specs of the personal AI team; installed as working Claude Code subagents in `.claude/agents/`. |

## Trust model

Docs have no permanent frontmatter — the title is the `# H1`, the description is the paragraph under it. A doc that is new or changed carries a technical marker at the top (`requires_approve: true` + `last_updated`); the CTO deletes the marker on approval.

- Marker absent → the doc is approved ground truth.
- Marker present → useful context only; always flagged as such when relied upon.
- **Any edit to an approved doc re-adds the marker** — get the changed files re-approved; the marker-deleting commit is the approval record.
- The number of marked docs must not grow; better — only shrink.

## How work happens

- Any non-trivial work (new research, knowledge package, structural change) starts with a brainstorming session → an approved design in `docs/specs/` (committed before execution) → a plan in [docs/plans/](docs/plans/) (committed before execution) → execution → the spec updated if reality deviated.
- Work in **atomic quanta** — no code bombs / doc bombs; every quantum should land a small improvement of the knowledge base.
- Trivial edits (typos, links, 1–2 docs without change of meaning) skip the spec — but say so explicitly.

## Conventions

- English is the primary language; Russian companions keep the `-ru` suffix and live in a `ru/` subfolder of the folder holding their base docs (filenames always English).
- Files and folders: `lowercase-with-hyphens.md`. Diagrams: mermaid preferred.
- Mentions in text become links; all links are duplicated in a `References` section at the end of the page.
- Every folder has a `README.md` landing: meaning + a cross-link table. Keep landings updated.

## References

- [CLAUDE.md](CLAUDE.md) — full operating guide (source of truth)
- [personal/repo-conventions.md](personal/repo-conventions.md) — conventions in the CTO's own words
- [personal/vision-ai-assisted-cto.md](personal/vision-ai-assisted-cto.md) — why this repo exists
- [docs/README.md](docs/README.md) — planning home
