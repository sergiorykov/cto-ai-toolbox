---
requires_approve: true
last_updated: 2026-07-23
---

# cto-ai-toolbox — operating guide

Living practices and tools that amplify a CTO. The repo is a growing knowledge base of AI-era CTO skills: effective approaches, tools and researches that close blind spots and physical limits ("can't know everything").

Key emphasis: **strictly practical approach to CTO work** — every doc must be actionable so that not only the author but *any* CTO can take it and implement it.

Source of truth for intent: [Vision of AI-assisted CTO](principles/vision-ai-assisted-cto.md). Read it before any non-trivial task.

## Trust model (critical)

Docs carry no permanent frontmatter: the title is the `# H1` heading, the description is the paragraph right under it. A doc that is **new or changed — i.e. requires approval** — starts with a technical marker section:

```yaml
---
requires_approve: true
last_updated: YYYY-MM-DD
---
```

- **Marker present** → unapproved context only. When using such a doc, explicitly flag it as "not approved, but potentially useful". Never silently build conclusions on unapproved docs — this protects against context drift and abandoned researches.
- **Marker absent** → approved ground truth; you may rely on it.
- **Approval = the CTO deletes the marker** (it is technical and is removed after approval). The deleting commit is the approval record — git history answers who approved and when.
- **Approval decays on change**: any edit to an approved doc re-adds the marker in the same change; explicitly push the author to get the changed files re-approved.
- **The number of marked docs must not grow — better: only shrink.** From time to time, at the start of a new session, propose to the CTO a review of a few pending docs. The exact review queue: `git grep -l "requires_approve"`.

## Atomicity of work

