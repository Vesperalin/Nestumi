# Nestumi

A booking platform for mental health and wellbeing services: find a specialist, compare offers, book a 1:1 session and manage it.

> **Status: domain modeling.** No application code yet. The project starts with requirements, a domain model and recorded decisions; implementation comes after the database design.

## Why this project

I'm a frontend developer (~4 years) growing into fullstack. Nestumi is my own product, with no client and no deadline, built to practise the parts of fullstack work that matter most to me: domain modeling, relational data, consistency under concurrency, and deliberate design decisions.

## What v1 does

- **Providers** create professional profiles, publish offers (service type, price, duration, buffer after the session, online/in-person) and set availability for specific weeks.
- **Visitors** browse the catalog without an account: filters, pagination, free slots.
- **Users** book a slot (confirmed automatically if the whole session still fits) and can view or cancel their bookings. Both sides see their sessions; history is kept after cancellation.
- Psychological and psychiatric help is clearly separated from wellbeing practices (yoga, meditation, breathwork, massage), even when one person offers both.

## The interesting parts

- **Shared busy-time across all offers of one person.** Sessions can't overlap across different offers and profiles, including the buffer after each session and bookings where the provider is a participant themselves.
- **The full duration has to fit.** A 120-minute session needs 120 free minutes, not just a free start time.
- **Concurrent bookings and retries.** Two people booking the same slot, a double-click or a retried request after a network error must not create a second booking.
- **Schedule changes vs. existing bookings.** Copying or editing availability must respect sessions already booked.

## Planned stack

Node.js, TypeScript, Express, PostgreSQL; React on the frontend. A modular monolith with one database to start. The final choice (router, data fetching, validation, migrations) will be recorded in an ADR before the skeleton is built.

## How I work

Concept → my own proposal → critique → experiment → verification → short decision record.

I use Claude Code as a reviewer, tutor and sparring partner, configured with project skills in [.claude/skills/](.claude/skills/). I draft models, rules and test expectations myself first; AI looks for counterexamples and gaps.

## Documentation (in Polish)

| File | Contents |
| --- | --- |
| [project-brief.md](docs/project-brief.md) | Problem, users, v1 scope, simplifications, risks |
| [glossary.md](docs/glossary.md) | Ubiquitous language of the domain |
| [use-cases.md](docs/use-cases.md) | Key flows: booking, cancellation, setting availability |
| [decisions.md](docs/decisions.md) | Decision log: decisions, assumptions, open questions |
| [roadmap.md](docs/roadmap.md) | Learning roadmap: from domain modeling to deployment, performance and real-time |
