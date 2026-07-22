---
title: loop-engineering — practice package
description: "Landing — loop engineering package: definition, history, deep dive, adoption case; EN base + RU companions"
last_updated: 2026-07-22
approved_by:
approved_when:
---

# loop-engineering

The practice that emerged in June 2026 as the next step after prompt engineering and context engineering in working with AI agents. One-line definition:

> "Loop engineering is when you stop being the person who prompts the agent. You design the system that does it for you." — Addy Osmani

The three figures it started with: **Peter Steinberger** (OpenClaw; "you should no longer prompt agents"), **Boris Cherny** (Claude Code lead at Anthropic; "I have loops running that prompt Claude"), **Addy Osmani** (named the practice and gave it its anatomy). Details and chronology: [loop-engineering-history.md](loop-engineering-history.md).

**Reliability caveat** (from the research, assembled 2026-07-22): the term is young (< 2 months at assembly time); many materials are secondary blogs retelling each other. The docs label "primary source" vs "overview/retelling". The academic frame is arXiv preprints, not peer-reviewed publications — treat as working theses.

## Docs

| Doc (EN base) | RU | About |
|---|---|---|
| [loop-engineering-overview.md](loop-engineering-overview.md) | [-ru](loop-engineering-overview-ru.md) | Meaning in two paragraphs, definition, anatomy of a loop, where the trend leads |
| [loop-engineering-history.md](loop-engineering-history.md) | [-ru](loop-engineering-history-ru.md) | Names, key posts, repositories, chronology of the term |
| [loop-engineering-deep-dive.md](loop-engineering-deep-dive.md) | [-ru](loop-engineering-deep-dive-ru.md) | Original articles + overviews + arXiv preprints + videos |
| [loop-engineering-case-monorepo-adoption.md](loop-engineering-case-monorepo-adoption.md) | [-ru](loop-engineering-case-monorepo-adoption-ru.md) | How-to: adoption plan for a fullstack monorepo (Node+PG+Docker), feature loop with Playwright |
| — | [loop-engineering-sources-ru.md](loop-engineering-sources-ru.md) | Russian-language authors and materials (Polomodov, Smirnov, Podlodka) |

**Docs are not individually approved yet** — context until the CTO fills `approved_by`/`approved_when` per the [trust model](../../../CLAUDE.md).

## References

- [ai-practices/README.md](../README.md) — parent group landing
- [docs/plans/2026-07-22-loop-engineering-promotion.md](../../../docs/plans/2026-07-22-loop-engineering-promotion.md) — the promotion spec
- [personal/research-backlog.md](../../../personal/research-backlog.md) — the CTO's instruction behind this package
