---
requires_approve: true
last_updated: 2026-07-22
---

# Loop-engineering promotion — spec & plan

**Goal:** fulfil the CTO's instruction: "for loop-engineering a top-level folder must be invented where such questions will be grouped — for example, ai-principles or something in that spirit" ([repo-conventions](../../personal/repo-conventions.md)).

**State before migration:** `research/loop-engineering/` was a completed ru-language research package (5 numbered files + README) that predated the repo conventions: transliterated numbered filenames, Russian base text, no frontmatter. Now migrated to [knowledge-base/ai-practices/loop-engineering/](../../knowledge-base/ai-practices/loop-engineering/).

## Decision

**`ai-practices/` — approved by the CTO, 2026-07-22.** (Alternatives considered: `ai-principles/` — narrower; `ai-engineering/` — too wide.)

**Refinement (CTO, 2026-07-22, later the same day):** all final artifacts live under one base folder (first named `sources/`, then renamed `knowledge-base/`) — so the group became [knowledge-base/ai-practices/](../../knowledge-base/ai-practices/), with the package in its own subfolder [knowledge-base/ai-practices/loop-engineering/](../../knowledge-base/ai-practices/loop-engineering/), each with a README landing.

## Tasks

### Task 1: Create the top-level folder

- [x] Create landings per [CLAUDE.md](../../CLAUDE.md): [knowledge-base/ai-practices/README.md](../../knowledge-base/ai-practices/README.md) (group) + [loop-engineering/README.md](../../knowledge-base/ai-practices/loop-engineering/README.md) (package)

### Task 2: Migrate content to conventions

- [x] Rename docs to convention: `01-predystoriya.md` → `loop-engineering-history-ru.md`, `02-obshiy-razrez.md` → `loop-engineering-overview-ru.md`, `03-glubokiy-razrez.md` → `loop-engineering-deep-dive-ru.md`, `04-russkoyazychnye-materialy.md` → `loop-engineering-sources-ru.md`, `05-howto-plan-vnedreniya.md` → `loop-engineering-case-monorepo-adoption-ru.md`
- [x] Produce EN base docs (faithful translations, code/configs kept byte-identical) — 4 EN docs; `loop-engineering-sources-ru.md` stays ru-only (Russian-sources enrichment doc)
- [x] Add frontmatter to every doc; reliability caveat kept in the [loop-engineering landing](../../knowledge-base/ai-practices/loop-engineering/README.md)
- [x] Add cross-links + References sections (EN↔RU pair links; References/Дополнительные ресурсы duplicated where the original lacked a links section)

### Task 3: Wire into the knowledge base

- [x] Update root [README.md](../../README.md) map and [research/README.md](../../research/README.md)
- [x] Remove `research/loop-engineering/` after content is fully moved (git history note: the folder was never committed — the original content survives only as the migrated `-ru` docs, which is why they preserve it verbatim)

### Task 4: Approval gate

- [ ] CTO reviews migrated docs and removes their `requires_approve` markers

## References

- [personal/repo-conventions.md](../../personal/repo-conventions.md) — the lifecycle instruction (verbatim)
- [knowledge-base/ai-practices/loop-engineering/](../../knowledge-base/ai-practices/loop-engineering/) — the promoted package
- [CLAUDE.md](../../CLAUDE.md) — target conventions
