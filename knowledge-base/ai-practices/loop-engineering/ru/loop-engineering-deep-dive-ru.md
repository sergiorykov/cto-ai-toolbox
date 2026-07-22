---
title: Loop engineering — глубокий разрез (статьи, препринты, видео)
description: Аннотированная подборка первоисточников, обзоров, научных препринтов, видео и критики по loop engineering
last_updated: 2026-07-22
approved_by:
approved_when:
---

# Глубокий разрез: статьи, препринты, видео

> [en: loop-engineering-deep-dive.md](../loop-engineering-deep-dive.md)

Разбито на: (A) оригиналы/первоисточники, (B) обзорные и аналитические, (C) научные препринты,
(D) видео, (E) критика и споры. Помечено, где первоисточник, где пересказ.

---

## A. Оригиналы / первоисточники

1. **Addy Osmani — «Loop Engineering»** *(первоисточник, задаёт имя и анатомию)*
   https://addyosmani.com/blog/loop-engineering/
   Эссе от 7 июня 2026. Определение в одну строку + «5 компонентов» (automations, worktrees,
   skills, connectors, sub-agents) + memory.

2. **O'Reilly Radar — «Loop Engineering»** *(републикация Osmani, редакторская версия)*
   https://www.oreilly.com/radar/loop-engineering/
   Републикация от 22 июня 2026 — «канонический» вид для широкой аудитории.

3. **The New Stack — «The Anthropic leader who built Claude Code… now he just writes loops»**
   *(первичная фиксация тезиса Boris Cherny)*
   https://thenewstack.io/loop-engineering/

4. **Пост Paweł Huryn с цитатой Boris Cherny + 16-мин видео** *(первичная цитата)*
   https://x.com/PawelHuryn/status/2069363303952818474
   «I don't prompt Claude anymore. I have loops prompting Claude and figuring what to do.»

5. **LinkedIn — Addy Osmani, «Designing Loops for Coding Agents»** *(первоисточник, короткий формат)*
   https://www.linkedin.com/posts/addyosmani_ai-softwareengineering-programming-activity-7469999258658791425-cTvy

---

## B. Обзорные и аналитические

6. **Gergely Orosz (Pragmatic Engineer) — «What is loop engineering?»** *(качественный обзор + скепсис)*
   https://newsletter.pragmaticengineer.com/p/what-is-loop-engineering
   Разбор для инженеров: что реально нового, а что маркетинг.

7. **TechCrunch — «The AI world is getting 'loopy'»** *(обзор тренда для широкой аудитории)*
   https://techcrunch.com/2026/06/22/the-ai-world-is-getting-loopy/

8. **The Neuron — Boris Cherny & Cat Wu объясняют agent loops** *(разъяснение от практиков Anthropic)*
   https://www.theneuron.ai/explainer-articles/claude-code-creators-boris-cherny-and-cat-wu-explain-how-to-use-agent-loops/

9. **Data Science Dojo — «Agentic Loops: From ReAct to Loop Engineering (2026 Guide)»**
   *(обзор с историческим контекстом от ReAct)*
   https://datasciencedojo.com/blog/agentic-loops-explained-from-react-to-loop-engineering-2026-guide/

10. **Firecrawl — «Should You Stop Prompting Agents and Start Designing Loops»** *(взвешенный обзор)*
    https://www.firecrawl.dev/blog/loop-engineering

11. **MindStudio — «What Is Loop Engineering? The New Meta for AI Coding Agents»** *(пересказ)*
    https://www.mindstudio.ai/blog/what-is-loop-engineering-ai-coding-agents

12. **ADTmag — «Loop Engineering Emerges as Developers Put AI Coding Agents on Repeat»** *(новостной обзор)*
    https://adtmag.com/articles/2026/07/01/loop-engineering-emerges-as-developers-put-ai-coding-agents-on-repeat.aspx

13. **Adaline Labs — «What Is Loop Engineering, and Who Owns It?»** *(разбор терминологии/авторства)*
    https://labs.adaline.ai/p/what-is-loop-engineering-for-ai-agent

14. **Valentina Alto (Medium) — «Introducing Loop Engineering»** *(пересказ + Human-Agents рамка)*
    https://valentinaalto.medium.com/introducing-loop-engineering-ac7a6098bb10

