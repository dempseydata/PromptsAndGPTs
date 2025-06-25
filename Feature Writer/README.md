# 🤖 LLMChat Feature Authoring GPT

This repository contains a **Custom GPT configuration and supporting templates** for defining high-quality, JIRA-style product features for **LLMChat** — a ChatGPT-style AI research assistant built on Chainlit, with integrated tools for:

- Document RAG  
- External research and internet search  
- AI image generation  
- Data visualization agents  
- Extendable AI agents (via MCP, A2A, etc.)

The GPT acts as a **strategic product co-pilot**, working alongside a senior PM to develop structured feature write-ups that support clear handoff to design and engineering.

---

## 🧠 What This GPT Does

- Works as an **iterative collaborator**, not a one-shot generator  
- Follows a structured, section-by-section **Feature Template**  
- Helps refine vague ideas into clear, testable, outcome-driven features  
- Maintains full session continuity across the entire feature  
- Flags mismatches, suggests improvements, and tracks unresolved items  
- Adapts responses based on the feature’s release phase (POC, Alpha, Beta, GA)

---

## 📁 Repository Structure

```bash
/
├── README.md                          # This file
├── gpt_instructions_llmchat.md       # GPT behavior and response logic
├── feature_template.md               # Feature structure used by GPT and PM
├── writing_examples_ai_features.md   # Writing standards and phrasing examples
├── llmchat_product_overview.md       # Product overview and architecture reference
```

⸻

🧩 Feature Template Overview

The feature_template.md provides a repeatable structure for documenting features, aligned to agile team needs:
	1.	User Story – Captures user context and intent
	2.	Release Type – POC, Alpha, Beta, or GA (brief guidance included)
	3.	Business Requirements – What it must achieve and why
	4.	Assumptions & Dependencies – Design, technical, external conditions
	5.	Foundational Research – Discovery, tech scan, or UX pattern needs
	6.	UX Design Needs – Lo-fi for ideation; Mid/Hi-fi required for user-facing flows
	7.	Logging & Metrics – Tracks usage, engagement, retention, abandonment
	8.	System Diagram Needs – Whether updates to architecture docs are needed
	9.	Acceptance Criteria – Structured into four categories
	10.	Iteration Parking Lot – Captures unknowns or follow-ups
	11.	Beta Types Appendix – Optional guidance for Closed, Usability, or Open Beta

⸻

✍️ Writing Standards

Use the examples in writing_examples_ai_features.md to:
	•	Write measurable, testable acceptance criteria
	•	Use active voice with clear ownership
	•	Avoid vague, passive, or overly technical phrasing
	•	Align expectations to user value and product phase

⸻

✅ How to Use This GPT
	1.	Load the GPT into ChatGPT’s Custom GPT environment
	2.	Ensure all .md knowledge files are uploaded as reference context
  3.  Update the llmchat_product_overview.md with an overview of your product and its capabilities
	3.	Begin a conversation with your feature idea
	4.	The GPT will guide you through each section of the template
	5.	Revise collaboratively and confirm before continuing
	6.	Use the output for JIRA Feature-level specs, ready for story breakdown

This GPT is designed to co-author, coach, and validate — not just write.

⸻

📌 License & Contribution

This project is intended for internal or personal productivity use.
Forks and adaptations for other products or organizations are welcome.

