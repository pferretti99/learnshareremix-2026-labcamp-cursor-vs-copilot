# GitHub Copilot — repository instructions

Copilot can use this file (and related `.github/instructions/`) as persistent guidance for this repo.

## Lab context

Teams build a small **agile task-management web app** (list, detail, create, filter/search, seed data, persistence). **Authoritative requirements:** `docs/challenge-brief.md`, `docs/data-and-types.md`. Optional agent workflow tips: `docs/working-with-ai-assistants.md`. Example Copilot custom agents (review / tests): `.github/agents/*.agent.md`. Prefer clarity and a runnable demo over extra scope.

## Conventions

- Keep changes incremental; avoid large refactors unless requested.
- Do not introduce secrets into the repository; use environment variables.
- After substantive edits, suggest commands to run tests or lint if the project defines them.

## When using Agent / Edits mode

- Propose a short plan before multi-file edits when the task is ambiguous.
- Call out risks (security, dependencies, breaking API changes) explicitly.
