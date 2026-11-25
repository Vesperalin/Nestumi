---
name: review-business-rules
description: Reviews the author's Nestumi domain-modeling work — business rules, examples and questions on the FigJam board, and edits to docs/glossary.md, docs/use-cases.md, docs/decisions.md — against the project docs. Every finding is backed by a file:line source, ranked by impact, with no gap-filling by analogy and no nitpicking. Use when she asks to check, review or verify her rules, examples, cards, board section or doc edits ("sprawdź", "przeanalizuj", "zweryfikuj", "co o tym myślisz").
argument-hint: "<FigJam URL or section name> | <doc path> | (empty = what changed since last check)"
---

# Review business rules

**Language: all replies in Polish.** These instructions are in English only for the skill itself.

Argument: `$ARGUMENTS` — a FigJam URL / board section (e.g. `UC-3`), a doc path, or nothing. Nothing → review what changed: the board section discussed last, or `git diff` of `docs/`. Unclear → ask in one sentence.

## 1. Read the work

- **FigJam board** (fileKey `VNYO13p0i2DKWXxfX22uXN`, server `figma-nestumi`): if the board is open in Chrome DevTools, read (and edit) through `evaluate_script` with `window.figma` — the Figma MCP has a call limit on her plan. Otherwise `get_figjam` on the section node. Read it in columns by x position: blue rule on top, then green / violet / red / white under it. Colors: blue = rule, green = example that complies, violet = violation, red = open question, white = her answer to a question.
- **Docs:** `git diff docs/` to see exactly what she changed; then read the changed entries in full.

## 2. Read only the sources you need

For every term, decision or use case the work touches, read its exact text: `docs/glossary.md` (entry + the ambiguous-words table), `docs/decisions.md` (the R-xxx entry, not just its title), `docs/use-cases.md` (the UC's steps and extensions). Don't rely on memory of a decision — reread it.

## 3. Check

**Rule card (blue)**
- One sentence, one rule. Two checks with separate extensions = two rules.
- Uses glossary terms; no word from the ambiguous-words table (e.g. "potwierdzenie", "zatwierdzenie", "dostępny", "przedział" in a non-glossary sense). Compare every card word by word against the table's first column — also cards checked in earlier rounds.
- Type fits: invariant passes the photo test (true at any moment); operation condition is checked at an attempt; policy has a real business alternative. The photo test applies only to invariants.
- **Skutek reguły:** an outcome line of the UC that follows from an existing rule or glossary definition (e.g. "after cancelling the time is free" follows from Zajętość = active reservations only) is not a new card. It goes as an example under that source rule. Before calling a card a policy, name the alternative another business could reasonably choose; none → it's an invariant or a skutek.
- Doesn't contradict glossary or R-xxx. Isn't a flow step or UI description.

**Example (green / violet)**
- Concrete: who, what offer, when. Shape: state → attempt → outcome, outcome in business terms ("rezerwacja powstaje", not "może").
- Each green tests something different from the others on the same rule.
- Violet actually reaches the rule (the person can attempt it) and states what the system does.
- **Color ≠ outcome.** Color says whether the rule holds at the moment of the attempt (broken → violet). The outcome comes from the UC extension and can be a success (e.g. UC-4 "already cancelled" ends in success). Every finding names which part to change: color, state, attempt or outcome.
- Before suggesting a path to a violation, check who and what state the system sees then (someone logged in as Ola *is* Ola). If no business path reaches the violation, say so — a note on the card ("brak osiągalnego naruszenia, bo …") is a valid result.
- **The outcome's reason matches this rule.** Don't borrow another decision's outcome because the effect looks similar (lesson: R-037 is about a slot that stopped being free, not about a withdrawn offer).

**Question (red) / answer (white)**
- Not already answered in docs — if it is, point to the R-xxx.
- A white answer that no doc covers is a new decision: say which UC it belongs to and that it must reach `docs/decisions.md` (or extends an existing R-xxx).

**Doc edits**
- Consistent with the other entries in the same file.
- Grep other `.md` files for the changed terms; report places that became wrong (not places that were merely imprecise before).

**Coverage** (only when she asks whether she found everything): map preconditions, outcome lines, checking steps and extensions of the UC to cards; list what has no card. When a card is removed or treated as a skutek, find its source rule on the board (other sections too) and check it says the same (e.g. "aktywna").

## 4. Verify before reporting

- Every finding cites its source as a clickable `file:line` link, or quotes the card.
- One finding = one card, checked against that card. No "to samo dotyczy kart X i Y" without checking each.
- If no doc covers the case, it is a **question**, not a finding. Never fill a gap by analogy.
- Drop any finding you can't back with a source.
- Drop points she already decided: if she kept her version after one remark earlier in the conversation, it's her decision — don't raise it again.

## 5. Report — in Polish, in this order

1. **W porządku** — one line listing what passed.
2. **Zmienia sens** — only things that produce a wrong rule, a contradiction with docs, or a card that can't be tested. For each: what, why (source), and a question with a heuristic ("dwa naraz", "zmieni się później", "ta sama osoba w dwóch rolach", "granica", "zero/brak/dużo", "ktoś się pomyli", "kto to widzi") — not a finished replacement.
3. **Drobiazgi** — at most 2 (typos, wording). Skip the section if none matter.
4. **Czego nie sprawdziłem** — one line: what you didn't read or what comes from memory.

No section → omit it. No closing summary.

## 6. Rules

- **Read only.** Don't edit the board or files unless she asks for that specific change. "Popraw drobiazgi / literówki" = typos, spaces, swapping a word for its glossary term. Anything that changes meaning → ask first. She edits the board in parallel: reread a card right before editing it.
- **Question-first:** for missing or wrong items give the question + heuristic, not the answer. Exceptions: she explicitly asks for a ready version — then mark every assumption on the card itself; she says she's stuck or asks what you propose ("nie wiem", "co proponujesz") — give one recommendation with its reason.
- Stage 3 scope: no tables, endpoints, architecture, code or screens. "Dokąd przechodzi" / "co klika" is UI — keep only the business part.
- Refer to the author as "ona".
