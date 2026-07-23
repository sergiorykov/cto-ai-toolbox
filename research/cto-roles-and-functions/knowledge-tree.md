---
requires_approve: true
last_updated: 2026-07-23
---

# Knowledge tree

Prototype structure of [knowledge-base/](../../knowledge-base/), derived from the [function map](cto-role-tree.md) of the CTO role. Branch skeleton only — a branch gets its `README.md` landing and `sources.md` at creation; practice docs are written as researches land, never scaffolded empty. `ru/` subfolders appear where Russian sources exist.

```text
knowledge-base/
├── README.md
├── cto-role/
├── strategy-and-architecture/
├── org-design/
├── people/
├── delivery/
├── operations-and-security/
├── business-partnership/
├── culture/
├── ai-practices/
│   └── loop-engineering/
└── tools/
```

AI-leverage placement decision: `ai-practices/` holds AI-era practice packages (how to work with AI); the per-instrument AI-leverage marks live in the [role tree](cto-role-tree.md) itself. No per-branch ai-leverage files — cross-links instead of duplication.

## Where existing content goes

| Today (flat) | Target branch |
|---|---|
| [cto.md](../../knowledge-base/cto.md) | `cto-role/` (+ the promoted [cto-role-tree.md](cto-role-tree.md)) |
| [technologies.md](../../knowledge-base/technologies.md) | `strategy-and-architecture/` (game-dev/Unity part stays a section) |
| [tech-radars.md](../../knowledge-base/tech-radars.md) | `strategy-and-architecture/` |
| [management.md](../../knowledge-base/management.md) | split: `people/` + `org-design/` |
| [agile-scrum.md](../../knowledge-base/agile-scrum.md) | `delivery/` |
| [em-dm-discovery-delivery.md](../../knowledge-base/em-dm-discovery-delivery.md) | split: `delivery/` + `business-partnership/` |
| [engineering-principles.md](../../knowledge-base/engineering-principles.md) | split: `culture/` + `delivery/` |
| [ru/](../../knowledge-base/ru/) (6 lists) | `ru/` subfolders of the matching branches |
| [ai-practices/](../../knowledge-base/ai-practices/) · [tools/](../../knowledge-base/tools/) | stay as-is |

## Acceptance test — the heavy-research backlog

Every [backlog](../../principles/research-backlog.md) research has one clean primary home: Unity AI impact → `strategy-and-architecture/` (the bet) with the practice landing in `ai-practices/`; AI exploratory testing for HOPA → `delivery/` (quality) with the practice in `ai-practices/`; docker-compose deployment across DCs without k8s → `operations-and-security/`.

At promotion time the AI-team contexts (`.claude/agents/`) get wired to the promoted role tree so agents triage requests against its branches.

## References

- [cto-role-tree.md](cto-role-tree.md) — the function map this tree is derived from
- [docs/plans/2026-07-23-cto-roles-and-functions.md](../../docs/plans/2026-07-23-cto-roles-and-functions.md) — plan incl. the restructuring follow-up
