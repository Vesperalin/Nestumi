---
name: theory
description: Teaches the theory for a given Nestumi roadmap stage or stage-plan step (e.g. "etap 3", "etap 3 krok 3", "3.3", "etap3-plan.md krok 3") in simple Polish, with Nestumi examples, common mistakes and check questions; saves the lecture to a file. Use when the author asks for theory, an explanation or a lecture for a stage or step ("teoria", "wytłumacz", "wykład").
argument-hint: "etap <N> [krok <M>] | <plan-file.md> [krok <M>]"
---

# Theory lecture for a stage / step

**Language: always write the lecture, the questions and all replies in Polish.** These instructions are in English only for the skill itself.

Argument: `$ARGUMENTS` — a stage number and optional step (e.g. `3`, `etap 3 krok 3`, `3.3`) or a path to a plan file and optional step (e.g. `etap3-plan.md krok 3`, `6-8-roadmap.md`). No argument or unclear → ask in one sentence which stage/step is meant.

If a file is given, it is the main source instead of `etap<N>-plan.md`; take the stage number from its content or name. Find the step by a heading starting with "Krok <M>".

## 1. Gather context (read only)

- `docs/roadmap.md` — section `### <N>.` (Zakres, Praktyka, Kryterium ukończenia) and "Materiały odniesienia".
- `etap<N>-plan.md` in the repo root, if it exists — for a given step, section `## Krok <M>.` (goal, **Teoria** item, practice, "gotowe, gdy").
- For examples: `docs/glossary.md`, `docs/decisions.md`, `docs/use-cases.md`, `docs/project-brief.md` — only the fragments you need.

The lecture's scope is the step's **Teoria** item (without a step — the stage's **Zakres**). Don't add topics beyond it; if something from another stage is needed to understand it, mention it in one sentence with the stage number.

## 2. Teach the theory — in Polish, in chat

The reader is a frontend developer (~4 years of experience) learning backend. Simple language, step by step, concrete. Frontend analogies (React, forms, UI state) are welcome when they genuinely help.

Structure (Polish headings):

1. **Po co to jest** — 1–2 sentences: what problem this technique solves in Nestumi.
2. **Pojęcia** — for each concept (max 5 at once; more → split into parts and ask whether to continue):
   - definition in plain language,
   - a Nestumi example based on existing documents (cite the source, e.g. R-043, UC-4, a glossary entry),
   - what the concept is **not** / what it gets confused with.
3. **Typowe błędy** — 2–4 common mistakes on this topic, each with a short counterexample.
4. **Pytania sprawdzające** — 2–3 questions without answers. The author answers first; only then do you assess and add what she missed.
5. **Skąd to wiem** — one line: which files you read and what comes from memory (e.g. a book definition you didn't check now).

## 3. Rules

- **Don't do the step's practice for her.** The lecture must not contain the exercise's finished output (e.g. in the business-rules step, don't list the rules from UC-3). Show an example of finished output on a different domain (e.g. a library, a gym).
- Don't invent new rules or decisions for Nestumi. If an example needs something undecided, mark it "(przykład hipotetyczny)".
- Respect the stage plan's constraints (e.g. in stage 3: no tables, endpoints, architecture or code).
- No schedules or time estimates.
- Don't modify any existing files and don't commit anything.

## 4. Save the lecture to a file

After teaching in chat, save the same content (without answers to the check questions) to:

- `theory/etap-<N>.md` or `theory/etap-<N>-krok-<M>.md`.

File heading: `# Etap <N>[, krok <M>] — <topic in Polish>`. If the file already exists, don't overwrite it without asking — show what will change and wait for approval. Finish by giving the path as a link.
