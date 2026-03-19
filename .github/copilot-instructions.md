# GitHub Copilot — repository instructions

Copilot can use this file (and related `.github/instructions/`) as persistent guidance for this repo.

## Lab context

Teams build a small AI-related tool with freedom on stack and shape. Prefer clarity and a runnable demo over scope.

## Conventions

- Keep changes incremental; avoid large refactors unless requested.
- Do not introduce secrets into the repository; use environment variables.
- After substantive edits, suggest commands to run tests or lint if the project defines them.

## When using Agent / Edits mode

- Propose a short plan before multi-file edits when the task is ambiguous.
- Call out risks (security, dependencies, breaking API changes) explicitly.
