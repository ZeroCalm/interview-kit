# Interview Kit

> High-performance interview prep agent with dynamic scaffolding and pedagogical coaching — a Cursor IDE plugin by **ZeroCalm**.

Interview Kit turns Cursor into a full-cycle mock-interview coach. It orchestrates multiple AI interviewer personas through a structured, Socratic workflow that takes you from resume alignment all the way to post-interview retrospective — producing reusable study assets at every step.

## How It Works

The plugin defines a five-phase pipeline. Each phase is a **Skill** that persists its output to Markdown files and automatically hands off to the next.

```
Alignment → Planning → Mocking → Mock Debrief → Retrospective
```

| # | Skill | Trigger | What it does |
|---|---|---|---|
| 1 | **Alignment** | `/IV.interview-alignment` | Ingests JD + Resume, performs gap analysis, produces a defensive/offensive strategy document |
| 2 | **Planning** | `/IV.interview-planning` | Converts the strategy into an executable prep plan with tagged mock questions |
| 3 | **Mocking** | `/IV.interview-mocking` | Dispatches one question at a time to the appropriate interviewer sub-agent; enforces 3-round dynamic scaffolding |
| 4 | **Mock Debrief** | `/IV.interview-mock-debrief` | Generates a rapid-study prep pack: Golden STARs, P0/P1/P2 triage checklist, reverse interview questions |
| 5 | **Retrospective** | `/IV.interview-retrospective` | Post-real-interview analysis: strategy vs reality, behavioral psychology, root-cause diagnosis, micro-practice plan |

## Interviewer Personas

During the **Mocking** phase, questions are dispatched to specialised sub-agents, each with a strict grading rubric:

| Sub-agent | Persona | Focus areas |
|---|---|---|
| `@/interview-architect` | Principal / Staff Architect | System design, scalability, trade-offs, abstraction vs over-engineering |
| `@/interview-manager` | Engineering Manager | Ownership, delivery & infra, mentorship, upward management |
| `@/interview-peer` | Senior Peer Engineer | Code-level execution, "I" vs "We", engineering rigor, collaboration friction |
| `@/interview-hr` | HR / Business Partner | Cultural fit, flight risk, conflict resolution, jargon filter |
| `@/interview-debrief` | Debrief Reviewer | Extracts reusable STAR assets after each question is passed |

## Pedagogical Rules

A global rule (`rules/pedagogical-coach.mdc`) enforces two teaching strategies across all agents:

- **3-Round Dynamic Scaffolding** — Round 1: strict pressure → Round 2: structural hints → Round 3: model answer demonstration, then the user must rewrite.
- **Root-Cause Analysis** — Every failure is traced to a missing mental model, paired with a 15-minute micro-deliberate-practice task.

## Quick Start

1. Clone this repository into your Cursor workspace.
2. Open Cursor and ensure the plugin is loaded (check `.cursor-plugin/plugin.json`).
3. Start a new interview prep session by invoking the first skill:

   ```
   /IV.interview-alignment
   ```

4. Provide your **Job Description** and **Resume** when prompted.
5. Follow the guided workflow — the agent will advance through each phase automatically.

## Project Structure

```
.
├── .cursor-plugin/
│   └── plugin.json              # Plugin manifest
├── agents/
│   ├── interview-architect.md   # Architect persona & rubric
│   ├── interview-debrief.md     # Debrief reviewer
│   ├── interview-hr.md          # HR persona & rubric
│   ├── interview-manager.md     # Manager persona & rubric
│   └── interview-peer.md        # Peer engineer persona & rubric
├── rules/
│   └── pedagogical-coach.mdc    # Global scaffolding & root-cause rules
├── skills/
│   ├── IV.interview-alignment/  # Phase 1 (EN + ZH-CN)
│   ├── IV.interview-planning/   # Phase 2 (EN + ZH-CN)
│   ├── IV.interview-mocking/    # Phase 3 (EN + ZH-CN)
│   ├── IV.interview-mock-debrief/ # Phase 4 (EN + ZH-CN)
│   └── IV.interview-retrospective/ # Phase 5 (EN + ZH-CN)
└── docs/interviews/             # Runtime data (gitignored)
    └── YYYY-MM-DD-[Company]-[Role]/
        ├── resume-snapshot.md
        ├── strategy.md
        ├── prep-plan.md
        ├── answer-bank/
        ├── mock-debrief.md
        └── review.md
```

## Language Support

Every skill has both an English (`SKILL.md`) and Simplified Chinese (`ZH-CN.md`) definition. The agent adapts its coaching language accordingly.

## License

See repository for license details.
