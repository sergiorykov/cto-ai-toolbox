# Repo conventions

The conventions the repo lives by: languages, text style, naming, research lifecycle, approval.

## Languages

- English is the primary language of docs and communication.
- Some docs also exist in Russian: text and sources in Russian, filename in English with the `-ru` suffix. Every folder with such docs keeps them in its `ru/` subfolder (`xxxx/main-doc.md` + `xxxx/ru/main-doc-ru.md`).
- EN docs never mention localizations; each ru doc links its EN base next to the title.
- In research the base is EN-only with English sources; ru docs enrich it with Russian-language sources.

## Text style

- Minimum descriptiveness: living, laconic text, understandable on its own.
- A human will not read walls of AI text: trust appears when readers see themselves in the text — answers to their questions, with examples. The practical orientation and the approval gate exist for this.
- Say everything in exactly one place: prefer cross-links over repetition — better several smaller docs than duplicated content.
- No change history inside documents — git holds it. When adding or changing content, integrate it into the doc without explanatory insertions.

## Naming and diagrams

- Files and folders: lowercase-with-hyphens, md format.
- Diagrams preferably in mermaid; if something fits the task better or features are missing — ask back and propose the optimal option.

## Research structure and lifecycle

- A research runs in `research/<topic>/` (a sonorous subfolder). Its task is to enrich the knowledge base: on completion the results move under [knowledge-base/](../knowledge-base/) into a fitting group, or a new group is created.
- A research always has `xxxx-overview.md` (accessibly explains the meaning; proposes further useful cases per the [vision](vision-ai-assisted-cto.md)), `xxxx-<specific>.md` deep dives and `xxx-case-yyy.md` usage cases.

## Cross-links and landings

- Every folder's `README.md` is a landing: the meaning and intro plus a cross-link table of nested folders and docs.
- Docs cross-link each other and their sources: in-text mentions become links, duplicated at the end in a References/Дополнительные ресурсы section.
- The root `README.md` is a clean public mini-landing (knowledge-base overview + how to contribute); technical pages live in [CONTRIBUTING.md](../CONTRIBUTING.md).

## Doc header and approval

- The title is the `# H1`; the description is the paragraph under it.
- New and changed docs carry the technical marker `requires_approve: true` + `last_updated`; the CTO deletes it on approval; any edit to an approved doc brings it back. Only unmarked docs are ground truth.

## Planning

- Planning lives in [docs/](../docs/): specs in `docs/specs/` (brainstorming output; approval = marker removal), plans in `docs/plans/` (writing-plans output) — both committed before execution starts, and the spec updated afterwards if reality deviated.
- Trivial edits (typos, links, 1–2 docs without change of meaning) skip the spec — said explicitly.
- Work in atomic quanta, no doc bombs; the number of unapproved docs must shrink; commit-as-is only on explicit human force.
- `.superpowers/` (ephemeral skill state) never goes into git — it is in the root `.gitignore`.

## References

- [CLAUDE.md](../CLAUDE.md) — operating guide enforcing these conventions
- [collaboration-principles.md](collaboration-principles.md) — collaboration principles
- [vision-ai-assisted-cto.md](vision-ai-assisted-cto.md) — the vision
