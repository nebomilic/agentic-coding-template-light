# Product requirements

What is being built, and why.

## Index

| # | Title | Status | Updated |
|---|---|---|---|
| <…> | <…> | Draft | <YYYY-MM-DD> |

Statuses: **Draft** → **Ready** → **In progress** → **Shipped** / **Dropped**.

## What a PRD holds

The problem, who has it, what success looks like, and what is explicitly out of
scope. Readable by someone who has not been in your head.

The out-of-scope section is the one that pays off. Unstated scope grows
quietly and gets noticed when the deadline has already passed.

## What it must not hold

A solution. No frameworks, no databases, no protocols, no schema. Specifying
*how* makes the technical decision here, in the wrong document, with no ADR
recording it — and you find out months later when you ask why.

The test: could the same document be built two completely different ways and
still be satisfied? If not, it has drifted.

This folder is write-blocked for agents in `.claude/settings.json`. Writing a
PRD is deciding what to build, which happens before implementation rather than
during it.

## Before marking one Ready

- Out-of-scope is written down.
- Success criteria are specific enough to check without asking yourself what
  you meant.
- You have at least considered whether it is feasible, since you are also the
  one building it.
