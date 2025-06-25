# 🧩 Feature Template: LLMChat Feature Definition

This template is used to structure product features in a clear, outcome-driven format that aligns engineering, UX, and strategic goals.

Proceed in the following order unless the feature is already partially complete.

---

## 1. **User Story**

**Format:**  
_As a [user type], when I [trigger/context], I want to [action], so that [goal/value]._

**Purpose:**  
Capture the user's intent, context, and benefit in a single sentence.

✅ Clarify if the task is vague, overly technical, or lacks a user type  
✅ If appropriate, offer alternative phrasings  
🔸 Ask: *What problem are they solving? What’s the larger value?*

---

## 2. **Release Type**

Generally speaking, a feature will focus on one release type:
- **POC**: An internal team-only demo or write up that focuses on the core capabilities required for later releases. The goal is to verify the feasibility of the feature
- **Alpha**: A subset of capabilities on a system for interactive testing by the internal team, and (optionally) a small number of select users. An Alpha does not need to scale beyond the internal team size.
- **Beta**: An almost fully functional version of the feature, accessible to users. Beta comes in 3 flavors: (1) "Usability Beta" - Invite only on a non-production system in order to perform usability testing (limited time access, moderated feedback session) prior to release, (2) "Closed Beta" - Invite only on the production system for a subset of users, followed up with feedback gathering sessions, (c) "Open Beta" - Accessible to all users to gather a broader set of feedback. With Beta, bugs and usability issues are expected, and is a good way to vet the 'final feature' prior to GA in order to fix any bugs etc.
- **GA**: Full functionality released to all users with no constraints

**Guidance:**  
✅ Include rationale for stage chosen
✅ Multiple stages OK, especially for net-new features  
✅ A Beta release will often be paired with GA release
🔸 Prompt if unclear: *Is this intended as an Alpha or a Usability Beta?*

---

## 3. **Business Requirements**

**WHAT this feature must achieve and WHY.**

✅ Focus on outcomes and business logic  
✅ Avoid UI or implementation details  
✅ Prompt for what’s IN vs. OUT of scope for this release
✅ The last part of the requirements must be the WHY of the feature. Who does the feature benefit, and what value or impact will this feature provide

🔸 Ask: *What happens if we don’t ship this? What does success look like?*
🔸 Ask: *How does this feature benefit the target users?*

---

## 4. **Assumptions & Dependencies**

List key technical, business, or behavioral assumptions. Include:

- External system dependencies  
- Required design readiness  
- Feature gating conditions

✅ Identify cross-team or architecture links  

🔸 Ask: *What must be true for this feature to succeed?*
🔸 Ask: *What must be true for work on this feature to start?*
🔸 Ask: *What risks blocking this feature if proven false?*

---

## 5. **Foundational Research**

Choose one or more:
- No research needed  
- Discovery / Journey Mapping  
- Competitive UX Pattern Research  
- Technology/Architecture Scan

✅ Required for novel capabilities, new user types, or domain-specific UX
🔸 Ask: *Is this something we’ve seen or done before?*

---

## 6. **UX Design Needs**

Select all that apply:
- No design needed  
- Low-fi wireframe  
- Mid-fi design  
- High-fi design  
- Interactive prototype

**Guidance by release stage:**
- **POC** → Should include UX design involvement to produce a low-fi wireframe as an output
- **Alpha/Beta/GA** → Needs a mid-fi or better, depending on the extent of the expected changes. A Minor UX change only needs a mid-fi design, but larger changes will need a high-fi design, and more complex features would benefit from an interactive prototype


✅ UX designs are required before Alpha, Beta or GA releases
✅ UX designs are required before implementation work can begin
 
🔸 Ask: *What is the expected impact on the current UX?*
🔸 Ask: *What is the simplest design artifact needed to test this?*

---

## 7. **Logging Plan & Measuring Impact**

Split into:
- **Data to Capture** (user/system actions, metadata)
- **Metrics to Derive** (adoption, success rate, abandonment)

✅ Include what’s logged now vs. what needs to be added
✅ Focus on what actions and supporting metadata need to be captured
🔸 Ask: *What does success look like in data?*

---

## 8. **System Diagram Needs**

Choose one:
- Minor/no impact  
- System diagram update  
- Tech Wiki update

✅ Diagram update only required if new tools, APIs, or agents are added  
✅ Tech wiki update required if process flow or data structures are changing

🔸 Ask: *Would this affect dev onboarding or architecture understanding?*

---

## 9. **Acceptance Criteria**

Split into 4 lists:
- **User Facing** — _As a user, I can…_  
- **Back End** — _The product should…_  
- **Logging** — _The metadata must…_  
- **Regression** — _The product should still…_

✅ Should be testable, clear, and tied to requirements  
🔸 Ask: *What would QA or PM use to verify this?*

---

## 10. **Open Questions / Unresolved Items**

Optional section.

Use this to capture:
- Decisions still pending  
- External clarifications needed  
- Items deferred to a follow-on release

✅ Often useful for Alpha/Beta handoffs  
🔸 Ask: *What’s still fuzzy, risky, or open-ended?*

---

**Usage Tips:**
- Each section can be revised iteratively  
- When vague inputs are given, treat them as starting points  
- Always validate feature logic against product stage, user need, and technical reality

