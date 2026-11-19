# Agent instructions

## Where things are

- `docs/prd/` — what is being built and why. Numbered, living.
- `docs/adr/` — technical decisions. Numbered, immutable, superseded rather
  than edited.
- Everything else is code.

## What does not belong here

- Work state. No `TODO.md`, no backlog file, no status table. That lives in the
  issue tracker.
- Raw research evidence or personal data — not in a document, a commit message,
  a fixture or a comment. If given a transcript as context, use it and leave it
  out of the repository.
- Separate design documents. This project is designed in code.

## Before changing anything

- Read `docs/adr/README.md`. An accepted ADR is a constraint.
- Change only what the task requires. Unrelated refactors and formatting
  sweeps go in their own change.

Stop and ask rather than deciding when:

- A technical choice is costly to reverse and no ADR covers it.
- The task implies behaviour no PRD describes.
- The request contradicts an accepted ADR.
- A user-visible decision is hiding inside a technical one. "Cache for 24
  hours" is technical; "users may see day-old data" is a product decision in
  technical clothing.

## Scope of a change

- Build the smallest thing that satisfies the PRD. Generality no current caller
  needs is a guess about the future, and it has to be maintained whether the
  guess was right or not.
- No abstraction until there is a second caller. One caller behind an interface
  is indirection with nothing on the other side.
- No configuration option until something needs to configure it.
- Prefer what the language, the runtime and the existing dependencies already
  do. Reaching for something new to do what the platform does is the common
  failure, not the exception.

## Dependencies

A dependency is cheap to add and expensive to remove, which makes it exactly
the kind of decision that needs an ADR.

Before adding one, say what in the standard library or the existing
dependencies was considered, and why it does not do the job. If that cannot be
answered, the dependency is not justified yet.

## Skills

`.claude/skills/` holds procedures you run on request. They are not rules that
apply always; nothing here is loaded until it is invoked.

### grill-me

Interrogation before work, never during it. Run it when:

- An idea has no PRD yet. Grill until the problem, the user, the outcome and
  what is out of scope can be stated without guessing.
- A decision would be expensive to reverse and no ADR covers it. Grill the
  alternatives and the revisit trigger, then write the ADR.
- A task implies behaviour no PRD describes. That is the stop rule above,
  answered properly instead of with a single question.

Working alone, this skill is standing in for the colleague who would otherwise
ask these questions. It is also the one place where spending a conversation is
cheaper than the rebuild it prevents.

Skip it when a PRD or an accepted ADR already answers the question, when the
cause is obvious and the fix is small, or when being wrong costs less than the
grilling. Do not grill mid-implementation.

## Writing documents

- **PRD** — problem and outcome only. A PRD that names a framework, a database
  or a protocol has drifted into ADR territory. Draft one on request, never
  unprompted.
- **ADR** — write one whenever a decision would be expensive to reverse. Use
  `docs/adr/TEMPLATE.md`, four-digit numbering. Never edit an accepted ADR;
  write one that supersedes it and update both index rows.

`docs/prd/` is write-blocked in `.claude/settings.json`. Hitting that block
means the work has drifted from implementing a requirement into rewriting it.
Say so rather than looking for a way around.

## Tests

- Test observable behaviour through the public interface. A test that reaches
  into internals blocks the refactors tests exist to enable.
- Use the lowest layer that can observe the behaviour honestly, and mock only
  what the project does not own — third-party services, the clock, the network.
  Needing to mock an internal module means the test belongs a layer up.
- Before finishing, ask what change to the code under test would break this
  test. If the answer is "none a user would notice", it asserts the
  implementation back to itself. Delete it and test the behaviour.
- No coverage target. Never weaken or delete a failing test to make a change
  pass; say which assumption changed and why.

## Conventions

- Filenames under `docs/`: zero-padded, kebab-case, `0007-short-title.md`.
- Links are relative with no `./` prefix: `[ADR-0001](0001-record-architecture-decisions.md)`.
  No wikilinks. Link text names the document, never "this ADR" or "see here".
- Never commit secrets, credentials, tokens or personal data, including in
  fixtures, example configs and documentation examples.

## Reporting

Say what changed and where. Do not narrate the steps or summarise what the diff
already shows.

State what is uncertain, incomplete or assumed in full sentences. That is the
part worth reading, and compressing it costs more than it saves.

## Definition of done

1. It builds and the project's checks pass.
2. Changed behaviour is covered at the right layer, and the new test fails when
   that behaviour is broken.
3. Any decision made along the way is recorded as an ADR.
4. Documentation the change made untrue is updated in the same change.

If any of these cannot be satisfied, say so rather than reporting success.