---

## C. Научные препринты (arXiv) — рабочие тезисы, не рецензировано

15. **«Stop Hand-Holding Your Coding Agent: Engineering the Loops that Replace Step-by-Step
    Prompting»** — arXiv:2607.00038 *(ключевой академический разбор термина)*
    https://arxiv.org/abs/2607.00038
    Определяет **loop specification** (триггер, цель, верификация, правило остановки, память);
    5-уровневая «лестница верификации»; анализ Loop Library из 50 реальных петель; принципы
    дизайна и анти-паттерны (self-correction, reward hacking, model-as-judge fragility).

16. **«From Question Answering to Task Completion: A Survey on Agent System and Harness Design»**
    — arXiv:2606.20683 *(обзор смежной harness-дисциплины)*
    https://arxiv.org/pdf/2606.20683

17. **«Supervising Ralph Wiggum: A Metacognitive Co-Regulation Agentic AI Loop for Engineering
    Design»** — arXiv:2603.24768 *(петли в инженерном проектировании)*
    https://arxiv.org/pdf/2603.24768

18. **«Closing the Auto-Research Loop: An AI Co-Scientist for Production Search Ranking»**
    — arXiv:2603.22376 *(автономные research-петли в проде)*
    https://arxiv.org/pdf/2603.22376

> Смежное по рискам верификации: «Detecting and Suppressing Reward Hacking with Gradient
> Fingerprints» (arXiv:2604.16242); «Is It Thinking or Cheating? Detecting Implicit Reward
> Hacking…» (arXiv:2510.01367). Полезно для раздела о reward hacking в петлях.

---

## D. Видео

19. **Boris Cherny — 16-минутный разбор петель** (через пост Paweł Huryn, X)
    https://x.com/PawelHuryn/status/2069363303952818474
    Первичное выступление автора Claude Code: «моя работа — писать петли».

20. **«Loop Engineering by Addy Osmani» (YouTube)**
    https://www.youtube.com/watch?v=7etFXmu9rvU

21. **«Loop Engineering: The Complete Landscape (2026)» (YouTube)**
    https://www.youtube.com/watch?v=h_YzyDMgZxM

22. **«Understanding Loop Engineering» (YouTube)**
    https://www.youtube.com/watch?v=bcY3oCj0A9o

23. **«I tried loop engineering, we need to talk...» (YouTube)** *(практический опыт/критика)*
    https://www.youtube.com/watch?v=Q1tgkuCcQBo

> Примечание: видео #20–23 — вторичные (объяснялки/опыт), кроме #19. Ссылки стоит открыть и
> сверить актуальность — часть каналов пересказывает эссе Osmani.

---

## E. Критика и споры

24. **Agent Autopsies — «Loopmaxxing: Your AI Loop Isn't Improving Anything. It's Laundering
    Confidence.»** *(сильная критика self-approving петель)*
    https://agentautopsies.substack.com/p/loopmaxxing

25. **BD TechTalks — «Demystifying loop engineering: get more from AI agents, avoid loopmaxxing»**
    https://bdtechtalks.com/2026/06/22/ai-loop-engineering/

26. **Memeburn — «Boris Cherny Says Loop Engineering Has Replaced Prompting»** *(популярный пересказ)*
    https://memeburn.com/boris-cherny-says-loop-engineering-has-replaced-prompting/

Основные тезисы критиков: (1) «петля» может быть временным костылём до улучшения harness
(Max Kanat-Alexander); (2) без независимого верификатора петля лишь «отмывает уверенность»;
(3) экономика: по API-ценам стоимость растёт быстрее пользы, если верификация дорогая/размытая.

---

## Как читать эту подборку (рекомендованный порядок)

1. Начать с **#1 (Osmani)** и **#3/#19 (Cherny)** — понять первоисточник.
2. Затем **#6 (Orosz)** — трезвый инженерный разбор.
3. Для глубины — **#15 (arXiv 2607.00038)**: единственный текст с формальной анатомией и
   анти-паттернами.
4. Для баланса — **#24 (Loopmaxxing)**: чтобы не купиться на хайп.

## Дополнительные ресурсы

Ссылки, уже упомянутые в тексте выше (без новых источников):

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
