# Gherkin rules for acceptance criteria

Acceptance criteria are written in real Gherkin syntax, inside a fenced code block tagged `gherkin`. This applies to epic-level and story-level acceptance criteria.

## Syntax

Use only these keywords:

- `Background:` holds the Given steps that every scenario in the block shares. Use at most one per block.
- `Scenario:` is one concrete example of behaviour, with a short name that says what it proves.
- `Scenario Outline:` plus `Examples:` covers variations of the same behaviour (different formats, roles, limits). Use it instead of writing near-duplicate scenarios.
- `Given` sets the starting state. `When` is the single action or event. `Then` is the observable outcome.
- `And` and `But` continue the previous step type.
- Tags such as `@BR-2` go on the line above the scenario.

## Rules

1. **One When per scenario.** A scenario with two actions is two scenarios, or a sign the story should be split.
2. **One outcome per scenario.** Use one `Then`. Add `And` lines only for facets of the same outcome (for example, the file downloads *and* it has the right name). If the `And` lines describe a different outcome, write a separate scenario.
3. **Tag every scenario** with the requirement or requirements it proves: `@BR-1`, or `@BR-1 @BR-3`. Every requirement in the story or epic has at least one tagged scenario.
4. **Then steps are observable and measurable.** Describe what a user or a test can see: a file, a message, a value, a time limit. Use numbers where the writing guide expects them ("within 2 seconds", "all 12 messages"). Never "works correctly", "is fast" or "is user-friendly".
5. **SHALL belongs in Requirements, not in Gherkin.** Gherkin describes behaviour in the present tense: "Then the file downloads", not "Then the system shall download the file".
6. **Quote exact UI text** when it matters: `Then the system shows "Nothing to export yet"`.
7. **Keep Givens about state, not steps.** "Given the session has 12 messages", not "Given the user typed 12 messages".
8. **Coverage follows release type** (see `release-types.md`). MVP: the main success path plus the most likely failures. Normal: also edge cases, permissions, error states, empty states and limits.
9. **More than about 8 scenarios** in one story is a signal the story should be split.
10. **No weasel words** in any step (see the writing guide's list).
11. **What, not how.** Steps describe what a user or tester can observe, never internal mechanics. "Then the export appears in the user's export history", not "Then a row is written to the exports table". See `what-not-how.md`.

## Epic level vs story level

- **Epic acceptance criteria** describe outcomes of the whole epic, at the level a stakeholder would check at release. Usually 3–6 scenarios.
- **Story acceptance criteria** describe the specific behaviour that story delivers, at the level QA would test.

## Example

```gherkin
Background:
  Given a signed-in researcher
  And an open chat session

@BR-1 @BR-3
Scenario: Export a session as plain text
  Given the session has 12 messages
  When the researcher selects Export > Plain text
  Then a .txt file downloads containing all 12 messages in order
  And each message shows its timestamp

@BR-1
Scenario: Export an empty session
  Given the session has no messages
  When the researcher selects Export > Plain text
  Then the system shows "Nothing to export yet"
  And no file downloads

@BR-2
Scenario Outline: Export in each supported format
  Given the session has 12 messages
  When the researcher selects Export > <format>
  Then a file with the extension <extension> downloads

  Examples:
    | format     | extension |
    | Plain text | .txt      |
    | Markdown   | .md       |
```
