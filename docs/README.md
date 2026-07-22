---
requires_approve: true
last_updated: 2026-07-22
---

# docs/

Planning home of the repo: **all specs and plans for all researches and tasks live here** (per [repo-conventions.md](../principles/repo-conventions.md)). The flow, mandated by [CLAUDE.md](../CLAUDE.md): brainstorming → approved design in `specs/` (committed before execution) → plan in [plans/](plans/) (committed before execution) → work runs in [research/](../research/) → results promoted into [knowledge-base/](../knowledge-base/) → spec updated if reality deviated.

## Contents

| Item | What it is |
|---|---|
| specs/ | Approved designs from `superpowers:brainstorming`, named `YYYY-MM-DD-<topic>-design.md`; the CTO removing the spec's `requires_approve` marker is the gate to start work |
| [plans/](plans/) | Execution plans from `superpowers:writing-plans`, one file per research/task, named `YYYY-MM-DD-<topic>.md` |
| [plans/2026-07-22-source-lists-research.md](plans/2026-07-22-source-lists-research.md) | Spec of the first research: curated source lists |

## References

- [principles/repo-conventions.md](../principles/repo-conventions.md) — why planning lives here
- [principles/research-backlog.md](../principles/research-backlog.md) — the CTO's task statements feeding these plans
- [CONTRIBUTING.md](../CONTRIBUTING.md) — the personal AI team executing the plans (`.claude/agents/`)
