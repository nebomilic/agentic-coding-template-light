---
name: grill-me
description: Interview the user one question at a time until an idea, a plan or a technical decision is pinned down well enough to write a PRD or an ADR. Use before any work starts. Triggers on "grill me", "stress-test this", "interrogate this idea".
---

# Grill me

Flip the direction of the conversation. The user stops explaining and starts
answering.

Adapted from Matt Pocock's `grill-me` (MIT, github.com/mattpocock/skills) and
narrowed to this repository's PRD and ADR conventions.

## Before the first question

Read `docs/adr/README.md` and any PRD the idea touches. Grilling the user about
something they already settled and wrote down wastes the one resource this
repository is built to protect.

## How to run it

1. Restate the idea in two sentences. If you cannot, that is the first
   question.
2. Ask **one** question and stop. Not a numbered list, not a form. One.
3. Ask the question whose answer changes the most of the remaining ones. Order
   by leverage, not by document section.
4. Challenge rather than collect. When an answer is vague, contradicts an
   earlier one, or contradicts an accepted ADR, say so and ask again.
5. Write no code and create no files until the grilling ends.

## What to dig at

- The problem, and who actually has it. Whether that is observed or assumed.
- What becomes true when this is done, stated from the user's side.
- What is deliberately out of scope. Keep pushing here; this is the section
  that pays off and the one people skip.
- The unhappy paths. Empty, slow, offline, denied, already exists.
- Which decision here is expensive to reverse, and what the alternatives were.
- What already exists that this touches.
- The user-visible decision hiding inside a technical one.

## When to stop

When the problem, the outcome, the out-of-scope list and the one decision that
matters can all be stated without guessing. Or when the user says enough.

Do not keep grilling for completeness. An interrogation that outlasts its
usefulness gets skipped next time.

## Handing off

End with the decisions reached and the questions still open, both short.

Then offer, and only on request:

- a **PRD** draft, using `docs/prd/TEMPLATE.md`. Print it in the conversation.
  `docs/prd/` is write-blocked and stays that way; the user commits it.
- an **ADR**, using `docs/adr/TEMPLATE.md`, written to `docs/adr/` and added to
  the index.

Unresolved questions go in the PRD's open questions table, not into the code as
an assumption.
