---
title: Technology Source Lists
description: Curated awesome lists and canonical resources by technology domain for a hands-on CTO in a Unity game studio
last_updated: 2026-07-22
approved_by:
approved_when:
---

# Technology Source Lists

High-signal, canonical sources per technology domain. Every link was verified on 2026-07-22.

## System Design & Scalability

- **[The System Design Primer](https://github.com/donnemartin/system-design-primer)** — The most-starred GitHub guide to designing large-scale systems, with diagrams, trade-off discussions, and interview-style exercises. The fastest way to refresh or pressure-test any scalability decision before an architecture review.
- **[Awesome Scalability](https://github.com/binhnguyennus/awesome-scalability)** — A curated reading list on the patterns behind scalable, reliable, high-performance systems, organized by principle (scalability, availability, stability) and backed by real engineering-blog case studies. Ideal for grounding design debates in what actually worked at scale.
- **[Designing Data-Intensive Applications](https://dataintensive.net/)** — Official site of Martin Kleppmann's seminal book on storage, replication, partitioning, and stream processing. The single best mental-model builder for evaluating backend and data platform choices, including game-services backends.
- **[ByteByteGo Newsletter](https://blog.bytebytego.com/)** — Alex Xu's system-design newsletter with weekly visual deep dives into real-world architectures. Low-effort, high-retention way to stay sharp on system design as an IC-CTO.

## Software Architecture

- **[Awesome Software Architecture](https://github.com/mehdihadeli/awesome-software-architecture)** — A comprehensive curated repository of articles, books, and talks covering architectural styles (DDD, CQRS, event-driven, modular monolith) and patterns. A one-stop index when preparing an architecture decision or teaching a team a new style.
- **[martinfowler.com](https://martinfowler.com/)** — Martin Fowler's site: the canonical reference for refactoring, evolutionary architecture, microservices trade-offs, and CD. Its bliki entries are the shared vocabulary of the industry — useful for aligning architects and stakeholders on terms.
- **[Microservices.io](https://microservices.io/)** — Chris Richardson's pattern language for microservices: decomposition, sagas, service discovery, and when *not* to use microservices. Valuable as a neutral catalog for deciding how far to split game backend services.
- **[Architecture Decision Records](https://github.com/joelparkerhenderson/architecture-decision-record)** — The reference collection of ADR templates and examples. Directly reusable to institutionalize lightweight, auditable architecture decisions across teams — a core architect-side practice for a CTO.

## DevOps, SRE & Platform Engineering

- **[Google SRE Books](https://sre.google/books/)** — Free full texts of *Site Reliability Engineering*, the *SRE Workbook*, and *Building Secure and Reliable Systems*. The foundational canon for error budgets, SLOs, and on-call design — the reference point for any reliability conversation.
- **[Awesome SRE](https://github.com/dastergon/awesome-sre)** — Curated list of SRE resources on culture, monitoring, capacity planning, post-mortems, and toil reduction. A good delegation source: hand specific sections to leads building out reliability practices.
- **[DORA](https://dora.dev/)** — Google's DevOps Research and Assessment program: the four key delivery metrics, capability catalog, and annual State of DevOps reports. The evidence base for justifying engineering-performance investments to the business side.
- **[Platform Engineering community](https://platformengineering.org/)** — The hub of the platform engineering movement: definitions, maturity models, talks, and the PlatformCon archive. Useful for deciding whether and how to build an internal developer platform for game teams.

## Cloud & Infrastructure

- **[CNCF Landscape](https://landscape.cncf.io/)** — The Cloud Native Computing Foundation's interactive map of the entire cloud-native ecosystem with project maturity levels. The fastest way to survey options and gauge project health before adopting infrastructure tech.
- **[The Twelve-Factor App](https://12factor.net/)** — The classic methodology for building portable, cloud-ready services (config, dependencies, statelessness, logs). Still the baseline checklist for any backend service a game studio ships.
- **[Awesome Kubernetes](https://github.com/ramitsurana/awesome-kubernetes)** — Long-running curated list of Kubernetes resources: learning paths, tools, deployment patterns, and production stories. A practical index when scoping or auditing a k8s-based game-services stack.

## Security

- **[OWASP Top Ten](https://owasp.org/www-project-top-ten/)** — The industry-standard awareness document for the most critical web application security risks. The minimal shared language for security requirements with teams and external partners.
- **[Awesome Security](https://github.com/sbilly/awesome-security)** — Broad curated collection of security tools, resources, and reading across network, web, endpoint, and operations. A starting index for building a studio security toolkit without hiring a large security org.
- **[OWASP SAMM](https://owaspsamm.org/)** — The Software Assurance Maturity Model: a measurable framework to assess and improve an organization's secure development practices. Fits a CTO's risk-management remit — turns "are we secure?" into a staged roadmap.

## Data Engineering

- **[Awesome Data Engineering](https://github.com/igorbarinov/awesome-data-engineering)** — Curated list of data engineering tools across ingestion, warehousing, orchestration, and streaming. Useful for surveying the stack behind game analytics and LiveOps pipelines.
- **[Data Engineer Handbook](https://github.com/DataExpert-io/data-engineer-handbook)** — Zach Wilson's heavily-starred repository of everything needed to master data engineering: books, courses, communities, and project templates. A ready-made growth track to hand to analysts and engineers building the studio's data function.

## AI / LLM Engineering & AI-Assisted Development

- **[Awesome-LLM](https://github.com/Hannibal046/Awesome-LLM)** — The canonical curated list of large language model papers, frameworks, training/serving tools, and applications. The best single map of the LLM ecosystem when evaluating models or tooling.
- **[Awesome AI Agents](https://github.com/e2b-dev/awesome-ai-agents)** — Curated catalog of AI agent frameworks and products, both open-source and commercial. Useful for scanning the agent landscape before building internal automation or AI-assisted workflows.
- **[Building Effective Agents (Anthropic)](https://www.anthropic.com/engineering/building-effective-agents)** — Anthropic's engineering guide distinguishing workflows from agents and cataloging composable patterns that actually work in production. The most-cited sober reference for deciding how much agency an AI system needs.
- **[Your AI Product Needs Evals (Hamel Husain)](https://hamel.dev/blog/posts/evals/)** — The widely-referenced practitioner guide to building evaluation systems for LLM products: unit tests, human review, and LLM-as-judge. Essential before shipping any AI feature — evals are the CTO-level quality gate.
- **[Simon Willison's Weblog](https://simonwillison.net/)** — The highest-signal ongoing commentary on LLMs, AI-assisted development, and agent tooling, written by a veteran engineer who tests everything hands-on. The most efficient way to track what actually changed in AI each week.

## Game Development & Unity

- **[Magictools](https://github.com/ellisonleao/magictools)** — The largest curated list of game development resources: engines, art and audio tools, assets, and learning materials. A broad index for tooling decisions across the whole production pipeline.
- **[Awesome Unity](https://github.com/RyanNielson/awesome-unity)** — Curated list of Unity-specific assets, open-source projects, libraries, and community resources. Directly relevant for a 2D HOPA studio's engine tooling and package choices.
- **[Game Programming Patterns](https://gameprogrammingpatterns.com/)** — Robert Nystrom's free online book on design patterns as they apply to game code (game loop, component, object pool, state). The shared architecture vocabulary for reviewing Unity codebases with leads.
- **[GDC Vault — Free Content](https://gdcvault.com/free)** — Free talks from the Game Developers Conference across programming, production, design, and business. The primary source of postmortems and production practices from studios that shipped — including casual and mobile titles.
- **[Unity Best Practice Guides](https://docs.unity3d.com/Manual/best-practice-guides.html)** — Unity's official hub of best-practice documentation on performance, memory, assets, and project organization. The authoritative baseline for engineering standards in the studio's core engine.
