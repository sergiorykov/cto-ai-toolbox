---
title: Предыстория loop engineering — имена, статьи, репозитории
description: Хронология появления термина «loop engineering», ключевые люди, первоисточники и репозитории
last_updated: 2026-07-22
approved_by:
approved_when:
---

# Предыстория: имена, статьи, репозитории

> [en: loop-engineering-history.md](../loop-engineering-history.md)

## Как появился термин (хронология)

Термин выкристаллизовался за несколько дней в начале июня 2026 года — три голоса из разных
углов мира ИИ-кодинга почти одновременно сформулировали одну идею.

- **~6–7 июня 2026** — **Peter Steinberger** (создатель OpenClaw, самого «зазвёзженного»
  нового репозитория в истории GitHub на тот момент) публикует пост: «Вы больше не должны
  промптить кодинг-агентов — вы должны проектировать петли, которые промптят ваших агентов».
  Пост набрал ~5 млн просмотров менее чем за сутки.
- **7 июня 2026** — **Addy Osmani** (инженерный лид Google Chrome) на следующий день даёт
  практике имя и структуру в эссе **«Loop Engineering»** на addyosmani.com. Позже (22 июня)
  переопубликовано в O'Reilly Radar.
- **Тогда же** — **Boris Cherny** (глава Claude Code в Anthropic) изнутри формулирует то же
  самое: «Я больше не промптлю Claude. У меня крутятся петли, которые промптят Claude и решают,
  что делать. Моя работа — писать петли». Тезис прозвучал в его выступлении (в т.ч. на
  конференции Meta @Scale).

Итог: **Steinberger** дал провокацию, **Osmani** дал имя и анатомию, **Cherny** дал
подтверждение «изнутри» лаборатории. Дальше термин подхватили O'Reilly, TechCrunch, The New
Stack, Pragmatic Engineer и десятки блогов.

## Ключевые люди

| Имя | Роль | Вклад в термин |
|-----|------|----------------|
| **Peter Steinberger** | Создатель OpenClaw, ex-PSPDFKit/Nutrient | Провокация «stop prompting, design loops»; вирусный пост-триггер |
| **Addy Osmani** | Eng lead, Google Chrome; автор O'Reilly | Назвал и структурировал практику; «5 компонентов» петли |
| **Boris Cherny** | Глава Claude Code, Anthropic | «Я пишу не промпты, а петли»; валидация из индустрии |
| **Cat Wu** | Продукт Claude Code, Anthropic | Совместные разъяснения агентных петель (The Neuron) |
| **Gergely Orosz** | Pragmatic Engineer | Разбор/критический обзор термина для широкой инженерной аудитории |
| **Max Kanat-Alexander** | Distinguished engineer | Скептик: «петля» может оказаться временным хаком до улучшения harness |

## Первоисточники (оригиналы)

- Addy Osmani — «Loop Engineering» (личный блог): https://addyosmani.com/blog/loop-engineering/
- Addy Osmani в O'Reilly Radar: https://www.oreilly.com/radar/loop-engineering/
- Addy Osmani (Substack «Elevate»): https://addyo.substack.com/p/loop-engineering
- The New Stack — заявление Boris Cherny: https://thenewstack.io/loop-engineering/
- Пост Paweł Huryn с цитатой и 16-мин видео Cherny (X): https://x.com/PawelHuryn/status/2069363303952818474
- LinkedIn-пост Addy Osmani «Designing Loops for Coding Agents»: https://www.linkedin.com/posts/addyosmani_ai-softwareengineering-programming-activity-7469999258658791425-cTvy

## Репозитории (GitHub)

| Репозиторий | Что даёт |
|-------------|----------|
| [cobusgreyling/loop-engineering](https://github.com/cobusgreyling/loop-engineering) | Паттерны, стартеры и CLI (`loop-audit`, `loop-init`, `loop-cost`); вдохновлён Osmani и Cherny |
| [dlmastery/loop_engineer](https://github.com/dlmastery/loop_engineer) | Skill-pack для Claude Code: self-prompting петли (автоматизации, worktrees, память, сабагенты, коннекторы) + шаблоны |
| [ChaoYue0307/awesome-loop-engineering](https://github.com/ChaoYue0307/awesome-loop-engineering) | Curated field guide: отделяет loop engineering от prompt/context/harness engineering; loop contracts, примеры |
| [AI-Builder-Club/loop-engineer-template](https://github.com/AI-Builder-Club/loop-engineer-template) | Стартовый шаблон «loop engineer»-агента: триггерится сам, берёт работу, верифицирует, логирует |
| [walkinglabs/learn-harness-engineering](https://github.com/walkinglabs/learn-harness-engineering) | Туториал по harness engineering «от 0 до 1» (смежная дисциплина) |
| [github.com/topics/agent-loops](https://github.com/topics/agent-loops) | Тег-хаб смежных проектов |

## Термин в контексте эволюции навыков

Prompt engineering (2023) → context engineering (2024–25) → **loop engineering / harness
engineering (2026)**. Идея: узкое место сместилось с *формулировки промпта* на *дизайн петли* —
триггер, топология, верификатор и правила остановки, которые решают, что агент делает дальше и
когда останавливается.

## Источники

- https://valentinaalto.medium.com/introducing-loop-engineering-ac7a6098bb10
- https://addyosmani.com/blog/loop-engineering/
- https://www.oreilly.com/radar/loop-engineering/
- https://thenewstack.io/loop-engineering/
- https://newsletter.pragmaticengineer.com/p/what-is-loop-engineering
- https://x.com/PawelHuryn/status/2069363303952818474
