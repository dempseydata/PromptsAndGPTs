# Example: Why This Epic for an Inferred need

Epic: **Skills support**. Users are not asking for "skills". They do say they don't trust the AI, that it does things differently each time, and that they worry about being replaced. The team believes skills address those pains.

Evidence counts are shown as placeholders (`<n>`) because this example is about structure. In a real epic, use real numbers and sources, or write `<TBD: owner>`.

```markdown
## 2. Why This Epic
**Need type:** Inferred

**Problem framing**
- **I am:** an analyst whose team works to standard operating procedures (SOPs) for research, reviews and reports
- **Trying to:** produce work my team can rely on, and spend my time on the judgement calls only I can make
- **But:** the AI does the same task differently each time, skips steps my SOP requires, and I end up redoing information gathering and document writing by hand
- **Because:** the assistant does not know my team's SOPs, so every request starts from scratch and the result depends on how I happened to phrase it
- **Which makes me feel:** unable to trust the AI with real work, and uneasy that it is being positioned to replace me rather than help me

**Context & constraints:** Teams already have written SOPs. Some steps need a human decision (approve, choose, sign off) and must stay with a person. Output often feeds regulated or client-facing documents.

**Evidence (signals of the problem, not requests for skills):**
- <n> of <m> interviewees said they do not trust AI output without re-checking every step.
- <n> support tickets or feedback items mention inconsistent results for the same task.
- <n> of <m> interviewees raised concern about AI replacing their role.
- Observed: users paste the same long instructions into new sessions to get repeatable results.

**Problem statement:** Analysts who follow team SOPs need a way to get consistent, step-by-step help from the AI because it does not know or follow their procedures, which currently makes its output untrustworthy and leaves them doing the grunt work themselves.

**Bet:** We believe skills (reusable, step-by-step versions of a team's SOPs that the assistant follows the same way every time, pausing for the human decisions) address the pains above because:
- following a defined procedure makes results consistent, which builds trust;
- explicit human decision points keep the analyst in charge of the judgement calls, which counters the fear of replacement;
- the assistant takes on the information gathering and document drafting, which frees time for higher-value work.

We will know we are right when users who run skills re-check or redo less of the output, report higher trust, and spend less time on gathering and drafting.

**Success:**
- Trust: the share of users who rate AI output as reliable rises from <baseline> to <target> within 90 days, among users who have run a skill.
- Consistency: rework on skill-run tasks (edits or reruns of the same task) is <target>% lower than on the same tasks without a skill.
- Time: users report <target> fewer hours a week on information gathering and document writing.
- MVP early signal: within 30 days, <target>% of teams that try a skill run it again on a second task.
```

## What to notice

- The problem framing never mentions skills. It describes what users say and do.
- The evidence is about the pain (distrust, inconsistency, fear), and is labelled that way.
- The Bet is the only place skills appear, and it ties each part of the capability to a specific pain.
- Success measures trust, consistency and time, not just how many people use skills.
- The Bet's core assumption ("following a defined procedure builds trust") would also go in section 6, Assumptions, and the success measures would each need a LOG item in section 10.
