# ADR-0001: Record architecture decisions

- **Status:** Accepted
- **Date:** <YYYY-MM-DD>
- **Related:** —

## Context

Technical decisions get made in conversations with an agent and in the moment
of writing the code. Within weeks the reasoning is gone and only the outcome
remains. The code shows *what* it does and never *why*, so settled questions
get re-opened and constraints chosen deliberately start to look accidental.

Working alone sharpens this. There is no colleague who remembers. The record is
the only copy.

AI agents sharpen it again. An agent reads the current state of the repository
and reasons from it. Without a record of what was already decided and why, it
proposes a reasonable-looking change that quietly contradicts a choice made for
reasons it cannot see.

## Decision

Record every architecture decision of consequence as a numbered Markdown
document in `docs/adr/`, following `TEMPLATE.md`. Accepted records are
immutable; a changed decision is a new ADR that supersedes the previous one.

## Alternatives considered

| Option | Why not |
|---|---|
| An external wiki or notes app | Drifts from the code, and invisible to agents reading the repository |
| Comments in the code | Scattered, lost in refactors, no room for rejected alternatives |
| Nothing | The status quo that produced the problem |
| Editing records as decisions change | Destroys the history, which is the reason for keeping them |

## Consequences

**Easier**

- The reasoning survives the week in which it was obvious.
- An agent can be pointed at one folder to learn the standing constraints.
- Arguments with yourself get shorter: read the record first.

**Harder, or committed to**

- A small cost on every decision of consequence.
- An index that has to stay honest. An out-of-date decision log is worse than
  none, because it is trusted.

**User-visible** — none.

## Revisit when

The log stops being read, or the index stops matching the folder. At that point
the practice has already failed and should be fixed or dropped deliberately
rather than left to rot.
