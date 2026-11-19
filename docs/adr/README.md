# Architecture decisions

Why the system is built the way it is.

## Index

| # | Title | Status | Date |
|---|---|---|---|
| [0001](0001-record-architecture-decisions.md) | Record architecture decisions | Accepted | <YYYY-MM-DD> |

Statuses: **Proposed** → **Accepted** → **Superseded by #NNNN** / **Deprecated**.

Keep the status column honest. Agents read this table as the current state of
the world, and an entry still marked Accepted six months after reality moved on
gets cited confidently and wrongly.

## When to write one

When the decision would be expensive to reverse, when it constrains future
work, or when you will later ask yourself why on earth it is like this.

Skip it for choices that are cheap to change. The log is useful in proportion
to its signal.

## Rules

- **Accepted ADRs are immutable.** Do not edit the decision or the context.
  Write a new ADR that supersedes the old one and update both index rows.
- **Supersession links both ways.** The new one names what it replaces, the old
  one names what replaced it.
- **Numbers are permanent.** A withdrawn ADR keeps its number and stays in the
  folder. Gaps in a renumbered log are how history gets lost.

## Keeping it true

There is no review meeting here — one person does not hold a cadence with
themselves. Check instead at the moment it matters: before building on a
decision more than a few months old, confirm it still holds.

An ADR nothing links to is usually missing from this index.
