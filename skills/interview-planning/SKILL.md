---
name: interview-planning
description: Use strictly after interview-alignment to convert a strategy document into an actionable mock questions execution plan.
triggers: ["/interview-planning"]
---

# Interview Planning

## Motivation
Use this skill immediately after `interview-alignment` has produced a strategy document. This skill does NOT chat or roleplay. It is a pure factory for creating executable plans.

## 1. Context Resolution & Read Strategy
Scan the `docs/interviews/` directory. 
- If there are multiple active `[Company]-[Role]` folders, you MUST pause and ask the user: "Which interview session are we proceeding with?".
- Once a single context is confirmed, locate and read the strategy document at `docs/interviews/YYYY-MM-DD-[Company]-[Role]/strategy.md`.

## 2. Generate the Preparation Plan
Based strictly on the Gap Analysis and Offensive/Defensive strategies defined in the document, generate a list of mock interview questions and knowledge review topics.

**Save to:** `docs/interviews/YYYY-MM-DD-[Company]-[Role]/prep-plan.md`

## 3. Mandatory Plan Formatting
The plan MUST use standard Markdown task list items `[ ]` for tracking. This is non-negotiable.
Additionally, you MUST tag each question with a specific target sub-agent role (e.g. `[Agent: @/interview-peer]`, `[Agent: @/interview-manager]`, `[Agent: @/interview-architect]`, or `[Agent: @/interview-hr]`).

Example format:
```markdown
# [Company] [Role] Preparation Plan

## Socratic Mock Questions
- [ ] **Question 1** [Agent: @/interview-architect]: Tell me about a time you had to optimize a slow database query. (Target: Database defense strategy)
- [ ] **Question 2** [Agent: @/interview-manager]: How do you handle shifting production deadlines? (Target: Time management gap)

## Knowledge Review
- [ ] Review the exact implementation details of the refactoring in project X.
```

## 4. Terminal State
Once the plan is written, do NOT begin executing the questions. Handoff to the next phase:

> "The mock interview plan has been generated and saved to `plans/`. We are ready to begin the execution phase. I am now invoking `@[/interview-mocking]`."
