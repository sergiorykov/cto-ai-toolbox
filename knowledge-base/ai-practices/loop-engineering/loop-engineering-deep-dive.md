---
title: Loop engineering deep dive (articles, preprints, videos)
description: Annotated collection of primary sources, overviews, scientific preprints, videos, and criticism on loop engineering
last_updated: 2026-07-22
approved_by:
approved_when:
---

# Deep Dive: Articles, Preprints, Videos

> Faithful translation of the Russian original [loop-engineering-deep-dive-ru.md](loop-engineering-deep-dive-ru.md)

Split into: (A) originals/primary sources, (B) overview and analytical pieces, (C) scientific preprints,
(D) videos, (E) criticism and debates. Marked where something is a primary source and where it is a retelling.

---

## A. Originals / primary sources

1. **Addy Osmani — "Loop Engineering"** *(primary source, sets the name and the anatomy)*
   https://addyosmani.com/blog/loop-engineering/
   Essay from June 7, 2026. One-line definition + "5 components" (automations, worktrees,
   skills, connectors, sub-agents) + memory.

2. **O'Reilly Radar — "Loop Engineering"** *(republication of Osmani, editorial version)*
   https://www.oreilly.com/radar/loop-engineering/
   Republication from June 22, 2026 — the "canonical" form for a broad audience.

