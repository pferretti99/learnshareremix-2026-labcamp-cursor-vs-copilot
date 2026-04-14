# Cursor subagents (labcamp)

These files are **Cursor subagents**: specialized delegates with their own context. The main Agent can spawn them automatically (from the `description` field) or you can invoke them explicitly, e.g. `/labcamp-code-reviewer` or natural language (“use the labcamp code reviewer subagent”).

Docs: [Subagents](https://cursor.com/docs/context/subagents).

**Not the same as:** `.cursor/rules/*.mdc` (static rules injected into chat) or GitHub Copilot’s `.github/agents/*.agent.md`.
