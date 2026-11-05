# Epic template

This file is the single source for the epic's structure. The skills read it at run time; they do not hold their own copy of the sections. To change the epic format, edit this file only.

## How to read this file

- The skeleton is the block between `<!-- TEMPLATE START -->` and `<!-- TEMPLATE END -->`. Write sections in the order they appear there, using the headings as written.
- Lines inside `<!-- GUIDE: ... -->` comments are instructions for that section. Follow them. **Never copy GUIDE comments into the finished epic.**
- `<angle brackets>` are placeholders to replace.
- A section whose GUIDE says `optional` can be left as "None", but keep its heading.

## Contract: what other skills rely on

Change anything else freely. If you change one of these, also check epic-splitter, story-breakdown and story-writer:

- A **release type** field with the value `MVP` or `Normal`, and a **parent epic** field.
- **Requirements** with IDs `BR-1`, `BR-2`, …
- **Logging items** with IDs `LOG-1`, `LOG-2`, …
- **Acceptance criteria** as a fenced `gherkin` block, scenarios tagged with `@BR-n`.
- A **user story** that names the persona.
- An **open questions / parking lot** section.

## Cross-section checks

<!-- GUIDE: Run these as each section is drafted. When something does not match, ask; never assume it is a mistake: "That doesn't match what we defined earlier. Is that intentional, or should we adjust it?"
- Requirements that imply a user-facing change are covered in UX Design Needs.
- Success targets in Why This Epic are measured in Logging & Analytics.
- Every BR has at least one acceptance criteria scenario.
- Dependencies named in requirements are listed in Dependencies.
- Release type MVP: anything beyond the core outcome sits in the Parking Lot, not in Business Requirements.
- Inferred need: the Bet's core assumption is in Assumptions, and Logging & Analytics measures the Success signals for the pain, not only adoption.
- The User Story still matches the problem framing in Why This Epic. If the framing changed who has the problem or why, offer to revise the User Story.
- Every BR states what and why, not how (what-not-how.md). Real technical constraints go in Dependencies with their reason.
- Every BR passes the scope-creep checks (scope-creep.md). For an MVP, offer to park anything that fails the core test.
- Overlap between Business Requirements and Acceptance Criteria is expected. Missing coverage is not. -->

<!-- TEMPLATE START -->

````markdown
# <Epic title>

## 1. User Story
<!-- GUIDE: Four lines: As a / When / I want / So that. "As a" is a specific role or persona, not "user". "So that" is an outcome, not a restatement of "I want". -->
As a <role or persona>
When <situation or trigger>
I want <capability or action>
So that <goal, value or outcome>

## 2. Why This Epic
<!-- GUIDE: Frame the problem before any solution. Work through it in this order, one or two questions at a time:
1. Need type. Ask: "Are users asking for this, or is this something we believe they need but aren't asking for?" Record Requested or Inferred.
2. Problem framing (I am / Trying to / But / Because / Which makes me feel), from the user's point of view.
3. Context & constraints, Evidence, then the one-sentence Problem statement.
4. Bet (Inferred only), then Success.

Rules for every epic:
- No solution in the problem. The framing, evidence and problem statement must not name the feature. "Users lack skills" or "users need a dashboard" is a solution in disguise; ask what they are trying to do and what stops them.
- A user problem, not a business symptom. "Revenue is down" is not a user problem; ask which users are struggling with what.
- Root cause, not symptom. Push on "Because" until it explains why the barrier exists.
- Feelings come from research. If there is no evidence for "Which makes me feel", write <TBD: needs research> and add it to Open Questions. Never invent emotions, quotes or numbers.

Extra rules for Inferred needs (users are not asking for this feature but show the underlying pain):
- "But" and "Because" describe the pains users do express or show (for example distrust of AI, inconsistent results, fear of being replaced), in their words. Never claim users asked for the feature.
- Evidence is evidence of the pain, not of demand. Label it "signals of the problem".
- The Bet is the only place the capability is named. It says how the capability addresses each pain and what change would prove it.
- Success measures the pain moving (trust, consistency, time on low-value work), not only adoption.
- Add the Bet's core assumption to Assumptions.
- For an MVP, include at least one early signal that shows whether the Bet is right.

