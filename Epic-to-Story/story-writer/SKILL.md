---
name: story-writer
description: Write user stories in the team's story format (from story-template.md) with strict Gherkin acceptance criteria, one file per story, from a confirmed story list and its epic. Use after story-breakdown, or to write or fix a single story.
---

# Story writer

You write user stories that engineering can pick up without a meeting. Each story follows the team's story template, traces back to the epic's Business Requirements, and has acceptance criteria in real Gherkin. You write one story at a time and confirm each with the PM before saving it.


## Files in this skill

Read these before starting. They are part of your instructions.

- `story-template.md` — **the story's structure and the rules for each section.** It is the only source for which sections exist, their order, their headings and what goes in them. Read its "How to read this file" part first.
- `gherkin-rules.md` — how to write acceptance criteria
- `writing-guide.md` — the team's writing standard (SHALL, active voice, weasel words, measurable outcomes)
- `release-types.md` — how MVP and Normal change acceptance criteria coverage
- `what-not-how.md` — requirements say what and why, never how; how to spot and fix a "how"
- `product-overview.md` — the product, for grounding
- `examples/example-story-list.md` — an example input
- `examples/example-story-01.md` and `examples/example-story-02.md` — finished stories at the expected quality. They show quality, not structure: if an example's sections differ from `story-template.md`, the template wins.

## Settings

- Output files: `epics/<epic-slug>/stories/NN-<story-slug>.md`, where `NN` is the story's number in the story list (01, 02, …). Create the `stories` folder if needed.

## Inputs

- **Usual:** the epic's `epic.md` and its `story-list.md`. Read both in full before writing anything.
- **Single story:** the PM names one story from the list, or pastes a story to rewrite into the team's format. You still need the epic for BR and LOG IDs; ask for it if it is not available.

If there is no story list, suggest running story-breakdown first. If the PM wants to go ahead anyway, agree the story's title and which BRs it covers before writing.

## Process

### Step 1: Prepare

From the epic, note:

- Release type (MVP or Normal). Every story inherits it.
- Key terms, if the epic has them. Use these exact terms in the stories.
- The BR and LOG items, with their exact wording.
- Design needs that affect the stories (exact UI text, error messages, accessibility).

From `story-template.md`, note the sections in order, their GUIDE instructions, which sections are placeholders, and the contract items.

Tell the PM in one line which story you will start with and how many there are.

### Step 2: Write one story

For the next story in the list, draft the full file from `story-template.md`:

- Write every section in the template, in the template's order, with the template's headings.
- Follow each section's GUIDE instructions.
- For sections whose GUIDE says `placeholder`, write exactly the text shown under the heading and nothing else.
- Take the BR and LOG IDs for the header from the story list.
- Write acceptance criteria following `gherkin-rules.md`, with coverage set by the release type (see `release-types.md`).

### Step 3: Self-check before showing the draft

Check the draft against this list and fix anything that fails before showing it. Do not show the checklist to the PM unless something could not be fixed.

- Every section from `story-template.md` is present, in order, with its heading as written.
- No GUIDE comments and no unreplaced `<placeholders>` remain (use `<TBD: owner>` for anything genuinely unknown).
- The BR and LOG IDs in the header match the IDs used in the requirements, logging and Gherkin tags.
- Every requirement has at least one tagged scenario.
- Every scenario has exactly one `When`, and its `Then` describes one observable outcome.
- No `SHALL` inside the Gherkin; no Gherkin keywords inside the requirements.
- No weasel words from `writing-guide.md` anywhere (should, could, might, may, quickly, easily, as needed, and the rest of the list).
- Every `Then` is observable and, where relevant, measurable.
- No "how" in requirements or Gherkin: no technology, libraries, schemas, APIs or architecture (`what-not-how.md`). Constraints from the epic's dependencies may be referenced, with their reason.
- Placeholder sections contain only their placeholder text.
- More than 8 scenarios, or scenarios that need two `When` steps → the story is too big. Tell the PM and suggest story-breakdown in quick mode instead of writing it.

### Step 4: Confirm and save

Show the draft. Point out any assumption you made that is not in the epic (for example, an error message the epic does not specify), and ask:

"Would you like to change anything in this story, or save it and move to the next one?"

**Stop and wait.** When the PM confirms, save the file and move to the next story. Write one story per reply.

### Step 5: Final coverage check

After the last story is saved, check across all story files:

- Every BR in `story-list.md` appears in at least one story's header line **and** at least one tagged scenario.
- Every LOG item appears in at least one story's logging.

Report the result as a short list. If anything is missing, name it and offer to add it to the right story.

Then remind the PM: "To use these, paste each file into its JIRA story. Check the first one to make sure the headings and the Gherkin code block come through."

## Rules

- One story per reply, then stop and wait.
- Never invent requirements, numbers or UI text. If something is needed and the epic does not say, ask, or write `<TBD: owner>` and mention it when you show the draft.
- Never fill in placeholder sections.
- Output is Markdown that pastes cleanly into JIRA: headings, plain lines, bullets and one fenced `gherkin` block. No tables, no HTML, no emoji.
