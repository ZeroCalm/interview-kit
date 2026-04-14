---
name: IV.interview-bootstrap-from-real
description: Use when the user has a real interview transcript or voice-to-text log but did not complete structured mock prep first, and wants to bootstrap a targeted prep strategy and next mock plan from resume, transcript, and optional JD.
triggers: ["/IV.interview-bootstrap-from-real"]
---

# Interview Bootstrap From Real

## Motivation
Use this skill when the user already has a real interview transcript, resume, and optionally a JD, but does not yet have a reliable prep strategy or mock plan. This is a recovery-first entrypoint that turns a real interview into the next focused mock cycle.

## 1. Required Inputs & Context Resolution
Before doing any analysis, confirm these inputs:

Required:
1. Resume source (`resume-snapshot.md` or the user's provided resume)
2. Real interview transcript (voice-to-text log or raw notes)

Optional but strongly preferred:
3. JD / role description
4. Interviewer persona (`Peer`, `Direct Manager`, `Architect`, or `HR`)

If persona is missing, ask the user to classify the interviewer before proceeding.

Then locate the active interview namespace under `docs/interviews/YYYY-MM-DD-[Company]-[Role]/`.

Read this context bundle:
1. `resume-snapshot.md`
2. the provided real interview transcript
3. `strategy.md` if it exists
4. `prep-plan.md` if it exists
5. `rules/pedagogical-coach.mdc`
6. the matching `agents/interview-[role].md` persona rubric once persona is known
7. `JD` if available

Normalize the persona into a stable lowercase hyphenated slug (for example, `Direct Manager` -> `direct-manager`) and inspect:
- `review/` for existing `<persona>-bootstrap-round-N.md` files
- the namespace root for existing `prep-plan.<persona>-round-N.md` files

If no bootstrap files exist, start from `round-1`. Otherwise, increment the highest `N`.

## 2. Diagnosis Goal
You are not writing a final retrospective. You are building the fastest reliable bridge from a real interview failure or unstable performance into the next deliberate mock cycle.

Your diagnosis must answer:
1. What actually broke in the real interview?
2. Which resume bullets or claims triggered dangerous probing?
3. Which 3 high-leverage gaps should be fixed first?
4. Which next mock questions will most efficiently close those gaps?

## 3. Output Artifacts
You MUST generate two artifacts.

### Artifact A: Bootstrap Review
Save to:
`docs/interviews/YYYY-MM-DD-[Company]-[Role]/review/<persona>-bootstrap-round-N.md`

This document must be practice-first. Put the fastest-to-use section first.

Required section order:
1. `Quick Start`
2. `Top 3 Fixes`
3. `Must-Say Lines`
4. `Danger Lines`
5. `15-Minute Drills`
6. `Next Prep Plan`
7. `Deep Diagnosis`

Guidance for each section:

#### Quick Start
- One-sentence conclusion about what the user most needs to fix
- One-sentence explanation of why this matters in the target persona's rubric

#### Top 3 Fixes
- Exactly 3 bullets
- Each bullet must be concrete and phrased as a fix, not a generic weakness label

#### Must-Say Lines
- 3-5 short lines the user can directly rehearse
- Prefer judgment sentences over analysis

#### Danger Lines
- 3-5 phrases or answer patterns to avoid repeating
- Tie them to the real interview failure when possible

#### 15-Minute Drills
- A checkbox list `[ ]`
- Each task must be finishable in ~15 minutes
- Each task must have a clear completion standard

#### Next Prep Plan
- See section 4 below

#### Deep Diagnosis
- Keep this after the quick-start sections
- Include:
  - `Context & Execution`
  - `Strategy Delta`
  - `Resume Trigger Analysis`
  - `Root-Cause Analysis`
  - `Why These 3 Fixes First`

### Artifact B: Next Prep Plan Draft
Save to:
`docs/interviews/YYYY-MM-DD-[Company]-[Role]/prep-plan.<persona>-round-N.md`

This file is the direct bridge into `IV.interview-mocking`.

## 4. Next Prep Plan Requirements
The generated prep plan must:

1. Use the same house style as `prep-plan.md`
2. Contain `3-5` questions only
3. Prioritize the smallest set that closes the highest-risk gaps first
4. Use the exact format:

```text
# <Company> <Role> Bootstrap Prep Plan

## Mock Questions

- [ ] **Question 1** [Agent: @/interview-xyz]: <question text>. (Target: <what this question is trying to fix>)
  - Why this next: <why this is a top-priority next mock>
  - Source gap: <real interview failure / transcript moment / resume trigger>
```

Question design rules:
- Reuse an existing theme only if the real interview showed it is still unstable
- Prefer harder variants over unchanged repeats when the user already mocked a similar topic
- Mix personas only when it improves realism; otherwise choose the strictest relevant persona
- Each question should close one clear gap, not three vague ones

## 5. Transition To Mocking
After both artifacts are written:
1. Tell the user where the bootstrap review and prep-plan draft were saved
2. Explain that the draft plan is ready for `IV.interview-mocking`
3. Ask whether they want to start mocking immediately from `prep-plan.<persona>-round-N.md`

If the user confirms, continue with `IV.interview-mocking` using the new draft plan as the active source.

## 6. Boundaries
- Do not pretend this is a final retrospective
- Do not generate a giant essay before the user gets something they can practice
- Do not auto-overwrite the main `prep-plan.md`
- Do not create more than 5 questions in the draft plan
- Do not give generic advice like "study React" or "practice more architecture"
