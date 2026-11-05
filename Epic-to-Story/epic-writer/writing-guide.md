# 📚 Feature Writing Guide

*Amazon-Style, Enhanced with AWS Narrative Principles*

---

## 1. **Problem-First, Outcome-Driven**

* **Start with the problem:** Clearly state the user/business pain or unmet need before describing the solution.

  * *Weak:* “We should add an export button.”
  * *Strong:* “Researchers cannot easily share session outputs with colleagues, causing rework and frustration. An export button will allow seamless sharing, reducing manual copy-paste effort.”
* **Define the successful outcome:**

  * *Strong:* “When this feature launches, 90% of users will successfully export a transcript on their first attempt.”

---

## 2. **Be Unambiguous and Testable**

* **Use measurable criteria and binary language.**

  * *Weak:* “System should be fast.”
  * *Strong:* “System SHALL return search results within 2 seconds for 99% of queries.”
* **All acceptance criteria MUST be verifiable.**

  * Use Given/When/Then or checklist formats.

---

## 3. **Active Voice, Clear Ownership**

* Assign ownership wherever possible.

  * *Weak:* “Logs are reviewed weekly.”
  * *Strong:* “The Analytics team reviews system logs every Friday and files issues in Jira.”
* Avoid “should,” “could,” “would like,” “might,” or passive voice.

---

## 4. **Conciseness and Structure**

* **Bullets > prose:**

  * Use bulleted or numbered lists for requirements, assumptions, and dependencies.
* **No filler:**

  * Remove unnecessary adjectives/adverbs (“simply,” “very,” “just,” etc.).
* **Consistent section formatting:**

  * Each section follows the template structure (User Story, Requirements, etc.).

---

## 5. **Data and Evidence-Driven**

* Reference facts, numbers, user feedback, or benchmarks wherever possible.

  * *Strong:* “In user interviews, 4/5 participants cited missing export as a top pain point.”

---

## 6. **Acceptance Criteria Format**

* Use Given/When/Then:

  * *Given a logged-in user,
  * *When they click 'Export',
  * *Then the system generates a .txt file within 2 seconds.

* Include negative/edge cases, backend requirements, and logging coverage.

---

## 7. **Security, Compliance, and Accessibility**

* Explicitly call out:

  * Who can access what data
  * What data is logged, stored, or transmitted
  * Which standards or regulatory requirements apply

---

## 8. **Parking Lot Items**

* Clearly label non-blocking, speculative, or deferred ideas as “Parking Lot.”

  * *“Potential extension: allow export to PDF. Out of scope for MVP.”*

---

## 9. **Checklist for Review**

* [ ] Every requirement is testable
* [ ] Problem and outcome are clear
* [ ] No passive or ambiguous language
* [ ] All numbers/facts are cited or sourced
* [ ] Acceptance criteria covers positive and negative flows
* [ ] Security, compliance, accessibility are addressed

---

## 10. **Words and Phrases to Avoid (“Weasel Words”)**

These words create ambiguity, reduce accountability, or signal uncertainty. Replace them with **clear, testable, and direct language**.

**Common Weasel Words:**

* should
* could
* would like to
* might
* may (unless regulatory, e.g., “may not store PII”)
* try to / attempt to
* probably / possibly
* ideally / preferably / as appropriate
* best effort / where feasible
* soon / ASAP / quickly / timely
* easily / simply / just / very / really
* generally / typically / often
* in some cases / where necessary / as needed

**Example rewrites:**

| Weasel Version                        | Amazon-Style Rewrite                              |
| ------------------------------------- | ------------------------------------------------- |
| “System should load results quickly.” | “System SHALL return results in under 2 seconds.” |
| “Logs may be reviewed regularly.”     | “The Analytics team reviews logs weekly.”         |
| “Ideally, users are notified.”        | “System SHALL notify users within 1 minute of X.” |
| “Feature is available ASAP.”          | “Feature is available to all users by July 15.”   |

> **Tip:** If you find yourself writing with uncertainty or open-ended phrases, ask:
>
> * Who owns the action?
> * How is success/failure measured?
> * When is the action done or the requirement satisfied?

---

## 11. **Sentence Structure & Rhythm**

*Inspired by AWS Narrative Principles*

* **Vary your sentence length** to create engagement and avoid monotony.

  * Short sentences emphasize.
  * Longer sentences add nuance, detail, or build energy.
* **Mix structure:** Use both simple and complex sentences for rhythm.
* **Read aloud:** Ensure your writing “sounds right”—no long monotonous blocks.
* Avoid “wall of text” prose; break up content with lists and spacing.

---

## 12. **Headlines and Calls to Action (CTAs)**

*Inspired by AWS Template*

* **Start with a headline** or summary that instantly communicates “why this matters.”
* **Craft direct, actionable CTAs:**

  * *Weak:* “Click here.”
  * *Strong:* “Start exploring your new dashboard.”
* Each update, requirement, or announcement should answer: “So what? What do I do next?”

---

## 13. **Examples: Strong vs. Weak Writing**

| Weak Example                         | Amazon-Style Rewrite                                                                             |
| ------------------------------------ | ------------------------------------------------------------------------------------------------ |
| “Should improve system reliability.” | “System SHALL maintain 99.9% uptime, measured monthly.”                                          |
| “Add dark mode.”                     | “Add dark mode so users working at night reduce eye strain; 60% adoption target within 1 month.” |
| “Logs are accessible.”               | “Only SRE team members SHALL access audit logs; access is logged and reviewed quarterly.”        |

---

**Use this guide as the standard for all feature specs, RFCs, and product communications. For questions, reach out to the product leadership team.**
