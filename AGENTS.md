# AGENTS.md

## Cursor Cloud specific instructions

### Repository overview

This is **interview-kit**, a Cursor IDE plugin (defined in `.cursor-plugin/plugin.json`). It contains zero source code, zero runtime dependencies, and zero services. The entire product is Markdown configuration files that define AI agent personas, skills/workflows, and pedagogical rules for mock interview coaching inside Cursor.

### Key directories

| Path | Contents |
|---|---|
| `.cursor-plugin/plugin.json` | Plugin manifest (name, version, description) |
| `agents/` | 5 interviewer persona definitions (`interview-manager`, `interview-peer`, `interview-architect`, `interview-hr`, `interview-debrief`) |
| `skills/IV.interview-*/SKILL.md` | 5 English skill/workflow definitions (alignment → planning → mocking → mock-debrief → retrospective) |
| `skills/IV.interview-*/ZH-CN.md` | Chinese (Simplified) translations of skills |
| `rules/pedagogical-coach.mdc` | Global Cursor rule for Socratic scaffolding & root-cause analysis |

### Build / Lint / Test / Run

There is **no build step, no linter, no test suite, and no runnable service**. Validation consists of:

- Confirming `plugin.json` is valid JSON: `python3 -c "import json; json.load(open('.cursor-plugin/plugin.json'))"`
- Confirming all agent/skill Markdown files exist and have YAML frontmatter.

### Gotchas

- The plugin's runtime is Cursor itself; it cannot be tested outside the Cursor agent framework.
- Interview data is persisted to `docs/interviews/` (gitignored) at runtime by the skills.
- `.gitignore` includes `node_modules/` but no `package.json` exists; this is vestigial.
