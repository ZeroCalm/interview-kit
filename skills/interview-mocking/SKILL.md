---
name: interview-mocking
description: Execute mock interview questions from a prep-plan one at a time using Socratic dialogue to perfect STAR answers.
triggers: ["/interview-mocking"]
---

# Interview Mocking

## Motivation
Use this skill to execute the Mock Questions defined in an active `prep-plan.md`. This is the core practice phase.

## 1. Context Resolution & Plan Verification
Scan the `docs/interviews/` directory.
- If there are multiple active `[Company]-[Role]` folders with uncompleted tasks, you MUST pause and ask the user: "You have multiple active prep sessions. Which interview role are we mocking today?".
- Once a single context is confirmed, find the appropriate `docs/interviews/YYYY-MM-DD-[Company]-[Role]/prep-plan.md` document. Check which `- [ ]` tasks are incomplete. If none, terminate.

## 2. Controller Dispatch & One Question At A Time (Hard-Gate)
You act exclusively as the **Central Controller**, not the direct Socratic interviewer.
You MUST select exactly **ONE** incomplete question from the mock list. 
Identify the `[Agent: @/interview-xyz]` tag attached to that question.

**Dispatch Protocol:**
Instead of answering as yourself, you MUST dispatch the designated sub-agent by feeding it the mock question context. 
The sub-agent (`interview-peer`, `interview-manager`, etc.) contains the exact persona and strict grading rubric to execute the Socratic loop with the user.
You step back and let the sub-agent iterate with the user. Do NOT present the next question until the active sub-agent considers the current answer absolutely perfect according to their rubric.

## 3. Delegation of the "Anti-Echo Chamber" Rule
The dispatched sub-agent is responsible for strictly enforcing the Socratic loop and preventing echo chambers. However, if the sub-agent fails and starts giving away answers, you as the Controller MUST intervene and correct the sub-agent's behavior.

## 4. Marking Progress
When you and the user agree the answer is perfect, you MUST:
1. Summarize the polished "STAR" answer.
2. Edit `prep-plan.md` to change exactly that task's checkbox from `- [ ]` to `- [x]`.

Then, immediately move to the next incomplete `- [ ]` question.

## 5. Terminal State
When all `[ ]` tasks in the plan have become `[x]`, or the user calls `/wrapup` to finish early:
1. Stop the mock scenarios.
2. Inform the user:
> "The mock session is complete. I am now invoking the `@[/interview-mock-debrief]` skill to generate your rapid-study prep pack and Triage checklist."
