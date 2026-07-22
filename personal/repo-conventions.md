---
title: Repo conventions
description: Faithful English translation of the CTO's verbatim theses on structure, languages, naming and doc format; ru file is source of truth
last_updated: 2026-07-22
approved_by:
approved_when:
---

# Repo conventions

Faithful translation of the Russian original — [repo-conventions-ru.md](repo-conventions-ru.md) is the source of truth. No synthesized additions.

## Languages

> The primary language of communication and docs is EN. In particular cases some docs will be in RU, and RU docs always sit next to the base docs: `main-doc.md` / `main-doc-ru.md` (the `-ru` suffix).

> EN separately (it is always the basis of research), and RU additionally (enriching the base docs). Base docs — EN only. RU docs — all sources in Russian, the doc's text in Russian. RU doc filenames — in English.

## Naming and diagrams

> Naming of all files and folders: lowercase-with-hyphens, in md format. Diagrams preferably in mermaid — if something fits the task better, or features are missing — ask back and propose the optimal option.

## Research doc structure

> In research always produce docs `xxxx-overview.md`, `xxxx-smth-specific.md`, so that the overview can always accessibly explain the meaning of the tool, approach, etc.; and additionally, in the research, driven by the CTO vision, add which usage variants need to be researched further or would be useful. Format usage cases as `xxx-case-yyy.md`.

## Research lifecycle

> For conducting research use the `research` folder with a sonorous subfolder, like `loop-engineering`; and upon completion — the data always moves into a main folder, or a new top-level one is created. That is, for loop-engineering a top-level folder must be invented where such questions will be grouped — for example, `ai-principles` or something in that spirit. The task of research is to enrich the knowledge base.

Refinement (statement of 2026-07-22, later the same day):

> Let's keep all final artifacts in `sources`. `ai-practices` inside it. And loop — into a separate `loop-engineering` folder with a README.md; and in `ai-practices` also a README.md per the stated rules.

## Cross-links and landings

> In every top-level folder use README.md as a landing that gives the meaning and intro for its content, and a table of cross-links to nested folders and docs.

> All docs contain cross-links between each other and to other sources. In documents, always turn in-text mentions into links, and at the end of the page duplicate them explicitly in a References/Дополнительные ресурсы section.

Refinement (statement of 2026-07-22, later):

> Remove the approval section from the root readme — it is like a mini-landing. Clean and for humans. Move the technical pages out into CONTRIBUTE.md, and in readme.md keep only the overview of the knowledge-base, with how to contribute at the end. Like a landing page.

## Doc format and trust

> Formatting of all docs: add to the beginning of every doc a section title/description/last_updated and — most importantly — approved_by, approved_when. You may rely only on docs that carry my approval — all other generated docs are context only, about which you always explicitly state that it has not passed approval but contains something useful — for the case when I go too wide into context and start abandoning researches.

## Planning

> For planning use /docs/ (I believe your planning skill is called superpowers) — and here all the specs for all researches and tasks.

Refinement (statement of 2026-07-22): a dump of the planning rules from another project of the CTO, with the instruction "take the best from it — how planning itself works via superpowers — and update claude.md":

> ## Specs and plans — mandatory
>
> - Any new functionality, behavior change or non-trivial refactoring starts with the superpowers:brainstorming skill. No code is written until the design is approved.
> - Save the approved spec to docs/superpowers/specs/YYYY-MM-DD-<topic>-design.md and commit it as a separate commit before implementation starts.
> - After the spec — superpowers:writing-plans: the plan goes to docs/superpowers/plans/YYYY-MM-DD-<feature>.md, also committed before code.
> - At the end of the work on a feature, update the spec if the implementation deviated from it: the spec must describe what was actually done.
> - Exception: trivial edits (typos, config, a bugfix in 1–2 files without behavior change) — no spec needed, but explicitly say the task is going without a spec.
>
> ## Separation of docs/superpowers/ and .superpowers/
>
> - docs/superpowers/ — permanent documentation (specs, plans). Always committed to git.
> - .superpowers/ — ephemeral working state of skills (review diffs and progress.md from subagent-driven-development, brainstorm-server mockups). Never goes into git.
> - .superpowers/ must be in the root .gitignore. Add this line right at project initialization — do not rely on the nested self-ignores of individual skills.
> - The contents of .superpowers/ can be deleted after a feature completes; nothing valuable for history lives there.

Adaptation in this repo (see [CLAUDE.md](../CLAUDE.md), section "Specs and plans — mandatory"): docs/specs/ and docs/plans/ are used instead of docs/superpowers/* (the /docs/ canon is set above); design approval = filling approved_by/approved_when in the spec.

## Approval, atomicity, knowledge base

Statement of 2026-07-22 (later the same day):

> Add to claude.md that if a file changes, the approval falls off. And you explicitly push the author to get the changed files approved (this commit — allow me to push as-is), but further on always demand atomicity — right now this is RnD of the structure; further on, return the request author (me or a collaborator) to atomicity of work — no code bombs (doc bombs) — and so that the number of docs without approvals does not grow — better, only shrinks. You may propose, from time to time at the start of a new session, to review a few docs. Only force from a human — and you commit as-is (but always try to propose conducting the work so that every quantum leads to a small improvement of the knowledge base). Let's name sources knowledge-base.

## References

- [repo-conventions-ru.md](repo-conventions-ru.md) — verbatim Russian original (source of truth)
- [collaboration-principles.md](collaboration-principles.md) — collaboration principles
- [CLAUDE.md](../CLAUDE.md) — operating guide implementing these conventions
