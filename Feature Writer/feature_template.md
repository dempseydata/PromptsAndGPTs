# 🧩 Feature Template: LLMChat Feature Definition

This template structures **Epic/Feature-level product ideas** into a clear, outcome-driven format — ready for story breakdown by engineering and design.

It is designed for **section-by-section collaboration between a PM and a GPT-based co-pilot**. The GPT acts as a thinking and writing partner — asking clarifying questions, suggesting better phrasing, and helping refine feature logic.

This document is intended to be iterated, not completed in one shot.

---

## 1. **User Story**

**Format:**  
_As a [user type], when I [trigger/context], I want to [action], so that [goal/value]._

**Purpose:**  
Capture the user’s need, the context, and the value in one sentence.

✅ Clarify if the task is vague, overly technical, or lacks a user type  
✅ If appropriate, offer alternative phrasing  
🔸 Ask: *What problem are they solving? What’s the larger value?*

---

## 2. **Release Type**

What stage is this feature targeting?

- **POC** – Internal-only proof of concept to validate feasibility  
- **Alpha** – Limited-function release for internal feedback  
- **Beta** – User-facing but not final; used to gather validation or early feedback  
- **GA** – Full release to all users, production-ready

**Guidance:**  
✅ Choose based on readiness and feedback goals  
✅ It's common to pair Beta with a GA plan  
✅ Include a short rationale for the stage chosen  

🔸 Ask: *Is this intended for early validation or a full rollout?*  
🔸 Ask: *Will users interact with this at this stage?*

---

## 3. **Business Requirements**

**WHAT this feature must achieve and WHY.**

✅ Focus on outcomes, not UI or implementation  
✅ Note IN vs. OUT of scope for this release  
✅ End with the WHY: who benefits, and how

💡 Optional:  
> _Success = [measurable impact, workflow improvement, or outcome]_

🔸 Ask: *What happens if we don’t ship this?*  
🔸 Ask: *What does success look like in practice?*

---

## 4. **Assumptions & Dependencies**

List any key assumptions or dependencies, such as:

- External systems or APIs  
- Design readiness  
- Technical gating conditions  
- Known risks or upstream blockers

✅ Call out cross-team, integration, or architectural dependencies

🔸 Ask: *What must be true for this to succeed?*  
🔸 Ask: *What needs to be ready before this can begin?*  
🔸 Ask: *What could delay or block this if proven false?*

---

## 5. **Foundational Research**

Choose one or more:
- No research needed  
- Discovery / Journey Mapping  
- Competitive UX Pattern Research  
- Technology / Architecture Scan

✅ Research is often needed for novel UX, unknown user segments, or new domains  
🔸 Ask: *Is this something we’ve seen or done before?*

---

## 6. **UX Design Needs**

Select all that apply:
- No design needed  
- Low-fi wireframe (for exploration/ideation)  
- Mid-fi design (required for user-facing work)  
- High-fi design (for polish or clarity)  
- Interactive prototype (for testing or handoff)

**Guidance:**  
Don’t assume design fidelity based on release stage.

- **Low-fi** is for internal exploration and early collaboration  
- **Mid- or High-fi** is expected for **any user-facing flows** (Alpha to GA)  
- **Prototypes** help test usability or clarify flows

✅ Create design artifacts before implementation  
✅ Choose the minimal artifact that supports confident development

🔸 Ask: *What design input is needed to make decisions or move forward?*  
🔸 Ask: *Does this impact UX enough to require visual exploration?*

---

## 7. **Logging Plan & Measuring Impact**

Split into:
- **Data to Capture** – Key user/system actions, metadata, flags  
- **Metrics to Derive** – What signals indicate success or failure?

**Guidance:**  
Use these lenses to guide metric thinking:

- **Usage** – Are people finding/triggering the feature? (e.g., # activations, # users)  
- **Engagement** – Are they using it meaningfully? (e.g., task completion, depth)  
- **Retention** – Do they return or repeat usage?  
- **Abandonment** – Are users dropping off, bouncing, or ignoring the feature?

✅ Specify what’s logged today vs. what must be added  
✅ Focus on signals of behavior, not vanity metrics  
✅ Prioritize 1–2 metrics that match the feature’s goals

🔸 Ask: *What would tell us this feature is working?*  
🔸 Ask: *What behavior would signal friction, confusion, or failure?*

---

## 8. **System Diagram Needs**

Choose one:
- Minor or no impact  
- System diagram update needed  
- Tech Wiki update needed

✅ Update diagram if adding tools, APIs, or agents  
✅ Update Tech Wiki if changing data flows or system behaviors

🔸 Ask: *Would this change how a new dev understands the system?*

---

## 9. **Acceptance Criteria**

Break into 4 lists:
- **User Facing** — _As a user, I can…_  
- **Back End** — _The system should…_  
- **Logging** — _The product must capture…_  
- **Regression** — _The product should still…_

✅ Should be clear, testable, and aligned to the business need  
✅ GPT can offer phrasing suggestions if PM input is unclear

🔸 Ask: *Would you like help turning that into a testable statement?*  
🔸 Ask: *What would QA or PM use to validate this?*

---

## 10. **Iteration Parking Lot (Unresolved Items)**

Use this section to note:
- Decisions still pending  
- Risky or unknown elements  
- Items deferred to a later release

✅ Great for Alpha/Beta stages where discovery continues  
🔸 Ask: *What’s still fuzzy or in flux?*  
🔸 Ask: *What do we expect to refine later?*

---

### ✅ Usage Tips

- This template is meant for **collaboration with a GPT co-pilot**. The GPT will prompt, clarify, and help refine each section — it’s not a one-shot generator.  
- You don’t have to finish everything in one pass. Write what’s clear, then iterate.  
- Always align with actual user value, not perceived completeness.

---

## 📘 Appendix: Beta Types (Reference Only)

If selecting a **Beta** release, you may clarify the intent using one of these categories:

- **Usability Beta** – Invite-only. Performed in test environments or structured sessions. Focus is on UX and workflow validation.  
- **Closed Beta** – Invite-only on production. Used for early exposure and feedback from trusted users.  
- **Open Beta** – Available to all users but clearly marked as pre-release. Used to gather large-scale feedback or monitor at-scale issues.

📝 Choose based on **feedback goals and risk**, not by default. These may evolve over time.
