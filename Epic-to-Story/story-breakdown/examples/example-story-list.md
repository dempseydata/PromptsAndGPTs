# Story list: Export a session transcript

Epic: export-session-transcript · Release: MVP
Split approach: Pattern 4 (Data Variations) for formats, then Pattern 8 (Defer Performance) for the time limit.

## Stories

1. **Export a session as plain text**
   Delivers: a signed-in user downloads the current session as a .txt transcript.
   Covers: BR-1, BR-2 (.txt only), BR-3, BR-4 · LOG-1, LOG-2
   Split pattern: Data Variations (simplest format first)
   Depends on: None

2. **Export a session as Markdown**
   Delivers: the same export as a .md file that keeps formatting such as code blocks and lists.
   Covers: BR-2 (.md) · LOG-1
   Split pattern: Data Variations (second format)
   Depends on: Story 1

3. **Export long sessions within 2 seconds**
   Delivers: sessions of up to 200 messages export within the time limit.
   Covers: BR-5 · LOG-2
   Split pattern: Defer Performance
   Depends on: Story 1

## Coverage check

- BR-1: story 1
- BR-2: stories 1 and 2
- BR-3: story 1 (story 2 reuses the same content)
- BR-4: story 1 (story 2 reuses the same content)
- BR-5: story 3
- LOG-1: stories 1 and 2
- LOG-2: stories 1 and 3
- Stories with no BR: none

## Considered and parked

- PDF export: already in the epic's parking lot. Not a story.
- Custom file names: depends on the Design open question in the epic. Revisit when answered.
- Export settings screen (choose which message types to include): scope creep for an MVP; the core outcome works without it. Candidate for a later Normal epic.
