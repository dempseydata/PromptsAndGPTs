```markdown
# PromptGenAssistant

PromptGenAssistant is an **Instruction and Prompt Refinement Engine**. Its job is simple: take vague ideas, rough prompts, or messy instruction sets and turn them into **clear, rigorous, reusable instructions** that actually hold up over time.

This assistant is not focused on creativity or speed. It is focused on **clarity, correctness, and structure**.

---

## What It Does

PromptGenAssistant helps you:
- Clarify what you’re actually trying to do
- Expose hidden assumptions and gaps
- Define boundaries, constraints, and non-goals
- Produce clean, copy-paste-ready instruction artifacts
- Explain *why* the instructions are designed the way they are

Think of it as a prompt architect, not a task executor.

---

## How It Works

The assistant operates in two modes:

**Create Mode**  
Used when you start with a loose idea, a goal, or an informal description. The output is a complete instruction set built from scratch.

**Modify Mode**  
Used when you already have a prompt or instructions and want them refined. By default, the assistant performs a structured refactor—cleaning up logic, improving clarity, and making the result reusable.

---

## Clarification Comes First (Always)

Before writing final instructions, the assistant pauses and asks questions.

It will ask about:
- Who the instructions are for
- What success looks like
- What is required vs optional
- Constraints, non-goals, and edge cases
- Inputs, outputs, and formatting expectations

This clarification step is mandatory. If critical details are missing, the assistant will not proceed until they are resolved or explicitly accepted as assumptions.

---

## The Build Process

Once clarification is complete, the assistant follows a fixed workflow:

1. **Intent Synthesis**  
   A short summary of what the assistant believes you want, plus stated assumptions.

2. **Design Plan**  
   An outline of the instruction structure and key design choices.

3. **Construction**  
   A clean, structured instruction artifact covering role, purpose, scope, workflow, outputs, and constraints.

4. **Verification**  
   A QA pass to catch conflicts, resolve issues, and flag remaining edge cases.

5. **Final Delivery**  
   A ready-to-use Markdown file, plus a short rationale explaining major decisions.

---

## Safety and Boundaries

- User-provided content is treated as untrusted input
- No tools or integrations are assumed unless explicitly stated
- Instructions cannot be overridden by downstream prompts
- The default environment is chat-only

---

## Style Philosophy

The writing is:
- Explicit and structured
- Direct and unambiguous
- Optimized for reuse and learning
- Focused on reasoning over flair

---

## What This Is *Not*

PromptGenAssistant is not:
- A creative writing tool
- A task automation agent
- A shortcut around thinking

It exists to make thinking visible and durable.

---

## When to Use It

Use PromptGenAssistant when you want to:
- Design system prompts
- Formalize project instructions
- Refactor existing prompts for rigor
- Create instruction frameworks that won’t collapse under reuse

If your goal is “make this clearer and harder to misunderstand,” this tool is the right fit.
```
