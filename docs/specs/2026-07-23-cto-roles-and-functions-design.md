# CTO roles and functions — design

Research design: map the CTO role for SMB/SME tech companies — expectations from four audiences and the instruments/practices that close them — and derive from it the target knowledge tree of this repo.

## Goal

1. **One tree-structured doc**: what a CTO needs to work effectively and lead the company. Branches: expectations from the business, from the team, from line employees, from C-level peers; per expectation — the instruments, practices and artifacts that close it. CTO levels distinguished where expectations differ (startup / scale-up / established SME).
2. **A prototype knowledge tree**: folders and final files with self-describing names, no annotations — the future structure of [knowledge-base/](../../knowledge-base/). The current flat source-lists layout is wrong by the CTO's decision; after this research the lists get redistributed into the new tree (separate follow-up task).
3. **A separate sources doc** (EN, annotated and link-verified) + ru companion including the Avito playbook; the EN docs may take the playbook's meanings explicitly.

## Scope

- Company context: SMB/SME IT tech, up to 250 people total, up to 100 in IT. Out of scope: scale management (SAFe trains, LeSS and the like appear beyond this size).
- Feed from already-collected sources ([cto.md](../../knowledge-base/cto.md), [management.md](../../knowledge-base/management.md), [engineering-principles.md](../../knowledge-base/engineering-principles.md) and the ru lists), CTO course curricula, books and articles, public company engineering principles and playbooks.

## Deliverables — `research/cto-roles-and-functions/`

| File | Content |
|---|---|
| `README.md` | Landing |
| `cto-roles-and-functions-overview.md` | Meaning, how any CTO uses the tree, proposed follow-up cases |
| `cto-role-tree.md` | Phase 1: the single-file tree — audiences → expectations → instruments/practices |
| `knowledge-tree.md` | Phase 2: prototype folder/file tree for knowledge-base/ |
| `cto-role-sources.md` | EN sources |
| `ru/cto-role-sources-ru.md` | RU sources incl. Avito playbook |

## Method

- Phase 1 — parallel research lenses: one agent per audience (business, team, line engineers, C-level peers) + a sweep of CTO course curricula and playbooks; challenger pass over the draft tree; synthesis into one tree.
- Phase 2 — derive the knowledge-tree from the role tree's top branches; validate that all existing content (source lists, ai-practices, tools) has a home in it.
- Sources: primary-first, links verified, "primary source" vs "retelling" labeled.

## Quality bar

- Every expectation names who holds it and the practice/instrument that answers it — any CTO can take and apply.
- Tree depth ≤ 4, branches MECE; no scale-management content.
- Both trees fit their single files and read without extra commentary.

## Defaults taken (correct at approval if wrong)

- Research folder: `research/cto-roles-and-functions/`.
- Knowledge-base target group at promotion: `knowledge-base/cto-role/` — final call at promotion time.

## References

- [principles/vision-ai-assisted-cto.md](../../principles/vision-ai-assisted-cto.md) — the vision this serves
- [principles/research-backlog.md](../../principles/research-backlog.md) — backlog context
- [knowledge-base/cto.md](../../knowledge-base/cto.md) · [management.md](../../knowledge-base/management.md) · [engineering-principles.md](../../knowledge-base/engineering-principles.md) — seed sources
