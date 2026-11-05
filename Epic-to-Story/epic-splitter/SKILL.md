---
name: epic-splitter
description: Split an epic that is too big for one release into an MVP epic and one or more Normal epics, using a story map to draw the MVP line. Use when epic-writer's size check flags an epic, or the PM says an epic is too big.
---

# Epic splitter

You help the PM split an oversized epic into an **MVP** epic plus one or more **Normal** epics. You do this by mapping the epic as a user journey (Jeff Patton's story mapping), drawing an MVP line, and assigning every Business Requirement to exactly one child epic.

You do not write the child epics in full. You produce drafts, and each draft is then completed with epic-writer.


## Files in this skill

- `release-types.md` — what MVP and Normal mean
- `scope-creep.md` — the core test and warning signs for scope creep
- `examples/example-split.md` — a complete worked split, in both modes

## Settings

- **split_mode:** `parent`
  - `parent`: keep the original epic as a parent that holds the full vision, and link the children from it.
  - `replace`: mark the original epic superseded; the children replace it.
  - The team has not settled this yet. If the PM names a mode when invoking the skill, use that. Otherwise use the value above. To change the default, edit the line above.
- Output folder: `epics/`, relative to the current working folder.

## Input

An `epic.md` (from epic-writer or pasted). If you only get a description, ask for the epic file or at least its user story and requirements before starting.

## Process

Work through the steps in order. At each **Stop** point, show your work and wait for the PM to confirm or change it before continuing.

### Step 1: Confirm the narrative

Write one sentence that states what the user is trying to get done end to end, based on the epic's user story and problem framing. Example: "Get my research to the people who need it."

**Stop.** Ask: "Is this the right end-to-end goal?"

### Step 2: Map the backbone

List 3–5 **activities**: what the user does, in order, to reach the goal. Activities are user behaviours, not features.

Under each activity, list its **steps** (2–5 each). After each step, put the BR IDs it relates to, for example `(BR-2, BR-3)`.

Every BR must appear under at least one step. If a BR fits nowhere, list it separately as "Unplaced" and ask the PM where it belongs.

Show the map as an indented list (not a table).

**Stop.** Ask: "Is anything missing from the journey, or in the wrong order?"

### Step 3: Propose the MVP line

Propose the MVP: **the smallest set of steps that lets the user complete the narrative end to end and delivers the epic's core outcome.** Every activity the MVP needs must be represented by at least its simplest step. An MVP that stops halfway through the journey is not an MVP.

Use `scope-creep.md` to draw the line: apply its core test to every step, and keep any step that shows a warning sign (admin screens, extra roles, extra integrations, dashboards, polish) below the line unless the PM says otherwise.

Then group everything below the line into one or more **Normal** slices. Each Normal slice is a coherent piece of the journey that can ship on its own (for example "PDF export", "share links", "team sharing").

Show:

- The MVP: which steps and BRs it includes, and one line on why this is the smallest useful slice
- Each Normal slice: a short name, its steps and BRs, and one line on what it adds

**Stop.** Ask: "Do you want to move the MVP line or regroup the Normal slices?"

### Step 4: Ownership check

Check that **every BR from the original epic is owned by exactly one child**. Do the same for LOG items.

- If a BR is in no child: list it as a gap and ask where it goes.
- If a BR is in two children: ask which one owns it. If the PM says it genuinely spans both, split the BR into two narrower BRs, one per child, and say so.

Show the ownership list as lines like `BR-4 → export-session-transcript (MVP)`.

**Stop** only if there are gaps or duplicates. Otherwise continue.

### Step 5: Write the drafts

Create one folder and draft file per child: `epics/<child-slug>/epic.md`. Use slugs like `<original-slug>-mvp` or a descriptive name the PM prefers.

Each draft uses **the same sections and headings as the original epic**, in the same order. Do not use a fixed list of sections; copy the structure from the original file. Fill the drafts like this:

- **User story:** narrowed to this child's slice
- **Release type field:** `MVP` or `Normal`, and the parent epic field set to the original slug (in `parent` mode) or `Split from: <original slug>` (in `replace` mode)
- **Requirements:** the BRs this child owns, **renumbered from BR-1**, each with a mapping note: `BR-1 (was parent BR-6)`
- **Logging:** the LOG items this child owns, renumbered the same way
- **Open questions / parking lot:** any open questions from the original that affect this child
- **Every other section:** copy what applies from the original, or keep the heading with `<To complete in epic-writer>`

If you cannot find one of these in the original epic (for example, it has no release type field), tell the PM which one is missing and ask where it should go before writing the drafts.

Then handle the original epic file according to `split_mode`:

- **parent:** keep the original file unchanged and add this section at the end:

  ```markdown
  ## Child epics
  - <child-slug> — MVP — BR-1, BR-2, ...
  - <child-slug> — Normal — BR-3, ...

  BR ownership check: all <n> BRs owned by exactly one child.
  ```

- **replace:** add this line at the very top of the original file and leave the rest unchanged:

  ```markdown
  > Superseded by: <child-slug>, <child-slug>, ... (split on <YYYY-MM-DD>).
  ```

### Step 6: Hand off

Tell the PM what you created, then:

"Next step: complete each child epic with epic-writer, starting with the MVP epic (<slug>). Each draft already has its release type, requirements and logging filled in."

## Rules

- Activities describe what the user does, not what the product has.
- Never drop a BR silently. Every BR ends up owned by exactly one child, or the PM explicitly removes it.
- Do not add new requirements during a split. If you notice a gap, list it as an open question for the relevant child.
- Do not split by technical layer (for example "backend epic" and "frontend epic"). Every child must deliver something a user can see or use.
- Output is Markdown that pastes cleanly into JIRA: headings, bullets and code blocks only. No tables, no HTML, no emoji.
