# ✍️ Writing Style Guide for AI Feature Specifications

This file provides **examples and principles** to help ensure feature specs are:
- Problem-first
- Testable
- Structured by outcome
- Appropriate to the feature’s phase (e.g., Alpha vs. GA)

This guide is used by the GPT to validate and improve feature writing.

---

## ✅ General Style Principles

- Use **active voice** and assign clear ownership
- Frame around **user problems**, not UI actions
- Focus on **value and testability**
- Prefer **plain, direct language** (avoid fluffy or abstract terms)
- Align scope and precision with the **release stage** (e.g., Alpha = narrower)

---

## 💬 Good vs. Weak Phrasing

| ❌ Weak / Vague | ✅ Improved & Testable |
|----------------|------------------------|
| “Add a button to export results” | “As a user, I can export chart results to CSV so I can use them in external tools.” |
| “Track usage” | “Log each use of the DALL·E image generation tool, including timestamp, user type, and input prompt.” |
| “Improve the UX of the chart tool” | “Add tooltips to chart elements so users can see metric definitions on hover.” |
| “Support research workflows” | “Enable saving and resuming document-based Q&A sessions, allowing researchers to continue across sessions.” |
| “Let the user customize” | “Allow the user to choose between light and dark mode for document viewer panels.” |

---

## 🧩 Section-Specific Patterns

### **User Story**
> _As a [user type], when I [trigger/context], I want to [action], so that [goal/value]._

✅ Tie directly to a need or workflow  
✅ Avoid feature-first framing

---

### **Business Requirements**
❌ Don’t say:  
- “We want to use feature X”  
- “Implement dropdowns for filters”  

✅ Do say:  
- “The goal is to help users segment search results by metadata (e.g., source, date) so they can narrow focus on relevant papers.”

---

### **Logging & Metrics**
- **Data to Capture**: _“Log tool use with user type, prompt, and output metadata.”_  
- **Metric to Derive**: _“% of users who use the export feature more than once.”_

✅ Log the event  
✅ Metric derives behavior insight  
✅ Separate “loggable events” from “metrics derived later”

---

### **Acceptance Criteria (by type)**

#### User Facing
> _As a user, I can edit the image caption after generation._

#### Back End
> _The system should validate input before sending to DALL·E._

#### Logging
> _The metadata must capture the number of generation attempts per session._

#### Regression
> _The chart tool should still render previous chart types without error._

✅ Keep each line testable  
✅ Use consistent phrasing

---

## 🛑 Avoid These Pitfalls

- "The feature should work well" → Too vague
- "Let the model decide how to handle this" → Offloads too much control
- “Improve performance” → No testable definition
- “Enhance experience” → Say what’s better and how we’ll know

---

## 🧠 Use Cases Where Clarity Matters Most

- **New agentic tools** (e.g., researcher, charting): clarify inputs, expected actions, edge cases
- **Complex flows**: clearly describe what each step must do
- **POC or Alpha features**: under-specify **just enough** to validate, but not to build at scale

---

## 📌 How the GPT Should Use This

- Default to phrasing patterns from this guide when rewriting
- Compare user input to “good vs. weak” examples
- Suggest rewrites and explain *why*
- Use these to validate clarity, phase-fit, and testability

