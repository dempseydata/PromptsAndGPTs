# Export a session as plain text
Epic: export-session-transcript · Release: MVP · Covers: BR-1, BR-2, BR-3, BR-4 · LOG-1, LOG-2

## Story
As a research analyst
When I finish a research session I want to share with colleagues
I want to download the session as a plain text file
So that I can share the findings without copying and pasting each message

## Requirements
- The system SHALL show an Export option with a Plain text choice in the session menu for signed-in users. (BR-1)
- The system SHALL produce the export as a .txt file. (BR-2)
- The file SHALL contain every user message and assistant response in order, each with its timestamp. (BR-3)
- The file SHALL exclude system prompts and tool-call internals. (BR-4)

## Implementation notes
_Engineering to complete._

## Logging
- Emit `export_requested` with user ID, session ID, format "txt" and message count. (LOG-1)
- Emit `export_completed` with duration, or `export_failed` with duration and error code. (LOG-2)

## Acceptance criteria
```gherkin
Background:
  Given a signed-in research analyst
  And an open chat session

@BR-1 @BR-2 @BR-3
Scenario: Export a session as plain text
  Given the session has 12 messages
  When the analyst selects Export > Plain text
  Then a .txt file downloads containing all 12 messages in order
  And each message shows its timestamp

@BR-4
Scenario: Internal content is left out
  Given the session includes a web search tool call
  When the analyst selects Export > Plain text
  Then the file contains the assistant's answer
  And the file contains no system prompt or tool-call payload

@BR-1
Scenario: Export an empty session
  Given the session has no messages
  When the analyst selects Export > Plain text
  Then the system shows "Nothing to export yet"
  And no file downloads

@BR-1
Scenario: Export fails
  Given the session history service is unavailable
  When the analyst selects Export > Plain text
  Then the system shows "Export failed. Try again." with a Retry action
  And no file downloads
```

## Testing notes
_Engineering to complete._

## Closure checklist
_Engineering to complete._