3. **The New Stack — "The Anthropic leader who built Claude Code… now he just writes loops"**
   *(primary record of Boris Cherny's thesis)*
   https://thenewstack.io/loop-engineering/

4. **Paweł Huryn's post with a Boris Cherny quote + 16-min video** *(primary quote)*
   https://x.com/PawelHuryn/status/2069363303952818474
   "I don't prompt Claude anymore. I have loops prompting Claude and figuring what to do."

5. **LinkedIn — Addy Osmani, "Designing Loops for Coding Agents"** *(primary source, short format)*
   https://www.linkedin.com/posts/addyosmani_ai-softwareengineering-programming-activity-7469999258658791425-cTvy

---

## B. Overview and analytical pieces

6. **Gergely Orosz (Pragmatic Engineer) — "What is loop engineering?"** *(high-quality overview + skepticism)*
   https://newsletter.pragmaticengineer.com/p/what-is-loop-engineering
   A breakdown for engineers: what is genuinely new and what is marketing.

7. **TechCrunch — "The AI world is getting 'loopy'"** *(trend overview for a broad audience)*
   https://techcrunch.com/2026/06/22/the-ai-world-is-getting-loopy/

8. **The Neuron — Boris Cherny & Cat Wu explain agent loops** *(explanation from Anthropic practitioners)*
   https://www.theneuron.ai/explainer-articles/claude-code-creators-boris-cherny-and-cat-wu-explain-how-to-use-agent-loops/

9. **Data Science Dojo — "Agentic Loops: From ReAct to Loop Engineering (2026 Guide)"**
   *(overview with historical context from ReAct onward)*
   https://datasciencedojo.com/blog/agentic-loops-explained-from-react-to-loop-engineering-2026-guide/

10. **Firecrawl — "Should You Stop Prompting Agents and Start Designing Loops"** *(balanced overview)*
    https://www.firecrawl.dev/blog/loop-engineering

11. **MindStudio — "What Is Loop Engineering? The New Meta for AI Coding Agents"** *(retelling)*
    https://www.mindstudio.ai/blog/what-is-loop-engineering-ai-coding-agents

12. **ADTmag — "Loop Engineering Emerges as Developers Put AI Coding Agents on Repeat"** *(news overview)*
    https://adtmag.com/articles/2026/07/01/loop-engineering-emerges-as-developers-put-ai-coding-agents-on-repeat.aspx

13. **Adaline Labs — "What Is Loop Engineering, and Who Owns It?"** *(analysis of terminology/authorship)*
    https://labs.adaline.ai/p/what-is-loop-engineering-for-ai-agent

14. **Valentina Alto (Medium) — "Introducing Loop Engineering"** *(retelling + Human-Agents framing)*
    https://valentinaalto.medium.com/introducing-loop-engineering-ac7a6098bb10

---

## C. Scientific preprints (arXiv) — working theses, not peer-reviewed

15. **"Stop Hand-Holding Your Coding Agent: Engineering the Loops that Replace Step-by-Step
    Prompting"** — arXiv:2607.00038 *(key academic analysis of the term)*
    https://arxiv.org/abs/2607.00038
    Defines the **loop specification** (trigger, goal, verification, stopping rule, memory);
    a 5-level "verification ladder"; analysis of a Loop Library of 50 real loops; design
    principles and anti-patterns (self-correction, reward hacking, model-as-judge fragility).

16. **"From Question Answering to Task Completion: A Survey on Agent System and Harness Design"**
    — arXiv:2606.20683 *(survey of the adjacent harness discipline)*
    https://arxiv.org/pdf/2606.20683

17. **"Supervising Ralph Wiggum: A Metacognitive Co-Regulation Agentic AI Loop for Engineering
    Design"** — arXiv:2603.24768 *(loops in engineering design)*
    https://arxiv.org/pdf/2603.24768

18. **"Closing the Auto-Research Loop: An AI Co-Scientist for Production Search Ranking"**
    — arXiv:2603.22376 *(autonomous research loops in production)*
    https://arxiv.org/pdf/2603.22376

> Related on verification risks: "Detecting and Suppressing Reward Hacking with Gradient
> Fingerprints" (arXiv:2604.16242); "Is It Thinking or Cheating? Detecting Implicit Reward
> Hacking…" (arXiv:2510.01367). Useful for the section on reward hacking in loops.

---

## D. Videos

19. **Boris Cherny — 16-minute breakdown of loops** (via Paweł Huryn's post, X)
    https://x.com/PawelHuryn/status/2069363303952818474
    Primary talk by the creator of Claude Code: "my job is writing loops."

20. **"Loop Engineering by Addy Osmani" (YouTube)**
    https://www.youtube.com/watch?v=7etFXmu9rvU

21. **"Loop Engineering: The Complete Landscape (2026)" (YouTube)**
    https://www.youtube.com/watch?v=h_YzyDMgZxM

22. **"Understanding Loop Engineering" (YouTube)**
    https://www.youtube.com/watch?v=bcY3oCj0A9o

23. **"I tried loop engineering, we need to talk..." (YouTube)** *(hands-on experience/criticism)*
    https://www.youtube.com/watch?v=Q1tgkuCcQBo

> Note: videos #20–23 are secondary (explainers/experience reports), except #19. The links are
> worth opening and checking for currency — some channels retell Osmani's essay.

---

## E. Criticism and debates

24. **Agent Autopsies — "Loopmaxxing: Your AI Loop Isn't Improving Anything. It's Laundering
    Confidence."** *(strong criticism of self-approving loops)*
    https://agentautopsies.substack.com/p/loopmaxxing

25. **BD TechTalks — "Demystifying loop engineering: get more from AI agents, avoid loopmaxxing"**
    https://bdtechtalks.com/2026/06/22/ai-loop-engineering/

26. **Memeburn — "Boris Cherny Says Loop Engineering Has Replaced Prompting"** *(popular retelling)*
    https://memeburn.com/boris-cherny-says-loop-engineering-has-replaced-prompting/

The critics' main theses: (1) a "loop" may be a temporary crutch until the harness improves
(Max Kanat-Alexander); (2) without an independent verifier, a loop merely "launders confidence";
(3) economics: at API prices, cost grows faster than value if verification is expensive/fuzzy.

---

## How to read this collection (recommended order)

1. Start with **#1 (Osmani)** and **#3/#19 (Cherny)** — to understand the primary source.
2. Then **#6 (Orosz)** — a sober engineering breakdown.
3. For depth — **#15 (arXiv 2607.00038)**: the only text with a formal anatomy and
   anti-patterns.
4. For balance — **#24 (Loopmaxxing)**: so as not to buy into the hype.

## References

Links already mentioned in the text above (no new sources):

- https://addyosmani.com/blog/loop-engineering/
- https://www.oreilly.com/radar/loop-engineering/
- https://thenewstack.io/loop-engineering/
- https://x.com/PawelHuryn/status/2069363303952818474
- https://www.linkedin.com/posts/addyosmani_ai-softwareengineering-programming-activity-7469999258658791425-cTvy
- https://newsletter.pragmaticengineer.com/p/what-is-loop-engineering
- https://techcrunch.com/2026/06/22/the-ai-world-is-getting-loopy/
- https://www.theneuron.ai/explainer-articles/claude-code-creators-boris-cherny-and-cat-wu-explain-how-to-use-agent-loops/
- https://datasciencedojo.com/blog/agentic-loops-explained-from-react-to-loop-engineering-2026-guide/
- https://www.firecrawl.dev/blog/loop-engineering
- https://www.mindstudio.ai/blog/what-is-loop-engineering-ai-coding-agents
- https://adtmag.com/articles/2026/07/01/loop-engineering-emerges-as-developers-put-ai-coding-agents-on-repeat.aspx
- https://labs.adaline.ai/p/what-is-loop-engineering-for-ai-agent
- https://valentinaalto.medium.com/introducing-loop-engineering-ac7a6098bb10
- https://arxiv.org/abs/2607.00038
- https://arxiv.org/pdf/2606.20683
- https://arxiv.org/pdf/2603.24768
- https://arxiv.org/pdf/2603.22376
- https://www.youtube.com/watch?v=7etFXmu9rvU
- https://www.youtube.com/watch?v=h_YzyDMgZxM
- https://www.youtube.com/watch?v=bcY3oCj0A9o
- https://www.youtube.com/watch?v=Q1tgkuCcQBo
- https://agentautopsies.substack.com/p/loopmaxxing
- https://bdtechtalks.com/2026/06/22/ai-loop-engineering/
- https://memeburn.com/boris-cherny-says-loop-engineering-has-replaced-prompting/
