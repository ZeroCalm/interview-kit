---
name: IV.interview-mock-debrief
description: Use immediately after completing an IV.interview-mocking session to generate a rapid-study preparation pack containing Golden STARs, Triage Checklists, and Reverse Interview questions.
triggers: ["/IV.interview-mock-debrief"]
---

# Mock Debrief & Triage

## Motivation
Use this skill immediately after a mock session concludes (before a real interview). It consolidates the mock performance into a highly actionable, triaged prep-pack.

## 1. Context Ingestion
Read the `strategy.md` and the completed `prep-plan.md` in the current `docs/interviews/YYYY-MM-DD-[Company]-[Role]/` namespace. Also, review the conversation log of the just-completed mock session.

## 2. Generate the Triage & Debrief Artifact
Write the debug artifact and **save to:** `docs/interviews/YYYY-MM-DD-[Company]-[Role]/mock-debrief.md`

You MUST include these exact sections:
1. **Strategy Validation (战术纪律复盘)**: Explicitly state whether the user adhered to the defenses laid out in `strategy.md` or if they were baited into answering outside their depth.
2. **Golden STARs (黄金小抄)**: Compress their successful answers into ultra-dense, 1-2 sentence bullet points. Focus purely on technical actions and measurable frontend/business outcomes.
3. **Triage Severity Checklist (红绿灯扫盲)**:
   For every error or gap identified, you MUST output BOTH a Root-Cause Diagnosis and a Micro-Deliberate Practice task. Do NOT just list the error. 
   - `[P0 - FATAL]`: Fundamental knowledge gaps. 
     - *Root-Cause:* "You failed the React.memo question because you don't actually understand JS referential equality."
     - *Micro-Practice:* "Spend 15 mins creating a sandbox with inline functions passed to a child component to visually trigger re-renders."
   - `[P1 - CRITICAL]`: Major behavioral flaws (e.g., getting defensive or rambling).
     - *Root-Cause:* Evaluate their psychological state. "You rambled for 3 minutes because you were intimidated by the micro-frontend question."
     - *Micro-Practice:* "Record yourself answering this specific question in exactly 60 seconds."
   - `[P2 - MINOR]`: Nice-to-have optimizations missed.
4. **Reverse Engineering (反向提问库)**: Generate 2-3 deep, highly technical questions the candidate should ask the Architect or Manager at the end of their real interview to prove their seniority (e.g., asking about their CI/CD frontend bottleneck, or micro-frontend state-sharing limits).

## Terminal State
Inform the user that the rapid-study pack is ready. Recommend they review `mock-debrief.md` immediately before their real interview.
