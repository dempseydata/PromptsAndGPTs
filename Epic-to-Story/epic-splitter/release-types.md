# Release types

Every epic and every story has exactly one release type: **MVP** or **Normal**. The release type sets how deep the work goes. Read the epic's release type before writing anything, and carry it down to every story.

## MVP

The smallest end-to-end slice that delivers the epic's core outcome.

- Open questions are allowed, but each one is written down in the open questions.
- Requirements cover the core outcome only. Anything else goes to the parking lot.
- Acceptance criteria cover the main success path plus the most likely failures (typically 2–4 scenarios per story).
- Edge cases, rare permissions cases and limits go to the parking lot, with a note that they belong to a later Normal epic.
- Logging covers adoption (did people use it?) and failure (did it break?) at minimum.

## Normal

A full release, or the later slices of an epic that was split.

- Push for completeness. Unresolved questions block sign-off unless the PM explicitly parks them.
- Requirements are complete and every one is testable.
- Acceptance criteria cover the success path, every failure, edge cases, permissions, error states, empty states and limits. Use Scenario Outline for variations.
- Logging covers adoption, success, failure, performance and anything the epic's success measures depend on.

## Split epics

When an epic is split, the original may stay as a **parent** that holds the full vision. The parent has no release type of its own; its children do. Each child epic records `Parent epic: <slug>` next to its release type.
