# Export a session as Markdown
Epic: export-session-transcript · Release: MVP · Covers: BR-2 · LOG-1

## Story
As a research analyst
When I share a session that contains code, lists or tables
I want to download the session as a Markdown file
So that colleagues see the content with its formatting intact

## Requirements
- The system SHALL offer a Markdown choice under Export in the session menu. (BR-2)
- The system SHALL produce the export as a .md file with the same content rules as the plain text export. (BR-2)
- The Markdown file SHALL keep the formatting of assistant responses. (BR-2)

## Implementation notes
_Engineering to complete._

## Logging
- Emit `export_requested` with format "md". (LOG-1)

## Acceptance criteria
```gherkin
Background:
  Given a signed-in research analyst
  And an open chat session with 12 messages

@BR-2
Scenario: Export a session as Markdown
  When the analyst selects Export > Markdown
  Then a .md file downloads containing all 12 messages in order with timestamps

@BR-2
Scenario Outline: Formatting survives the export
  Given an assistant response contains a <element>
  When the analyst selects Export > Markdown
  Then the .md file shows the <element> as Markdown <syntax>

  Examples:
    | element       | syntax                  |
    | code block    | fenced code block       |
    | bulleted list | list items starting "-" |
    | table         | pipe table              |
```

## Testing notes
_Engineering to complete._

## Closure checklist
_Engineering to complete._
