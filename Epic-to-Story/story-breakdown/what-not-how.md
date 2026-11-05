# What, not how

Epics and stories say **what** the product must do and **why**. Engineering decides **how**. A requirement or acceptance criterion that prescribes the implementation takes that decision away from the people best placed to make it, and often locks in a worse answer.

## Specify (what and why)

- User-facing behaviour: what the user can do, see and expect
- Business rules and policies
- Data the user needs to see or provide, and where it comes from
- Targets: time limits, volumes, availability, accuracy
- Security, privacy, compliance and accessibility obligations
- Exact UI text where wording matters (messages, labels, errors)

## Don't specify (how)

- Technology, frameworks, languages or libraries
- UI component choices and animation details
- Database tables, schemas or storage choices
- API design, endpoints or payload shapes
- Architecture, services, queues or caching approaches
- Algorithms or code structure

## The one exception: real constraints

If the "how" is genuinely fixed by something outside the team, state it as a constraint **with its reason**, in the epic's dependencies or constraints, not as a requirement:

- "Must use the company SSO provider (security policy)."
- "Must store data in the EU region (GDPR commitment to customers)."

A preference is not a constraint. "We usually use Redis" is not a reason.

## How to fix a "how" statement

Ask what outcome the "how" was meant to achieve, and write that instead.

- ✗ "Cache API responses in Redis for 5 minutes."
  ✓ "The system SHALL show the dashboard within 1 second of opening it. Data shown SHALL be no more than 5 minutes old."
- ✗ "Add a React dropdown that stores the selection in global state."
  ✓ "The user SHALL be able to choose one option from the list. The chosen option SHALL stay selected on later screens and after a page refresh."
- ✗ "Then the export service writes a row to the exports table."
  ✓ "Then the export appears in the user's export history."

## Where this applies

- Business requirements in the epic, and requirements in each story
- Every Gherkin step: Given, When and Then describe what a user or tester can observe, never internal mechanics
- Story titles and story list entries

Sections reserved for engineering (such as implementation notes) are where the "how" belongs. Never fill them in for engineering.

When you spot a "how", don't silently rewrite it. Point it out, suggest the "what" version, and ask whether it is a real constraint.
