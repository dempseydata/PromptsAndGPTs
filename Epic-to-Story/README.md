# Epic-to-stories skills

Four skills that take a feature idea to a written epic, split it into stories, and write each story in the team's format, ready to paste into JIRA. Written to run on Claude Sonnet 5: each skill has numbered steps, explicit stop-and-confirm points and exact output templates.

## The flow

```
idea → epic-writer → size check
                       ├─ too big → epic-splitter → epic-writer (each child epic)
                       └─ fits    → story-breakdown → story-writer (each story) → paste into JIRA
```

| Skill | What it does | Output |
|---|---|---|
| `epic-writer` | Writes one epic with the PM, one section at a time, using the 13-section template. Ends with a size check. | `epics/<slug>/epic.md` |
| `epic-splitter` | Maps an oversized epic as a user journey, draws the MVP line, and drafts an MVP epic plus Normal epics, with every requirement owned by exactly one child. | `epics/<child-slug>/epic.md` for each child, plus a note on the original |
| `story-breakdown` | Turns an epic into a confirmed story list using the nine Humanizing Work splitting patterns, checks every requirement is covered, and states dependencies between stories. Quick mode splits one oversized story. | `epics/<slug>/story-list.md` |
| `story-writer` | Writes each story in the 7-section format with strict Gherkin, one story at a time. | `epics/<slug>/stories/NN-<story>.md` |

## How the pieces connect

- **Release type** is MVP or Normal. It is set on the epic and every story inherits it. MVP means the smallest end-to-end slice and lighter acceptance criteria; Normal means full coverage. See `release-types.md`.
- **IDs:** the epic numbers its Business Requirements `BR-1…` and Logging items `LOG-1…`. Stories list the IDs they cover, and each Gherkin scenario is tagged with the BR it proves. Each skill checks coverage at the end.
- **Stories** have seven sections: Story, Requirements, Implementation notes, Logging, Acceptance criteria, Testing notes, Closure checklist. The three engineering sections are left as `_Engineering to complete._`

## Guardrails used across the skills

- **What, not how** (`what-not-how.md`): requirements and Gherkin describe behaviour, rules and targets, never technology, schemas, APIs or architecture. Real constraints go in the epic's dependencies with their reason. Used by epic-writer, story-breakdown and story-writer.
- **Scope creep** (`scope-creep.md`): the core test ("without it, does the user still get the core outcome?") and a list of warning signs. Used by epic-writer, epic-splitter (to draw the MVP line) and story-breakdown.

## Changing the templates

The epic and story formats live only in their templates: `epic-writer/epic-template.md` and `story-writer/story-template.md`. The skills read the template each time they run and follow its sections, order, headings and per-section guidance. They do not keep their own copy, so you can add, remove, rename or reorder sections by editing the template alone.

- Each section's instructions sit in a `<!-- GUIDE: ... -->` comment under its heading. Edit the GUIDE to change how that section is written. GUIDE comments never appear in the output.
- In the story template, a GUIDE of `placeholder` means the section is left for engineering with the text shown.
- Cross-section checks for the epic are in a GUIDE block at the top of the epic template.
- Each template has a short **contract** at the top: the few things other skills depend on (release type, `BR-n` and `LOG-n` IDs, Gherkin acceptance criteria tagged `@BR-n`, a user story, a parking lot). Change anything else freely; if you change a contract item, check the other skills too.
- The examples show the expected quality, not the structure. If you change a template, the skills still follow the template, but update the examples when convenient so they don't teach the old shape.

## Setup

Each skill folder is self-contained: its `SKILL.md` plus every reference file and example it needs. Move a folder wherever your system needs it, keeping the files together.

- **If your system uses Claude Code-style skills:** put each folder in its skills directory. The `name` and `description` at the top of each `SKILL.md` are what the system uses to pick the skill.
- **If it doesn't:** use `SKILL.md` as the instructions and attach the other files in the same folder as reference material.

### Before first use

1. **Product overview.** `product-overview.md` (in `epic-writer/` and `story-writer/`) is a blank template: product summary, users, current capabilities, technology and platform, integrations, constraints, analytics, product terms and roadmap. Fill it in once per product, and keep both copies identical. Each section has a GUIDE comment saying what to put there. If you work on more than one product, keep one filled-in copy per product and swap it in.
2. **Split mode.** In `epic-splitter/SKILL.md`, under Settings, `split_mode` is `parent` (keep the original epic as a parent). Change it to `replace` if the team decides the children should replace the original. The PM can also name the mode when running the skill.
3. **Output folder.** All skills write under `epics/` in the current working folder. Change the Settings line in each skill if you want somewhere else.

### Shared files are copies

To keep folders self-contained, some reference files appear in more than one folder. If you edit one, update every copy:

- `writing-guide.md`: epic-writer, story-writer
- `gherkin-rules.md`: epic-writer, story-writer
- `release-types.md`: all four skills
- `product-overview.md`: epic-writer, story-writer
- `examples/example-epic.md`: epic-writer, story-breakdown
- `examples/example-story-list.md`: story-breakdown, story-writer
- `what-not-how.md`: epic-writer, story-breakdown, story-writer
- `scope-creep.md`: epic-writer, epic-splitter, story-breakdown

## First run checklist

1. Run `epic-writer` on a small, real feature. Check it asks for Release Type first and stops after each section.
2. Run `story-breakdown` on the saved epic. Check the coverage list.
3. Run `story-writer` for one story. **Paste the file into a JIRA story** and check the headings, bullets and the Gherkin code block come through. If anything breaks, adjust `story-template.md` in `story-writer/`.
4. If Gherkin feels too heavy, lower the MVP coverage in `release-types.md` and `gherkin-rules.md` before dropping Gherkin.

## Sources

- `epic-writer` is ported from Andrew's Feature Writer Custom GPT (github.com/dempseydata/PromptsAndGPTs, Feature Writer folder), with Release Type changed to MVP/Normal, numbered requirement and logging IDs, Gherkin acceptance criteria and a size check added.
- The methods behind the other skills: story mapping (Jeff Patton), the nine story-splitting patterns (Richard Lawrence and Peter Green, Humanizing Work) and the INVEST criteria (Bill Wake).
