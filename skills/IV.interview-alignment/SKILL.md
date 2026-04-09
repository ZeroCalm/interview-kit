---

## name: IV.interview-alignment

description: Use when starting preparation for a new interview. Ingests JD and Resume to align on a structural interview strategy through Socratic questioning.
triggers: ["/IV.interview-alignment"]

# Interview Alignment

## Motivation

Use this skill FIRST when a user wants to prepare for an interview. Do NOT start asking mock questions. This phase is purely for identifying gaps and agreeing on a high-level strategy (what to emphasize, what to defend).

## 1. Information Ingestion (Hard-Gate)

You MUST request the following inputs if they are not already provided:

1. **JD (Job Description)** or target role requirements.
2. **Resume** of the candidate.

Do NOT proceed until both are provided. 

## 2. Gap Analysis & Socratic Strategy

Silently analyze the mismatch between the JD and the Resume. Identify 2-3 key risk areas (e.g., JD requires Go, Resume only has Java).

Present your gap analysis to the user, and ask **Socratic questions** to formulate a strategy. 
*Example:* "You lack distributed systems experience, which is heavily requested in the JD. Specifically, how do you plan to pivot the conversation to your strong suit of database optimization if asked about scaling?"

Do NOT give them the answer. Force them to define their own strategy. 
Iterate until you have a solid defensive and offensive strategy for the interview.

## 3. Deposition (Terminal State)

Once you and the user have agreed on the overarching strategy, you MUST generate TWO files to persist the state:

1. **Resume Snapshot**

**Save to:** `docs/interviews/YYYY-MM-DD-[Company]-[Role]/resume-snapshot.md`
Copy the raw text of the user's submitted resume here perfectly. This acts as a historical snapshot for the retrospective phase to see exactly what was claimed on paper at this point in time.

1. **Strategy Document**

**Save to:** `docs/interviews/YYYY-MM-DD-[Company]-[Role]/strategy.md`
(Use the actual date, company and role to create the isolated entity folder).

The document MUST contain:

- Context
- Gap Analysis
- Offensive Strategy (What to highlight)
- Defensive Strategy (How to handle missing skills)

**After saving the document, you MUST invoke the next skill:**

> "Strategy defined and saved. Please review the strategy doc. If it looks correct, we can move on to the next phase. I am now invoking `@[/IV.interview-planning]`."

