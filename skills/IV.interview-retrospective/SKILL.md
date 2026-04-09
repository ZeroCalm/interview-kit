---
name: IV.interview-retrospective
description: Complete an interview workflow by compiling golden STAR answers and knowledge gaps into a final retrospective document.
triggers: ["/IV.interview-retrospective"]
---

# Interview Retrospective

## Motivation
Use this skill as the final step of the Interview Kit workflow (after `IV.interview-mocking` finishes or `/wrapup` is called) to consolidate the user's hard work into a reusable asset.

## 1. Persona Context & Transcript Ingestion
Before writing the retrospective, you MUST explicitly ask the user TWO things (if not already provided):
1. The **Real Interview Transcript** (voice-to-text log or raw text notes).
2. The **Interviewer Persona**: Was this interview with a Peer, a Direct Manager, an Architect, or HR?

Once provided, you MUST load the exact grading rubric for that specific persona from `.agents/agents/interview-[role].md` into your memory. This is critical because the definition of "success" changes based on who was asking the questions.

Then, locate the active interview namespace (`docs/interviews/YYYY-MM-DD-[Company]-[Role]/`) and explicitly read the following trio of files:
1. `resume-snapshot.md` (to see exactly what the user claimed to the interviewer)
2. `strategy.md` (to see the initial plan)
3. `prep-plan.md` (to see what was actually mocked)

Cross-reference the real transcript against the resume snapshot to evaluate if the resume attracted unwanted probing questions. Then check performance against the prepared materials to evaluate the execution Delta.

## 2. Artifact Deposition & Pedagogical Diagnosis
Write the final debrief document.

**Save to:** `docs/interviews/YYYY-MM-DD-[Company]-[Role]/review.md`

Instead of just listing what went wrong, you MUST act as a Senior Engineering Mentor. Provide a deep, pedagogical diagnosis of the transcript using the following exact sections:
1. **Context & Execution**: Company, Role, Date, and a summary of how the real interview felt compared to the prep session.
2. **Strategy vs. Reality (战略执行度)**: Did the candidate successfully pivot dangerous topics to their Socratic strengths (as defined in `strategy.md`), or did they get baited by the interviewer?
3. **Behavioral Psychology (心理侧写)**: Point out defensiveness, rambling, or lack of confidence in the transcript. Identify the exact sentence where they lost the interviewer's attention. Analyze if a bad interaction was caused by an overblown bullet point on their resume (`resume-snapshot.md`).
4. **Root-Cause Analysis (病灶归因)**: For every technical failure, identify the missing mental model. (e.g., "You failed the VDOM question because you memorized the API instead of understanding tree-diffing heuristics.")
5. **Actionable Study Plan (微型刻意练习 & 简历降级)**: A checklist `[ ]` assigning 15-minute highly specific coding/learning tasks to fix the gaps (DO NOT give generic advice like "study React"). PLUS explicit mandatory directives to downgrade or delete the resume bullet points that proved to be liabilities.

## 3. Terminal State
After saving the retrospective, inform the user that the interview prep workflow has successfully concluded. Do not invoke any further skills.