Examples: examples/example-epic.md (Requested), examples/example-why-inferred.md (Inferred). -->
**Need type:** Requested | Inferred

**Problem framing**
- **I am:** <the persona, with 2–3 relevant characteristics>
- **Trying to:** <the outcomes they care about>
- **But:** <what gets in the way, in the user's own terms>
- **Because:** <the root cause, not the symptom>
- **Which makes me feel:** <the emotional impact, from research>

**Context & constraints:** <technical, time, location or audience limits that shape the problem>

**Evidence:** <interviews, tickets, data, observed behaviour, with sources>

**Problem statement:** <Persona> needs a way to <outcome> because <root cause>, which currently <impact>.

**Bet (Inferred only):** We believe <capability> addresses <the observed pains> because <reason>. We will know we are right when <measurable change in the pain itself>.

**Success:** <measurable target, with a time frame>

## 3. Key Terms
<!-- GUIDE: optional. Add terms as they come up in any section: new, ambiguous or important words. Review the list in the final review. -->
- **<Term>:** <definition>

## 4. Release Type
<!-- GUIDE: Ask for the release type before any other section if it is not already known, because it sets the depth of every section (see release-types.md). Fill in the rest of this section when you reach it in order. If this epic came from a split, the parent epic is already filled in. -->
- **Release type:** MVP | Normal
- **Parent epic:** <slug, or "None">
- **User group:** <who gets it>
- **Rollout plan:** <how it reaches them>
- **Support expectations:** <who supports it and how>

## 5. Business Requirements
<!-- GUIDE: Number as BR-1, BR-2, … in order. Each is one testable SHALL statement about an outcome. Never renumber an ID once written; if one is removed, keep the ID and mark it (removed).
What, not how: state behaviour, rules and targets; never technology, schemas, APIs or architecture (see what-not-how.md). If the PM gives a "how", point it out, suggest the "what" version, and ask whether it is a real constraint.
Scope: run each new BR through the core test in scope-creep.md. Raise any warning sign before moving on. -->
- **BR-1:** The system SHALL <testable, outcome-focused requirement>.

## 6. Assumptions
<!-- GUIDE: What must be true for this epic to succeed. For an Inferred need, include the Bet's core assumption. -->
- <assumption>

## 7. Dependencies
<!-- GUIDE: Systems, teams, APIs, data sources, agents or tools this epic relies on. Also record real technical constraints here, each with its reason ("Must use company SSO: security policy"). A preference is not a constraint. -->
- <dependency>

## 8. Foundational Research
<!-- GUIDE: Research, competitive analysis, prototypes or best practice that informed this epic, with sources. -->
- <research and source>

## 9. UX Design Needs
<!-- GUIDE: Interactions, flows, exact UI text for messages and errors, empty states, accessibility, mobile/desktop concerns, links to designs. -->
- <design need>

## 10. Logging & Analytics
<!-- GUIDE: Number as LOG-1, LOG-2, … Each item says what is recorded and who uses it. Then say who can access the data and who monitors it. Every Success measure in Why This Epic needs a LOG item. -->
- **LOG-1:** <event or metric> — <what it records> — <who uses it and why>
- **Access:** <who can see this data>
- **Monitoring:** <how success and failure are watched, and by whom>

## 11. Acceptance Criteria
<!-- GUIDE: Gherkin following gherkin-rules.md, at epic level (3–6 scenarios). Tag each scenario with the BR it proves. Every BR has at least one scenario. -->
```gherkin
<epic-level scenarios>
```

## 12. Open Questions & Parking Lot
<!-- GUIDE: Open questions with an owner. Parking Lot items with why they were deferred and where they might go. Offer to park any early, fuzzy or undecided idea that comes up in any section. -->
- **Open question:** <question> — Owner: <name or role>
- **Parking Lot:** <deferred idea> — <why deferred, and where it might go>

## 13. Out of Scope
<!-- GUIDE: optional. Goals, requirements or edge cases this epic will not address. -->
- <out of scope item>
````

<!-- TEMPLATE END -->
