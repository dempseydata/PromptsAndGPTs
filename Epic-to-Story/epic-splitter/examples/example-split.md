# Example split: Share and export sessions

This shows the epic-splitter output for an epic that was too big. Only the parts that change are shown; each child epic is then completed with epic-writer.

## Original epic (oversized)

**User story:** As a research analyst, when I want others to see my research, I want to share and export my sessions, so that colleagues can use my findings.

Business Requirements (abridged):
- BR-1: export the current session from the session view
- BR-2: export as .txt and .md
- BR-3: export as PDF with branding
- BR-4: transcript includes every message with timestamps
- BR-5: transcript excludes system prompts and tool-call internals
- BR-6: create a read-only share link
- BR-7: revoke a share link
- BR-8: share a session with a named team member
- BR-9: email an export on a schedule
- BR-10: export within 2 seconds for up to 200 messages

Size check: 10 BRs, three user journeys (export, link sharing, team sharing). Too big.

## Story map

Narrative: get my research to the people who need it.

- **Activity 1: Get a copy of the session** — choose format (BR-2, BR-3), download (BR-1, BR-4, BR-5, BR-10)
- **Activity 2: Share without a file** — create link (BR-6), revoke link (BR-7)
- **Activity 3: Work with my team** — share with a team member (BR-8), scheduled email (BR-9)

MVP line (confirmed by PM): Activity 1 with .txt and .md only.

## Result (split_mode: parent)

### Parent: `share-and-export-sessions` (kept)

The original epic stays as written, with this section added:

```markdown
## Child epics
- export-session-transcript — MVP — BR-1, BR-2, BR-4, BR-5, BR-10
- export-session-pdf — Normal — BR-3
- share-session-link — Normal — BR-6, BR-7
- team-session-sharing — Normal — BR-8, BR-9

BR ownership check: all 10 BRs owned by exactly one child. No gaps, no duplicates.
```

### Children (drafts handed to epic-writer)

- `export-session-transcript` — Release: MVP · Parent epic: share-and-export-sessions
- `export-session-pdf` — Release: Normal · Parent epic: share-and-export-sessions
- `share-session-link` — Release: Normal · Parent epic: share-and-export-sessions
- `team-session-sharing` — Release: Normal · Parent epic: share-and-export-sessions

Each child renumbers its own BRs from BR-1 and keeps a mapping line, for example: `BR-5 (was parent BR-10)`.

## Result (split_mode: replace)

Same four children. The original epic file gets this note at the top and is no longer used:

```markdown
> Superseded by: export-session-transcript, export-session-pdf, share-session-link, team-session-sharing (split on <date>).
```
