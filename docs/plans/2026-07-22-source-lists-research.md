---
requires_approve: true
last_updated: 2026-07-22
---

# Source-lists research — spec & plan

**Goal:** a separate folder with curated source lists — technologies, management, agile/scrum, EM/DM discovery-delivery, CTO (awesome lists), tech radars, engineering principles of large companies — as stated verbatim in the [research backlog](../../personal/research-backlog.md).

**Approach:** parallel research agents, one per category cluster; English base docs with English sources only; `-ru` companions with Russian sources where strong ones exist; every entry annotated (what it is + why valuable for the CTO) and link-verified.

**Working area:** was `research/source-lists/`; on completion the results were promoted to the top-level folder [knowledge-base/](../../knowledge-base/) (CTO decisions, 2026-07-22: promoted to `sources/`, renamed to `knowledge-base/` the same day) per the [research lifecycle](../../CLAUDE.md).

## Global constraints

- Doc format per [CLAUDE.md](../../CLAUDE.md): frontmatter, lowercase-with-hyphens naming, cross-links in text + References section.
- Base docs: EN only, EN sources only. RU docs: `-ru` suffix, English filenames, Russian text, Russian sources only.
- No invented URLs: links verified or explicitly marked `(unverified)`.
- 15–30 high-signal entries per file; no SEO listicles.

## Tasks

### Task 1: EN base docs — 7 categories

**Files (create):** `research/source-lists/technologies.md`, `tech-radars.md`, `engineering-principles.md`, `cto.md`, `management.md`, `agile-scrum.md`, `em-dm-discovery-delivery.md`

- [x] Dispatch 4 parallel research agents (technologies+radars; principles+cto; management; agile+discovery-delivery)
- [x] Each agent: gather canonical sources, annotate each entry for the CTO, verify links via web tools
- [x] All 7 files written with required frontmatter — done 2026-07-22, 172 entries total, all links verified

### Task 2: RU enrichment docs

**Files (create):** `research/source-lists/<category>-ru.md` — only for categories with genuinely strong Russian sources (expected minimum: `management-ru.md`, `cto-ru.md`, `tech-radars-ru.md`, `agile-scrum-ru.md`)

- [x] Dispatch RU research agent (Habr hubs, TeamLead Conf / HighLoad++ talks, Podlodka, public Russian company tech radars, quality tg-channels, Russian books/translations)
- [x] RU files written and link-verified — done 2026-07-22: 6 files, 71 entries; `engineering-principles-ru` deliberately skipped (no strong primary RU corpus); 3 links marked `(unverified)` (fetch-blocked radars)

### Task 3: Research packaging

**Files (create):** README landing with cross-link table + overview (meaning + proposed further use cases per the vision) — now [knowledge-base/README.md](../../knowledge-base/README.md) and [knowledge-base-overview.md](../../knowledge-base/knowledge-base-overview.md)

- [x] Write overview with proposed follow-up cases
- [x] Write README landing (complete table incl. RU files)

### Task 4: Validation pass

- [ ] Run [validator](../../agents/validator.md) checklist over all files: claim audit, link audit, convention audit
- [ ] Fix defects found

### Task 5: CTO approval gate

- [ ] CTO reviews each doc; removes the `requires_approve` marker on accepted ones
- [ ] Rejected/parked docs stay as flagged unapproved context

### Task 6: Promotion to knowledge base

- [x] Agree the top-level target folder — `sources/` approved by the CTO, 2026-07-22, renamed to `knowledge-base/` the same day (tools/ also moved under [knowledge-base/tools/](../../knowledge-base/tools/) by the same decision)
- [x] Move docs out of `research/` into [knowledge-base/](../../knowledge-base/); landings and cross-links updated. Note: promotion executed by the CTO's direct instruction ahead of the doc-approval gate (Task 5) — docs remain unapproved context until reviewed

## References

- [personal/research-backlog.md](../../personal/research-backlog.md) — the original task statement
- [knowledge-base/](../../knowledge-base/) — final home of the results
- [agents/validator.md](../../agents/validator.md) — validation checklist owner
- [CLAUDE.md](../../CLAUDE.md) — lifecycle and conventions
