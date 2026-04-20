# Cursor vs GitHub Copilot — Hands-on Labcamp (2026)

Shared **starter** for the **Learn Share Remix** labcamp. Work in **teams** on a **small agile task-management web app** described in **`docs/`**—same overall shape for everyone (list, detail, create, filters/search, persistence); stack and extras are up to you within that brief.

**Facilitators:** Paolo Ferretti (Cursor) · Riccardo Sartori (GitHub Copilot)

---

## Contents

1. [What you’ll do today](#what-youll-do-today)
2. [Before you arrive](#before-you-arrive)
3. [Choose your lane](#choose-your-lane)
4. [Quick setup](#quick-setup)
5. [Repo context (rules, agents, MCP, skills)](#repo-context-rules-agents-mcp-skills)
6. [Bundled Anthropic skills (optional)](#bundled-anthropic-skills-optional)
7. [Challenge & project docs (`docs/`)](#challenge--project-docs-docs)
8. [Final presentations](#final-presentations)
9. [How teams are evaluated](#how-teams-are-evaluated)
10. [Resources hub (skills, MCP, communities, docs)](#resources-hub-skills-mcp-communities-docs)

---

## What you’ll do today

1. Short **tool deep-dives** (Cursor vs Copilot)—philosophy, strengths, guardrails.
2. **Team challenge:** a small **agile task-management web app** per **[`docs/challenge-brief.md`](docs/challenge-brief.md)** (everyone builds the same *kind* of product; details and data shape in **`docs/`**).
3. **Demos + debrief:** selected teams present; we celebrate strong builds, creative workflows, and honest “best fails.”

> Timing and room logistics follow the live agenda.

---

## Before you arrive

| | Cursor | VS Code + Copilot |
|---|--------|-------------------|
| Product | [cursor.com/download](https://cursor.com/download) | [VS Code](https://code.visualstudio.com/) |
| Account | Cursor (Free/Pro is fine) | GitHub with **Copilot** ([plans](https://docs.github.com/en/copilot/get-started/plans)) |
| Repo | `git clone` and **Open Folder** as workspace | Same |
| Optional | Import VS Code settings (Command Palette → *Import* + *VS Code*) | Team extensions (LSP, themes, …) |

**Bring:** charger, GitHub login, and (if your org requires it) approval to use AI coding assistants on a **non-production** sandbox.

---

## Choose your lane

- We may split **by tool** or **by team**—follow the facilitators.
- **Mixing tools in one team** is OK if everyone agrees; be ready to explain what you used.
- Goal is **learning**, not tooling debates.

---

## Quick setup

### Cursor

1. Install from [cursor.com/download](https://cursor.com/download) → **Open Folder** on this repo.
2. During the lab, try **Tab**, **inline edit** (`Ctrl/Cmd+K`), **Chat** (`Ctrl/Cmd+L`), **Agent**, **@** context (`@Files`, `@codebase`, …), **Plan mode** if available.
3. **Privacy:** Check Privacy Mode and data settings in **Cursor Settings**. [Cursor docs](https://cursor.com/docs).

### Visual Studio Code + GitHub Copilot

1. [VS Code](https://code.visualstudio.com/) → install official **GitHub Copilot** / **Copilot Chat** → sign in with GitHub and Copilot access.
2. During the lab: **Tab** for completions, **Copilot Chat**, **Agent / Edits** (names vary by version).
3. [Copilot docs hub](https://docs.github.com/en/copilot).

**Copilot Business / Enterprise:** admins may restrict policies and models; treat this repo as a sandbox.

---

## Repo context (rules, agents, MCP, skills)

| Concept | Where |
|---------|--------|
| Portable instructions for agents | **`AGENTS.md`** (edit for your team) |
| Cursor — always-on hints | **`.cursor/rules/labcamp-starter.mdc`** (`alwaysApply: true`) |
| Cursor — **subagents** (delegated context) | **`.cursor/agents/*.md`** — [`labcamp-code-reviewer`](.cursor/agents/labcamp-code-reviewer.md), [`labcamp-test-writer`](.cursor/agents/labcamp-test-writer.md) ([`.cursor/agents/README.md`](.cursor/agents/README.md)). Invoke with **`/name`** (e.g. `/labcamp-code-reviewer`) or let Agent delegate; see [Cursor Subagents](https://cursor.com/docs/context/subagents). Same *roles* as Copilot `.github/agents/*.agent.md`, different format. |
| Cursor — optional rules (static context) | Other **`.cursor/rules/*.mdc`** you add (e.g. stack-specific); distinct from subagents. |
| Copilot — repo-wide instructions | **`.github/copilot-instructions.md`**, optional **`.github/instructions/*.instructions.md`** |
| Copilot — custom agents (cloud / supported flows) | **`.github/agents/*.agent.md`** — [`labcamp-code-reviewer`](.github/agents/labcamp-code-reviewer.agent.md), [`labcamp-test-writer`](.github/agents/labcamp-test-writer.agent.md) ([`.github/agents/README.md`](.github/agents/README.md)) |
| Hide sensitive or huge paths from AI | **`.cursorignore`** ([docs](https://docs.cursor.com/context/ignore-files)) |
| MCP | Cursor: **`.cursor/mcp.json`**. VS Code + Copilot: **`.vscode/mcp.json`**. See [`docs/mcp-configuration.md`](docs/mcp-configuration.md). Never commit secrets. |
| **Skills** (portable playbooks, often `SKILL.md`) | **Cursor:** project skills under **`.cursor/skills/<skill-name>/SKILL.md`** — [Cursor Skills](https://cursor.com/docs/context/skills). You can copy patterns from **`skills/anthropic-official/`** into that layout. **GitHub Copilot** does not use the same on-disk path as Cursor: repo guidance is usually **instructions** (above); community **skills** are often installed as **plugins** from [awesome-copilot](https://github.com/github/awesome-copilot) (`copilot plugin install …`) or by pasting skill content into `.github/instructions/`. Format reference: [agentskills.io](https://agentskills.io). |

---

## Bundled Anthropic skills (optional)

Folder **`skills/anthropic-official/`** is a vendored snapshot of [`anthropics/skills`](https://github.com/anthropics/skills). You may **delete** it for a minimal workspace or **reuse ideas** in your own files. Licenses vary by folder—see upstream and **`skills/README.md`**.

---

## Challenge & project docs (`docs/`)

**Authoritative product + technical expectations** for the build live in **`docs/`**—use them as context for Cursor, Copilot, and your team.

| Doc | What it’s for |
|-----|----------------|
| [`docs/README.md`](docs/README.md) | Index of all project docs |
| [`docs/challenge-brief.md`](docs/challenge-brief.md) | Goal, user stories, functional/technical expectations, acceptance checklist |
| [`docs/data-and-types.md`](docs/data-and-types.md) | Suggested task fields, enums, seed data (~20), `localStorage` notes |
| [`docs/working-with-ai-assistants.md`](docs/working-with-ai-assistants.md) | How to brief agents (plans, slices, acceptance criteria) |

**Summary:** build a **web app** for **agile-style task management**—list of work items, **detail** view, **create** with validation, **filter and/or search**, **~20 seeded tasks** in the repo, **new tasks persist after refresh** (e.g. `localStorage`). **Not** a mandated Kanban board (no required columns or drag-and-drop). Framework and visual design are **your choice** within `AGENTS.md` dependency rules.

### Lab process (same for every team)

1. **It must run or be demonstrable**—partial success is OK if boundaries are clear.
2. **At least two distinct assistant features** (e.g. inline + agent, chat + custom instructions, `@codebase` + plan, MCP + review, …)—**name them** in the pitch.
3. **Transparency:** AI-assisted work is expected; say if something critical was hand-written.

Team size per facilitators.

---

## Final presentations

About **3 minutes** per team:

1. **~30s** — What you built and why  
2. **~1m** — Demo (live preferred; screenshots/video OK)  
3. **~1m** — Which **tool features** you used; what worked / surprised / failed  
4. **~30s** — “Without AI, how long would this take?”

**How many teams:** often **3–4** diverse picks in a large room; two macro-teams (e.g. Cursor vs Copilot) → **both** present. Facilitators choose live to fit the agenda.

---

## How teams are evaluated

**Judges:** facilitators plus the Social team, aligned on the criteria below.

Working software or honest partial (~40%) · tool mastery, ≥2 features used well (~25%) · creativity and problem fit (~20%) · engineering judgment—secrets, deps, sense (~15%). Soft tie-breakers: clearer demo, better failure story, stronger collaboration.

---

## Resources hub (skills, MCP, communities, docs)

### Agent Skills (format & examples)

- [anthropics/skills](https://github.com/anthropics/skills) — public Agent Skills from Anthropic (this repo vendors a copy under `skills/anthropic-official/`).  
- [agentskills/agentskills](https://github.com/agentskills/agentskills) — specification repo for the Agent Skills format.  
- [agentskills.io](https://agentskills.io) — spec and overview site.

### MCP marketplaces & example configs

- **Cursor:** [Cursor Marketplace](https://cursor.com/marketplace) · [cursor.directory](https://cursor.directory/) (community). Example **`.cursor/mcp.json`** shape: [Cursor MCP docs](https://cursor.com/docs/context/mcp).  
- **VS Code + Copilot:** MCP gallery in Extensions (**search `@mcp`**) · [Add and manage MCP servers in VS Code](https://code.visualstudio.com/docs/copilot/chat/mcp-servers) · [MCP configuration reference](https://code.visualstudio.com/docs/copilot/reference/mcp-configuration). Workspace file: **`.vscode/mcp.json`**.  
- **Side-by-side examples (lab):** [`docs/mcp-configuration.md`](docs/mcp-configuration.md) — sample JSON for Cursor vs VS Code (**different keys**: `mcpServers` vs `servers`).

### Curated community repos

- [PatrickJS/awesome-cursorrules](https://github.com/PatrickJS/awesome-cursorrules) — Cursor rules / `.cursorrules` examples (adapt to `.cursor/rules/*.mdc` as needed).  
- [github/awesome-copilot](https://github.com/github/awesome-copilot) — Copilot agents, instructions, skills, plugins.

### Official product documentation

- **Cursor:** [cursor.com/docs](https://cursor.com/docs) · [Quickstart](https://cursor.com/docs/get-started/quickstart) · [Agent best practices](https://www.cursor.com/blog/agent-best-practices) · [Subagents](https://cursor.com/docs/context/subagents) · [MCP](https://cursor.com/docs/context/mcp) · [Skills](https://cursor.com/docs/context/skills)  
- **GitHub Copilot:** [docs.github.com/copilot](https://docs.github.com/en/copilot) · [Custom agents](https://docs.github.com/en/copilot/tutorials/customization-library/custom-agents/your-first-custom-agent) · [Custom instructions](https://docs.github.com/en/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot)

### Prompting (general)

- [Anthropic — prompt engineering](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) · [OpenAI — prompt engineering](https://platform.openai.com/docs/guides/prompt-engineering)

### License

Starter files (`README.md`, `AGENTS.md`, `docs/*`, `.cursor/rules/*`, `.cursor/agents/*`, `.github/copilot-instructions.md`, `.github/agents/*.agent.md`) are for the event. The **Anthropic skills bundle** keeps **upstream licenses**—see `skills/anthropic-official/README.md`.

---

**Build small, demo clearly, take good notes.**
