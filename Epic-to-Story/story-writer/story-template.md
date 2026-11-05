# Story template

This file is the single source for the story's structure. The skill reads it at run time; it does not hold its own copy of the sections. To change the story format, edit this file only.

## How to read this file

- The skeleton is the block between `<!-- TEMPLATE START -->` and `<!-- TEMPLATE END -->`. Write sections in the order they appear there, using the headings as written. Keep every heading, even when a section is empty.
- Lines inside `<!-- GUIDE: ... -->` comments are instructions for that section. Follow them. **Never copy GUIDE comments into the finished story.**
- A GUIDE that says `placeholder` means: write exactly the text shown under the heading and nothing else. These sections are for engineering.
- `<angle brackets>` are placeholders to replace.

## Contract: what the skill relies on

Change anything else freely. If you change one of these, also check story-writer's self-check:

- A **header line** listing the BR and LOG IDs the story covers.
- **Requirements** ending with the BR they come from, e.g. `(BR-2)`.
- **Acceptance criteria** as one fenced `gherkin` block, scenarios tagged with `@BR-n`.

## Formatting

Must survive pasting into JIRA: `#`/`##` headings, plain lines, bullet lists and one fenced `gherkin` code block. No tables, no HTML, no emoji.

<!-- TEMPLATE START -->

````markdown
# <Story title>
<!-- GUIDE: The title says the value, not the widget: "Export a session as plain text", not "Add export button". -->
Epic: <epic slug> · Release: <MVP | Normal> · Covers: <BR-n, BR-n> · <LOG-n, LOG-n or "No logging">
<!-- GUIDE: The header lists every BR and LOG item this story covers, from the story list. It must match the IDs used in Requirements, Logging and the Gherkin tags. -->

## Story
<!-- GUIDE: Four lines: As a / When / I want / So that. Use the persona from the epic's user story unless this story serves someone else. "So that" states the outcome, not a restatement of "I want". -->
As a <role or persona>
When <situation or trigger>
I want <capability or action>
So that <goal, value or outcome>

## Requirements
<!-- GUIDE: Only what this story delivers. Each line is a SHALL statement ending with the BR it comes from. A story requirement can be narrower than its BR (for example, one format out of two). What, not how: behaviour, rules and targets only; no technology, schemas, APIs or architecture (see what-not-how.md). -->
- The system SHALL <requirement>. (BR-n)

## Implementation notes
<!-- GUIDE: placeholder -->
_Engineering to complete._

## Logging
<!-- GUIDE: Only the events or metrics this story emits, each tagged with its LOG item, using the field names from the epic. If the story emits nothing, write: "No logging required for this story: <reason>." -->
- <event or metric this story emits> (LOG-n)

## Acceptance criteria
<!-- GUIDE: One fenced gherkin block following gherkin-rules.md. Background for shared Givens. Every requirement in this story has at least one tagged scenario. Coverage by release type: MVP = the main success path plus the most likely failures (usually 2–4 scenarios); Normal = also edge cases, permissions, error states, empty states and limits, using Scenario Outline for variations. Quote exact UI text from the epic's UX design needs. Every step describes what a user or tester can observe, never internal mechanics (see what-not-how.md). -->
```gherkin
Background:
  Given <shared starting state>

@BR-n
Scenario: <what this scenario proves>
  Given <state>
  When <single action or event>
  Then <observable, measurable outcome>
```

## Testing notes
<!-- GUIDE: placeholder -->
_Engineering to complete._

## Closure checklist
<!-- GUIDE: placeholder -->
_Engineering to complete._
````

<!-- TEMPLATE END -->
