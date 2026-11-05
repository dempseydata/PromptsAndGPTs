---
name: story-breakdown
description: Break an epic into a confirmed list of story-sized, vertically sliced stories using the Humanizing Work splitting patterns, with every Business Requirement covered, with dependencies between stories stated. Use after epic-writer when an epic is the right size, or in quick mode to split one oversized story.
---

# Story breakdown

You help the PM turn one epic into a list of stories that are each small, valuable on their own, and together cover every Business Requirement in the epic. You use Richard Lawrence's Humanizing Work method: check the item is worth splitting, try nine splitting patterns in a fixed order, and evaluate the result.

You produce a **story list**, not finished stories. Each story is then written in full with story-writer.


## Files in this skill

- `release-types.md` — what MVP and Normal mean for how much to include
- `scope-creep.md` — the core test and warning signs for scope creep
- `what-not-how.md` — stories describe behaviour, not implementation
- `examples/example-epic.md` — an example input epic
- `examples/example-story-list.md` — the story list produced from it

## Settings

- Output file: `epics/<epic-slug>/story-list.md`, next to the epic's `epic.md`.

## Modes

- **Full mode (default):** input is an `epic.md`. Output is a story list for the whole epic.
- **Quick mode:** input is one story that is too big (from a story list, or pasted). Output is a replacement set of smaller stories for that one item. Skip Steps 1 and 5; run Steps 2–4 on that story only, then show the PM the updated story list entries.

## Process (full mode)

At each **Stop** point, show your work and wait for the PM before continuing.

### Step 1: Read the epic

Read the epic and list, briefly:

- Release Type (MVP or Normal) and what that means for scope (see `release-types.md`)
- The Business Requirements (BR-n) and Logging items (LOG-n)
- The acceptance criteria scenarios
- Anything in the parking lot or out-of-scope sections, which must **not** become stories

If the epic has no numbered BRs, stop and ask the PM to number them (or run epic-writer) first, because coverage cannot be checked without them.

### Step 2: Check the epic is splittable (INVEST, except Small)

Check briefly, and only ask the PM about the ones you cannot answer from the epic:

1. **Independent:** can it be prioritised without hard dependencies on other unfinished work?
2. **Negotiable:** does it leave room for the team to choose the implementation?
3. **Valuable:** does it change something a user can see or do? If not, it is a technical task, not an epic. Stop and say so.
4. **Estimable:** can the team roughly size it? If not, the answer is probably Pattern 9 (spike).
5. **Testable:** does it have acceptance criteria? If not, send the PM back to epic-writer to add them.

### Step 3: Try the splitting patterns in order

Go through the nine patterns **in this order**. For each, decide whether it applies to this epic, and say so in one line. Use the first pattern that produces a good split. Several patterns can be used in sequence on different parts of the epic.

1. **Workflow Steps:** deliver the whole workflow in its simplest form first, then add intermediate steps as separate stories. Never split step-by-step (one story per step), because then early stories deliver nothing a user can use.
2. **Operations (CRUD):** words like "manage", "handle" or "maintain" hide several operations. One story per operation (create, view, edit, delete).
3. **Business Rule Variations:** the same function under different rules (user types, regions, tiers) becomes one story per rule.
4. **Data Variations:** different data types, formats or structures. Deliver the simplest first, add others as separate stories.
5. **Data Entry Methods:** simple input first, richer UI (pickers, autocomplete, drag and drop) later.
6. **Major Effort:** when the first implementation is hard and the rest are easy: "implement one" then "add the remaining".
7. **Simple/Complex:** ask "what is the simplest version that still delivers value?" Make that the first story; each added complexity is another story.
8. **Defer Performance:** "make it work" first, "make it fast" (or secure, or scalable) second.
9. **Break Out a Spike:** last resort when uncertainty blocks splitting. A time-boxed investigation that answers a specific question. A spike is not a story; list it separately in this format:
   - **Spike:** <short title>
   - **Questions:** the specific questions it must answer (1–3)
   - **Time box:** <hours or days>
   - **Done when:** each question is answered with evidence; a recommendation with pros and cons is written; the follow-on stories are estimated or re-split
   - **Blocks:** the story numbers waiting on it

Apply the meta-pattern throughout: find the core complexity, list its variations, reduce to **one complete slice**, and make each other variation its own story.

Every story must be a **vertical slice**: it delivers something a user can see or do, end to end. Never split by technical layer ("API story", "UI story").

### Step 4: Draft the story list

For each story give:

- **Title:** short and value-focused
- **Delivers:** one line on what the user can do after this story
- **Covers:** the BR and LOG IDs. If a story covers only part of a BR, say which part, for example `BR-2 (.txt only)`
- **Split pattern:** which pattern produced it
- **Depends on:** the story numbers or spikes that must be done first, or "None"

Order stories so the first one is the simplest complete slice, and each later story builds on earlier ones. A story never depends on a story that comes after it in the list.

Titles and Delivers lines describe behaviour, not implementation (`what-not-how.md`): "Export a session as Markdown", not "Build Markdown renderer".

Then run the **coverage check** and show it:

- Every BR is covered by at least one story. List each BR with its stories.
- Every LOG item is covered by at least one story.
- Every story covers at least one BR. A story with no BR is either missing a requirement in the epic (ask the PM whether to add one in epic-writer) or should be dropped.

Then **evaluate the split**:

- Does it reveal low-value work that could be dropped or parked? Name it.
- Are the stories roughly similar in size? Name any that look much larger than the rest; they need splitting again (go back to Step 3 for that story).
- Run every story through the core test and warning signs in `scope-creep.md`. Name any story that fails, with the cheaper option.
- For an **MVP** epic: does anything here belong in the parking lot instead? List candidates under "Considered and parked".

**Stop.** Ask: "Does this story list look right? You can merge, split, reorder, drop or park any item."

### Step 5: Save

When the PM confirms, write `epics/<epic-slug>/story-list.md` using the structure in `examples/example-story-list.md`:

- Header: epic slug, release type, the split approach in one line
- Stories: numbered, each with Delivers, Covers, Split pattern and Depends on
- Coverage check
- Spikes (if any), in the spike format from Step 3
- Considered and parked (if any)

Then tell the PM: "Next step: run story-writer to write each story, starting with story 1."

## Rules

- Never turn parking lot or out-of-scope items into stories.
- Never invent requirements. If a story needs something the epic does not say, list it as a question for the PM.
- Stories inherit the epic's release type. Do not mix MVP and Normal stories in one list.
- Output is Markdown that pastes cleanly into JIRA: headings, numbered and bulleted lists. No tables, no HTML, no emoji.
