# Working with Cursor & Copilot on this challenge

Short practices that match how coding agents work best (see also [Cursor — agent best practices](https://www.cursor.com/blog/agent-best-practices)).

## Give the agent a stable brief

- Point the chat at **`docs/challenge-brief.md`** and **`docs/data-and-types.md`** (e.g. `@docs/challenge-brief.md` in Cursor, or paste the acceptance checklist).
- Ask for an **implementation plan** before large edits when requirements are fuzzy (Cursor **Plan mode**; Copilot: ask for a numbered plan in chat).

## Slice the work

- Example sequence: (1) data types + seed JSON, (2) list view, (3) detail + navigation, (4) create + validation, (5) filter/search, (6) `localStorage` merge, (7) README run command.
- After each slice, run the app and fix errors before asking for the next.

## Acceptance criteria in prompts

- End prompts with bullets: *“Done when: seed loads, list shows 20 rows, filter by status works, new task persists after refresh.”*  
  Sharp criteria reduce rework.

## Repository instructions

- Root **`AGENTS.md`**: fill in stack, run command, and test command as you go—Copilot and Cursor both benefit.
- **`.cursor/rules/`** and **`.github/copilot-instructions.md`**: add only team-specific rules (e.g. “use fetch + JSON only, no axios”).
- **Optional personas:** Copilot **`.github/agents/*.agent.md`** vs Cursor **`.cursor/agents/*.md` subagents** (e.g. `/labcamp-code-reviewer`)—same goals, different hosts; see [Cursor Subagents](https://cursor.com/docs/context/subagents).

## What to avoid

- Vague “build the app” without referencing the brief.
- Committing **`.env`** or real API keys (use [env-template.txt](./env-template.txt) as a reminder only).
