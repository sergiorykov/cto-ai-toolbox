---
requires_approve: true
last_updated: 2026-07-22
---

# Engineering Principles & Handbooks of Large Companies

Curated, verified public engineering principles, culture docs, and handbooks from Google, Amazon, Netflix, Spotify, GitLab, Basecamp, Stripe, Shopify, Microsoft, Meta and others, plus aggregators of engineering blogs and postmortems.

## Google

- **[Google Engineering Practices](https://github.com/google/eng-practices)** — Google's public documentation of how they do code review, from both the reviewer's and the author's side. The canonical reference to steal from when calibrating review standards and "how good is good enough" across teams.
- **[Google SRE Books](https://sre.google/books/)** — The full SRE canon (Site Reliability Engineering, The SRE Workbook, Building Secure and Reliable Systems) free to read online. Source of SLOs, error budgets, and toil elimination — the vocabulary for any conversation about reliability vs. feature velocity trade-offs.
- **[Software Engineering at Google](https://abseil.io/resources/swe-book)** — The "Flamingo book," free online: how Google approaches engineering as a function of time, scale, and trade-offs — culture, processes, and tooling. Dense with transferable policy patterns (deprecation, testing culture, large-scale changes).
- **[Google Style Guides](https://google.github.io/styleguide/)** — Google's public per-language style guides. Useful less for the specifics than as a template for ending style debates by adopting an authoritative external standard.
- **[Google Testing Blog](https://testing.googleblog.com/)** — Long-running blog on testing culture and practice at Google scale ("Testing on the Toilet" and friends). Practical ammunition for building a testing culture without a dedicated QA army.

## Amazon & AWS

- **[Amazon Leadership Principles](https://www.amazon.jobs/content/en/our-workplace/leadership-principles)** — The official 16 leadership principles that function as Amazon's actual decision-making and hiring OS, not wall art. A reference model for turning values into operational mechanisms (bar raisers, disagree-and-commit).
- **[Working Backwards](https://www.workingbackwards.com/)** — Official site for the book by Colin Bryar and Bill Carr (long-time Amazon executives) describing Amazon's inner mechanisms: PR/FAQ, six-page narratives, single-threaded leaders, input metrics. The best documented bridge between product discovery and engineering execution.
- **[Stevey's Google Platforms Rant](https://gist.github.com/chitchcock/1281611)** — Steve Yegge's famous accidentally-public 2011 memo containing the firsthand account of Bezos's "API mandate" that forced Amazon onto service interfaces and enabled AWS. The seminal text on platform thinking and Conway's law applied deliberately.
- **[The Amazon Builders' Library](https://aws.amazon.com/builders-library/)** — Articles by senior AWS principal engineers on how Amazon actually builds and operates distributed systems (timeouts, retries, cell-based architecture, operational readiness). Rare staff-plus-level depth published under a company's name.
- **[AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)** — AWS's official framework of pillars (operational excellence, security, reliability, performance, cost, sustainability) with review questions. Works as a ready-made architecture review checklist even for non-AWS estates.

## Netflix & Spotify

- **[Netflix Culture Memo](https://jobs.netflix.com/culture)** — The current official version of the famous culture deck: talent density, candor, "context not control," and the keeper test. The reference point for high-freedom/high-responsibility org design and its costs.
- **[Netflix TechBlog](https://netflixtechblog.com/)** — Netflix's engineering blog: chaos engineering, resilience, data platform, and the operational reality behind the culture memo. Consistently high signal on running systems at scale with small autonomous teams.
- **[Spotify Engineering Culture (Part 1)](https://engineering.atspotify.com/2014/03/spotify-engineering-culture-part-1)** — The original 2014 Kniberg/Ivarsson video and post on squads, tribes, chapters, and guilds, hosted on Spotify's own engineering blog. Read as a primary source — including to understand why the copy-pasted "Spotify Model" fails elsewhere (Spotify itself moved on).

## Company Handbooks (GitLab, Basecamp, Valve)

- **[The GitLab Handbook](https://handbook.gitlab.com/)** — The largest public company handbook in existence (thousands of pages): engineering, product, people, finance, all-remote operations. A living reference for handbook-first management and for lifting concrete policies (grades, comp calculator philosophy, meeting hygiene) wholesale.
- **[Shape Up](https://basecamp.com/shapeup)** — Basecamp/37signals' free book on their product development method: shaping, betting, six-week cycles, appetite over estimates. The strongest coherent alternative to Scrum/SAFe-style planning, directly relevant to PI-planning discussions.
- **[Getting Real](https://basecamp.com/gettingreal)** — 37signals' earlier free book on building web products lean: less mass, fixed scope, launch early. Dated in places but still the clearest articulation of small-team product pragmatism.
- **[Valve Handbook for New Employees](https://www.valvesoftware.com/en/publications)** — Valve's official publications page including the famous 2012 handbook describing a flat, self-allocating organization ("desks have wheels"). The extreme end of the org-design spectrum — valuable as a boundary case, with well-documented failure modes.

## Engineering Blogs & Playbooks (Stripe, Shopify, Microsoft, Meta)

- **[Stripe Engineering Blog](https://stripe.com/blog/engineering)** — Stripe's official engineering channel: API design, reliability, migrations, and developer productivity from the company that set the bar for API craftsmanship. (Their Increment magazine is discontinued but archives are linked from here.)
- **[Shopify Engineering](https://shopify.engineering/)** — Shopify's engineering blog: modular monolith at extreme scale, flash-sale capacity engineering, and developer experience investment. One of the best public records of scaling a Rails monolith instead of defaulting to microservices.
- **[Microsoft Code With Engineering Playbook](https://microsoft.github.io/code-with-engineering-playbook/)** — The public playbook of Microsoft's ISE (Industry Solutions Engineering) org: concrete checklists for agile ceremonies, code reviews, CI/CD, observability, and security when engineering alongside customers. Immediately reusable as a delivery baseline for consulting-style or platform teams.
- **[Engineering at Meta](https://engineering.fb.com/)** — Meta's official engineering blog: infrastructure at billions-of-users scale, open source (React, PyTorch), and production engineering culture. Best sampled for deep dives on systems your teams are about to hit a smaller version of.

## Aggregators & Postmortems

- **[kilimchoi/engineering-blogs](https://github.com/kilimchoi/engineering-blogs)** — The canonical curated list of hundreds of company and individual engineering blogs, with an OPML file for one-shot RSS import. The single best entry point for building a company-engineering-blog reading pipeline.
- **[danluu/post-mortems](https://github.com/danluu/post-mortems)** — Dan Luu's curated collection of public postmortems from AWS, Google, Cloudflare, GitLab and many others. Raw material for incident-review culture, risk conversations, and "this happened to them, here's our exposure" arguments.
