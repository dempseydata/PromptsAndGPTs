# Export a session transcript

## 1. User Story
As a research analyst
When I finish a research session I want to share with colleagues
I want to export the session as a file
So that I can share the findings without copying and pasting each message

## 2. Why This Epic
**Need type:** Requested

**Problem framing**
- **I am:** a research analyst who runs long research sessions and reports findings to colleagues and stakeholders
- **Trying to:** share what I found, with its context, as soon as a session is done
- **But:** I have to copy messages one by one into an email or document, and the order and timestamps get lost
- **Because:** the product has no way to get a session out as a single file
- **Which makes me feel:** frustrated at the rework, and worried colleagues see an incomplete picture

**Context & constraints:** Colleagues read results in email and chat, not in the product. Many sessions run past 50 messages.

**Evidence:** In user interviews, 4 of 5 participants named missing export as a top pain point. Support logged 37 export requests in the last quarter.

**Problem statement:** Research analysts need a way to share a complete session with colleagues because the product cannot export a session as a file, which currently forces manual copying and loses context.

**Success:** 90% of export attempts succeed on the first try, and 20% of weekly active users export at least one session within 30 days of launch.

## 3. Key Terms (optional, update throughout)
- **Session:** one conversation thread, from the first message to the most recent.
- **Transcript:** a file containing every user message and assistant response in a session, in order.
- **Tool-call internals:** the raw requests and responses exchanged with tools (search, RAG, image generation). These are not part of a transcript.

## 4. Release Type
- **Release type:** MVP
- **Parent epic:** None
- **User group:** all signed-in users
- **Rollout plan:** feature flag, 10% of users for one week, then 100%
- **Support expectations:** Product support handles questions using a help-centre article published at launch

## 5. Business Requirements
- **BR-1:** The system SHALL let a signed-in user export the current session from the session view.
- **BR-2:** The system SHALL export transcripts in plain text (.txt) and Markdown (.md).
- **BR-3:** The transcript SHALL include every user message and assistant response, in order, each with its timestamp.
- **BR-4:** The transcript SHALL exclude system prompts and tool-call internals.
- **BR-5:** The system SHALL complete an export within 2 seconds for sessions of up to 200 messages.

## 6. Assumptions
- Users share transcripts mainly by email and chat, so .txt and .md cover the MVP need.
- Sessions longer than 200 messages are under 2% of sessions.
- The session history API returns messages with timestamps.

## 7. Dependencies
- Session history API (Platform team) for message content and timestamps.
- Feature flag service for the staged rollout.
- Analytics pipeline for LOG-1 and LOG-2.

## 8. Foundational Research
- User interviews, 5 participants: 4 of 5 named missing export as a top pain point.
- Support tickets: 37 export requests last quarter.
- Comparable assistants offer .txt or .md export from the session menu.

## 9. UX Design Needs
- Export appears in the session menu with a submenu: Plain text, Markdown.
- Empty sessions show the message "Nothing to export yet" instead of downloading a file.
- Errors show "Export failed. Try again." with a retry action.
- The menu is reachable by keyboard and labelled for screen readers.

## 10. Logging & Analytics
- **LOG-1:** `export_requested` — user ID, session ID, format, message count — Product team, adoption tracking.
- **LOG-2:** `export_completed` / `export_failed` — duration in milliseconds, error code on failure — Engineering on-call, reliability and the 2-second target.
- **Access:** Product and Engineering teams. No message content is logged.
- **Monitoring:** The Product team reviews the export dashboard every Monday for the first 4 weeks after launch.

## 11. Acceptance Criteria
```gherkin
Background:
  Given a signed-in user with an open session

@BR-1 @BR-2 @BR-3
Scenario: Export a session in a supported format
  Given the session has 12 messages
  When the user exports the session as Markdown
  Then a .md file downloads containing all 12 messages in order with timestamps

@BR-4
Scenario: Transcripts exclude internal content
  Given the session includes a web search tool call
  When the user exports the session as plain text
  Then the file contains the assistant's answer
  And the file contains no system prompt or tool-call payload

@BR-5
Scenario: Long sessions export within the time limit
  Given the session has 200 messages
  When the user exports the session as plain text
  Then the file downloads within 2 seconds
```

## 12. Open Questions & Parking Lot
- **Open question:** Should exported files include the session title in the file name? — Owner: Design
- **Parking Lot:** PDF export. Requested by 2 of 5 interviewees. Candidate for a later Normal epic.
- **Parking Lot:** Export straight to email. Out of scope for MVP.

## 13. Out of Scope (optional)
- Exporting several sessions at once.
- Exporting attached documents or generated images.
