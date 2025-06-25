# 🧩 Feature Template: LLMChat Feature Definition

This template is used to structure product features in a clear, outcome-driven format that aligns engineering, UX, and strategic goals.

Proceed in the following order unless the feature is already partially complete.

---

## 1. **User Story**

**Format:**  
_As a [type of user], when I [scenario], I want to [task], so that [desired result]._

**Purpose:**  
Capture the user's intent, context, and benefit in a single sentence.

✅ Clarify if the task is vague, overly technical, or lacks a user type  
🔸 Ask: *What problem are they solving? What’s the larger value?*

---

## 2. **Release Type**

Choose one or more:
- **POC**: internal team-only, low-UX validation
- **Alpha**: dev demo for select users, low scale
- **Beta**: MVP for broader user feedback
- **GA**: production-ready with polish and support

**Guidance:**  
✅ Include rationale for stage  
✅ Multiple stages OK, especially for net-new features  
🔸 Prompt if unclear: *Is this intended as a fast test or first public version?*

---

## 3. **Business Requirements**

**What this feature must achieve and why.**

✅ Focus on outcomes and business logic  
✅ Avoid UI or implementation details  
✅ Prompt for what’s IN vs. OUT of scope for this release

🔸 Ask: *What happens if we don’t ship this? What does success look like?*

---

## 4. **Assumptions & Dependencies**

List key technical, business, or behavioral assumptions. Include:

- External system dependencies  
- Required design readiness  
- Feature gating conditions

✅ Identify cross-team or architecture links  
🔸 Ask: *What must be true for this to work?*

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
- **POC/Alpha** → wireframes or low-fi are often sufficient  
- **Beta/GA** → needs mid-fi or better

🔸 Ask: *What’s the simplest design artifact needed to test this?*

---

## 7. **Logging Plan & Measuring Impact**

Split into:
- **Data to Capture** (user/system actions, metadata)
- **Metrics to Derive** (adoption, success rate, abandonment)

✅ Include what’s logged now vs. what needs to be added  
🔸 Ask: *What does success look like in data?*

---

## 8. **System Diagram Needs**

Choose one:
- Minor/no impact  
- System diagram update  
- Tech Wiki update

✅ Required if new tools, APIs, or agents are added  
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

