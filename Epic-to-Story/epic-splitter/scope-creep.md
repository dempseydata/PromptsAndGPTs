# Scope creep checks

Most epics carry more than they need. Use these checks whenever a requirement, story or slice is added, and again at review. The aim is not to refuse ideas: it is to put each one in the right place (this epic, a later Normal epic, or the parking lot) on purpose.

## The core test

For any requirement, story or slice, ask both:

1. **Without it, can the user still get the epic's core outcome?** (the "So that" in the user story, and the success target)
2. **For an Inferred need: without it, can we still test the Bet?**

If both answers are yes, it is not core. For an **MVP**, it goes to the parking lot or a later Normal epic. For a **Normal** release, ask the PM whether it earns its place in this release or should wait.

A second test: **Day one or day one hundred?** Is this needed the first day someone uses the feature, or only once many people use it a lot?

## Warning signs

Flag any of these and ask the PM whether it belongs in this epic:

- **"While we're at it…"**: an addition that is not part of the problem being solved
- **Admin, settings and configuration** screens before the core feature has proven itself
- **Analytics dashboards** before there is data worth looking at (logging the events is fine; building the dashboard can wait)
- **Several user types or roles** when one would prove the value
- **Several integrations** when one would prove the concept
- **Several formats, channels or platforms** when one would do (offer the simplest first)
- **Polish ahead of value**: onboarding tours, animations, theming, customisation
- **Scale before fit**: building for volumes the product does not have yet
- **Retention features before adoption is proven**: notifications, streaks, reminders
- **Edge-case handling in an MVP** that belongs in the Normal release (see release-types.md)
- **A requirement no success measure depends on**
- **A requirement no one asked for and no problem in the epic explains**

## How to raise it

Name the item, the warning sign and the cheaper option, then let the PM decide:

"BR-6 (team sharing) looks like scope creep for an MVP: the analyst can still share findings with export alone. Park it for a later Normal epic, or keep it?"

Record the decision. Parked items go to the parking lot with a reason, so they are not lost and do not come back unexamined.

## What is not scope creep

- Error handling and failure states that the core outcome needs (an export that fails silently is not a working export)
- Logging that the success measures depend on
- Accessibility and security obligations
- Requirements the PM has explicitly confirmed as core after this check
