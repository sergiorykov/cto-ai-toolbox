---
title: Technology Radars
description: Public technology radars, radar-building tooling, and guides for running your own radar
last_updated: 2026-07-22
approved_by:
approved_when:
---

# Technology Radars

Sources for tracking technology adoption decisions via the radar format, and for building the company's own radar. Every link was verified on 2026-07-22.

## ThoughtWorks Technology Radar

- **[ThoughtWorks Technology Radar](https://www.thoughtworks.com/radar)** — The original and most influential technology radar, published twice a year with techniques, tools, platforms, and languages rated Adopt/Trial/Assess/Hold. The industry's reference opinion for calibrating your own adoption decisions and vocabulary.
- **[Technology Radar FAQ](https://www.thoughtworks.com/radar/faq)** — ThoughtWorks' explanation of how the Radar is made: quadrants, rings, blips, and the internal Doppler process behind each volume. The methodology description to copy when designing your own radar process.

## Other Public Company & Community Radars

- **[Zalando Tech Radar](https://opensource.zalando.com/tech-radar/)** — The best-known company-specific public radar, maintained by Zalando's engineering organization to align hundreds of engineers on technology choices. A realistic model of radar scope and ring semantics for a mid-to-large engineering org.
- **[AOE Technology Radar](https://techradar.aoe.com/)** — AOE's public radar (currently version 9) covering languages and frameworks, methods and patterns, platforms and operations, and tools. A good example of a versioned radar with written justifications per blip.
- **[Digitec Galaxus Tech Radar](https://www.galaxus.ch/techradar/)** — Public radar of Switzerland's largest online retailer, using the classic Adopt/Trial/Assess/Hold rings. Another live example of a company radar embedded directly in the engineering culture and published openly.
- **[CNCF End User Technology Radars](https://www.cncf.io/reports/?_sft_lf-report-type=radar)** — Archived series of radars produced by CNCF's end-user community on topics like CI/CD, observability, and secrets management, reflecting what real adopters (not vendors) recommend. Useful as a template for topic-scoped, community-voted radars.
- **[Inspirational Technology Radar Examples](https://www.workingsoftware.dev/inspirational-technology-radar-examples/)** — A curated survey of public technology radars (ThoughtWorks, Zalando, AOE, Galaxus, and others) with commentary on their differences. A quick way to scan the landscape of radar styles before choosing your own format.

## Radar-Building Tooling

- **[thoughtworks/build-your-own-radar](https://github.com/thoughtworks/build-your-own-radar)** — ThoughtWorks' open-source app that generates an interactive radar visualization from a Google Sheet, CSV, or JSON file. The lowest-friction way to stand up a first company radar without writing code.
- **[zalando/tech-radar](https://github.com/zalando/tech-radar)** — The open-sourced code behind Zalando's radar visualization, a small D3.js library you fully control. The right choice when you want the radar embedded in your own docs or intranet.
- **[AOEpeople/aoe_technology_radar](https://github.com/AOEpeople/aoe_technology_radar)** — AOE's static-site generator for a full-featured radar with markdown-based blip descriptions and version history. Best option when each blip needs a written rationale, not just a dot on a chart.
- **[Backstage Tech Radar plugin](https://github.com/backstage/community-plugins/tree/main/workspaces/tech-radar)** — The Tech Radar plugin for Spotify's Backstage developer portal, rendering a radar inside the internal platform engineers already use. The natural fit if the company adopts Backstage as its developer portal.

## Guides on Running Your Own Radar

- **[Build Your Own Radar (ThoughtWorks guide)](https://www.thoughtworks.com/radar/byor)** — ThoughtWorks' official guide and toolkit for running an internal radar exercise, including how to facilitate the workshop and interpret results. The canonical starting point for a CTO introducing the practice.
- **[Build Your Own Technology Radar (Neal Ford)](https://nealford.com/memeagora/2013/05/28/build_your_own_technology_radar.html)** — Neal Ford's essay explaining why individuals and companies should maintain a radar, and how to run the exercise as a living document. The best articulation of the *why* behind the practice, for both personal skill strategy and org strategy.
- **[Technology Choices at Zalando: Updating our Tech Radar Process (Zalando Engineering)](https://engineering.zalando.com/posts/2020/07/technology-choices-at-zalando-tech-radar-update.html)** — Zalando's engineering-blog account of how their radar process works and how they evolved its governance (who decides, how often, with what inputs). The most concrete public description of radar operations at scale.
- **[How Zalando uses its own Tech Radar to make better technology choices (LeadDev)](https://leaddev.com/technical-direction/how-zalando-uses-its-own-tech-radar-make-better-technology-choices)** — An outside-in case study of Zalando's radar as a decision-making instrument, from spreadsheet origins to formal process. Useful for pitching the radar internally in business terms rather than tooling terms.
- **[Introducing Tech Radar for Backstage (Backstage blog)](https://backstage.io/blog/2020/05/14/tech-radar-plugin/)** — Spotify's announcement explaining how they use a tech radar inside Backstage, with a central architect committee owning it and engineers contributing input. A working governance model for a radar owned by architecture but fed by the whole org.

## Adjacent Trend Reports

- **[InfoQ Trends Reports](https://www.infoq.com/InfoQ-trends-report/)** — InfoQ's opinionated adoption-curve reports across architecture, AI/ML, DevOps, and culture, written for architects and technical leaders. A useful second opinion to cross-check radar placements against.
- **[ThoughtWorks Looking Glass](https://www.thoughtworks.com/insights/looking-glass)** — ThoughtWorks' annual longer-horizon report on technology lenses shaping business strategy, complementing the Radar's shorter cycle. Feeds the IT-strategy side of the CTO role rather than day-to-day tool choices.
