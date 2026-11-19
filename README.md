# <Project Name>

> One sentence: what this does, and for whom.

## What this repository is

The project and the reasoning behind it in one place. Code, the requirements
it answers, and the technical decisions it rests on, so that a change and the
document explaining it travel together.

Built for one person doing design, development and product. Everything about
dividing work between people has been stripped out.

| Path | What lives here |
|---|---|
| `docs/product.md` | What the product is, and what it will never do |
| `docs/prd/` | What is being built and why |
| `docs/adr/` | Technical decisions and what they commit you to |
| `AGENTS.md` | Rules for AI agents working in this repository |
| `.claude/skills/` | Procedures agents run on request |
| `.claude/settings.json` | Paths agents may not write to |

Code goes wherever the stack wants it. This template does not prescribe a
layout; add one and say so here once it exists.

## What does not live here

- **Work state** — what is in flight, what is next. That belongs in an issue
  tracker. State changes many times a week and version control turns that into
  commit noise and merge conflicts. No `TODO.md`, no backlog file.
- **Raw research** — transcripts, recordings, purchased reports. Record the
  finding, point at where the evidence lives. Personal data never enters
  version history, which is permanent and distributed.
- **Visual design** — this project is designed in code. The code is the design
  record.

Tickets and notes link *into* this repository. Nothing here restates them.

## Getting started

1. Read `AGENTS.md`.
2. Read `docs/product.md`. One page, and it decides what gets said no to.
3. Skim `docs/adr/README.md` for decisions already settled.
4. Read the PRD for whatever you are about to touch.

## Status

**This is the template, not a project built from it.** There is no code; the
documents under `docs/` are a template plus the one ADR that justifies keeping
ADRs at all.

Replace this section when you copy it — for example: `Building v1, scope in
docs/prd/0001`.