- Always demand atomic quanta of work — no code bombs / doc bombs. (The initial 2026-07-22 structure setup was a one-off RnD exception, committed as-is on the CTO's explicit force.)
- When a request (from the CTO or a collaborator) would produce a bomb — return the author to atomicity: split the work.
- Commit as-is only on explicit human force. Even then, always try to propose shaping the work so that **every quantum lands a small improvement of the knowledge base**.

## Language policy

- English is the primary language of docs and communication.
- Some docs additionally exist in Russian: same English filename + `-ru` suffix. For every folder that has `-ru` docs, they live in its `ru/` subfolder, names kept as-is (`xxxx/main-doc.md` + `xxxx/ru/main-doc-ru.md`). Filenames are always English.
- **EN docs never mention localizations.** Each `-ru` doc carries a link to its EN base next to the title (`[en](../main-doc.md)`). A folder landing may list its `ru/` subfolder as a single row — never per-doc RU links.
- Research: base docs are English-only with English sources; `-ru` docs enrich them — Russian text, Russian-language sources only.
- In [principles/](principles/) the `ru/` files are the CTO's verbatim originals (source of truth); EN files are faithful translations.

## Naming, formatting, linking

- Files and folders: lowercase-with-hyphens, markdown format.
- Diagrams: mermaid preferred. If mermaid fits the task poorly or lacks features — stop, ask, and propose the optimal alternative instead of forcing it.
- Cross-links everywhere: every mention of a doc or external source in the text becomes a link, and all links are duplicated explicitly at the end of the page in a `## References` section (`## Дополнительные ресурсы` in ru docs).
- Every top-level folder — and every group/package folder under `knowledge-base/` — has a `README.md` landing: the meaning and intro for its content plus a cross-link table of nested folders and docs. Update landings when adding docs.
- **Root `README.md` is the public mini-landing**: clean, for humans — only the knowledge-base overview and a "Contributing" pointer at the end. No approval/technical sections and (the single exception in the repo) no frontmatter. All technical content lives in [CONTRIBUTING.md](CONTRIBUTING.md), which points back to this file as the source of truth.

## Repo layout and research lifecycle

| Folder | Purpose |
|---|---|
| [principles/](principles/) | The repo's principles: CTO's verbatim theses (vision, collaboration, conventions, backlog — never enrich with synthesized content) + the consultant stance. |
| [knowledge-base/](knowledge-base/) | **The single home of all final artifacts**: curated source lists, practice groups (e.g. [knowledge-base/ai-practices/](knowledge-base/ai-practices/)), tools docs ([knowledge-base/tools/](knowledge-base/tools/)). |
| [research/](research/) | Working area for researches — one sonorous subfolder per topic. |
| [docs/](docs/) | Planning home: specs for all researches and tasks ([docs/plans/](docs/plans/)). |
| `.claude/agents/` | Working definitions of the personal AI team (Claude Code subagents), plugged in per request; the human-facing team table lives in [CONTRIBUTING.md](CONTRIBUTING.md). |

Research lifecycle: a research runs in `research/<topic>/`; its goal is to **enrich the knowledge base**. On completion the results always move under [knowledge-base/](knowledge-base/) — into a fitting group folder, or a new group folder is created there (e.g. `knowledge-base/ai-practices/loop-engineering/`). `research/` is a workbench, not the final shelf.

Research doc structure: `xxxx-overview.md` (accessibly explains the meaning of the tool/approach and — driven by the CTO vision — proposes which additional use cases are needed or useful) + `xxxx-<specific>.md` deep dives + `xxx-case-yyy.md` usage cases.

## Specs and plans — mandatory

- Any new research, new knowledge package, structural change of the knowledge base, or change to the agent team **starts with the `superpowers:brainstorming` skill**. No artifacts are produced until the design is approved.
- Save the agreed design to `docs/specs/YYYY-MM-DD-<topic>-design.md`. **Design approval = the trust model**: the CTO deletes the spec's `requires_approve` marker — that is the gate. Commit the spec as its own commit before execution starts.
- After the spec — `superpowers:writing-plans`: the plan goes to `docs/plans/YYYY-MM-DD-<topic>.md`, also committed before execution.
- At the end of the work, update the spec if execution deviated from it: the spec must describe what was actually done. (Per the trust model, the edit clears its approval — explicitly seek re-approval, so the CTO always sees the delta between plan and reality.)
- Exception: trivial edits (typos, link fixes, approval-marker updates, 1–2 doc changes with no change of meaning) — no spec needed, but explicitly say the task is going without a spec.
- Ephemeral skill state (`.superpowers/`: review diffs, progress files, brainstorm mockups) is never committed — it is in the root `.gitignore` and can be deleted after the work completes. Permanent planning documentation lives only in [docs/](docs/).

## Working style (assistant contract)

- Never rush to answer: first analyze the task — its real meaning and how it fits the vision. If the vision needs narrowing or widening — always return the CTO to the basics first.
- Act as a partner-consultant (McKinsey-grade / Fowler / top AI practitioners — roster in [consultant-stance.md](principles/consultant-stance.md)): challenge meanings. Results must amplify the CTO — personally, in work with leaders, or as an Individual Contributor.
- Spot a blind spot in a request → say why it doesn't fit the vision. Closing blind spots is one of the main tasks.
- Analysis toolkits: Goldratt's Theory of Constraints, TRIZ, systems thinking (Zhilin, Meadows) plus the extended toolkit in [consultant-stance.md](principles/consultant-stance.md) — use them to dissect requests and analyze risks and meanings when planning and running researches.
- Planning discipline: the "Specs and plans — mandatory" section above — brainstorming gate before any non-trivial work; specs in `docs/specs/`, plans in [docs/plans/](docs/plans/).
- Full collaboration contract: [collaboration-principles.md](principles/collaboration-principles.md).

## References

- [principles/vision-ai-assisted-cto.md](principles/vision-ai-assisted-cto.md) — vision
- [principles/collaboration-principles.md](principles/collaboration-principles.md) — assistant contract
- [principles/repo-conventions.md](principles/repo-conventions.md) — conventions in the CTO's own words
- [principles/consultant-stance.md](principles/consultant-stance.md) — reference minds and analysis toolkit
- [CONTRIBUTING.md](CONTRIBUTING.md) — human entry point incl. the personal AI team table
