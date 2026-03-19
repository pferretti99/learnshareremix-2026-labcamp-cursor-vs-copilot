# Cursor vs GitHub Copilot — Hands-on Labcamp (2026)

Welcome! This repository is the **shared starter base** for the **Learn Share Remix** labcamp. You will work in **teams**, with **freedom** to choose languages, frameworks, and product shape—while following a few **clear rules** so the session stays fair, safe, and fun.

**Facilitators:** Paolo Ferretti (Cursor) · Riccardo Sartori (GitHub Copilot)

---

## Table of contents

1. [What you’ll do today](#what-youll-do-today)
2. [Before you arrive (checklist)](#before-you-arrive-checklist)
3. [Choose your lane: Cursor or Copilot](#choose-your-lane-cursor-or-copilot)
4. [Setup — Cursor](#setup--cursor)
5. [Setup — Visual Studio Code + GitHub Copilot](#setup--visual-studio-code--github-copilot)
6. [Agents, rules, skills & MCP (quick map)](#agents-rules-skills--mcp-quick-map)
7. [Bundled Anthropic skills (optional)](#bundled-anthropic-skills-optional)
8. [Challenge rules](#challenge-rules)
9. [Final presentations](#final-presentations)
10. [How teams are evaluated](#how-teams-are-evaluated)
11. [Safety, privacy & “would you merge this?”](#safety-privacy--would-you-merge-this)
12. [Official documentation & further reading](#official-documentation--further-reading)

---

## What you’ll do today

At a high level:

1. Short **tool deep-dives** (Cursor vs Copilot)—philosophy, strengths, guardrails.
2. **Team challenge:** build a small **AI-powered micro-tool** (CLI, web app, API, notebook, chatbot—your call).
3. **Demos + debrief:** a few teams present; we celebrate strong builds, creative workflows, and honest “best fails.”

> Exact timing and room logistics follow the live agenda.

---

## Before you arrive (checklist)

| Step | Cursor track | Copilot (VS Code) track |
|------|----------------|-------------------------|
| Install the product | [Download Cursor](https://cursor.com/download) | Install [VS Code](https://code.visualstudio.com/) |
| Account | Cursor account (Free or Pro is fine for the lab) | GitHub account with **Copilot** enabled ([Copilot plans](https://docs.github.com/en/copilot/get-started/plans)) |
| Sign-in | Sign into Cursor | Sign into VS Code with GitHub; enable Copilot |
| Optional | Import VS Code extensions/settings into Cursor | Install any team extensions you already use (language servers, themes, etc.) |
| This repo | `git clone` (or unzip) and **open the folder** as your workspace | Same |

**Bring:** laptop charger, GitHub login, and (if required by your org) approval to use AI coding assistants on a **non-production** sandbox.

---

## Choose your lane: Cursor or Copilot

- We may split the room **by tool** (half Cursor, half Copilot) or **by team**—follow the facilitators’ instructions.
- **Mixing tools inside one team** is allowed if everyone agrees—just be ready to explain what you used.
- The goal is **learning**, not religious wars: pick the workflow you want to explore today.

---

## Setup — Cursor

### 1. Install & first launch

1. Download from **[cursor.com/download](https://cursor.com/download)** (macOS, Windows, Linux).
2. Open Cursor → **Open Folder…** → select this repository.

### 2. Import from VS Code (recommended if you use VS Code today)

- **Command Palette:** `Ctrl+Shift+P` (Windows/Linux) / `Cmd+Shift+P` (macOS) → **“Cursor: Import VS Code Settings”**  
  (wording may vary slightly by version; search for *Import* + *VS Code*).

This brings extensions, themes, and keybindings so Cursor feels familiar.

### 3. Core features to try during the lab

| Capability | Typical shortcut / entry point | Why it matters in the challenge |
|------------|--------------------------------|----------------------------------|
| **Tab (AI completions)** | `Tab` to accept | Fast iteration; good for “glue” code |
| **Inline edit** | `Ctrl+K` / `Cmd+K` | Precise edits with a natural-language instruction |
| **Chat** | `Ctrl+L` / `Cmd+L` | Ask / plan / agent workflows |
| **Agent** | Chat → *Agent* mode (see UI) | Multi-file changes, terminal steps (with approvals) |
| **Plan mode** | Often `Shift+Tab` in the chat input (or mode picker) | Review a plan before big edits |
| **@ context** | `@Files`, `@Folders`, `@codebase`, `@Web`, … | Steer the model with explicit context |

> Shortcuts can be remapped; search Command Palette for the feature name if needed.

### 4. Project brain: Rules + `AGENTS.md`

This repo includes:

- **`AGENTS.md`** — short instructions any agent-style tool can read (edit it for your team!).
- **`.cursor/rules/labcamp-starter.mdc`** — gentle defaults for the lab (you may tweak or add rules).

**Create more rules** when you see the model repeat the same mistake:  
Command Palette → **“New Cursor Rule”** → prefer small, scoped rules.

### 5. Ignore secrets from AI & indexing

Add patterns to **`.cursorignore`** (similar to `.gitignore`) for anything sensitive or huge.  
See: [Cursor ignore files](https://docs.cursor.com/context/ignore-files).

### 6. (Optional) MCP — Model Context Protocol

MCP connects the agent to external tools (GitHub, databases, docs, etc.).

- Project config: **`.cursor/mcp.json`**
- **Never commit secrets**; use environment variables and local overrides.

Docs: [Cursor MCP](https://cursor.com/docs/context/mcp).

### 7. (Optional) Agent Skills

Skills are procedural “playbooks” (often `SKILL.md`). Cursor’s support evolves by release; if Skills are available in your build, you can place team skills under **`.cursor/skills/`**.  
See: [Cursor Skills](https://cursor.com/docs/context/skills).

### 8. Privacy

If your organization requires it, review **Privacy Mode** and data-handling settings in **Cursor Settings**.  
Docs: [Cursor Docs](https://cursor.com/docs) → security / privacy topics.

---

## Setup — Visual Studio Code + GitHub Copilot

### 1. Install VS Code & Copilot

1. Install **[Visual Studio Code](https://code.visualstudio.com/)**.
2. Open **Extensions** → install **GitHub Copilot** and **GitHub Copilot Chat** (bundled in many setups—install what the marketplace shows as official).
3. Sign in with **GitHub** and ensure your account has Copilot access (trial or subscription per your org).

Docs hub: **[GitHub Copilot documentation](https://docs.github.com/en/copilot)**.

### 2. Enable inline completions & chat

- Start typing—accept suggestions with **`Tab`**.
- Open **Copilot Chat** from the sidebar / command palette.
- Explore **Agent / Edits** style flows (names evolve—use the Copilot panel modes you see in your version).

### 3. Repository instructions Copilot reads

This repo includes **`.github/copilot-instructions.md`** as a starting point.  
Copilot also supports richer setups:

- **`.github/instructions/*.instructions.md`** — scoped instructions (great for monorepos).
- **`AGENTS.md`** — simple, portable guidance at the repo root (also used by GitHub’s coding agent flows in many setups).

Template references: [Custom instructions](https://docs.github.com/en/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot).

### 4. (Optional) Custom agents (Markdown)

GitHub supports reusable **custom agents** as Markdown under **`.github/agents/`** (organization features may vary).  
Use them for repeatable roles: reviewer, docs maintainer, test writer, etc.

### 5. (Optional) MCP in VS Code

Copilot Chat in VS Code can integrate with **MCP servers** in many configurations.  
Treat MCP like installing **plugins with power**: verify sources, approve tool calls consciously, and avoid production systems.

### 6. Enterprise notes

If you are on **Copilot Business / Enterprise**, your admin may control policies, allowed models, and audit settings. When in doubt, use a **sandbox repo** like this one.

---

## Agents, rules, skills & MCP (quick map)

| Idea | Cursor (typical) | GitHub Copilot (typical) |
|------|------------------|---------------------------|
| **Persistent guidance** | `.cursor/rules/*.mdc`, User Rules | `.github/copilot-instructions.md`, `.github/instructions/` |
| **Simple portable file** | `AGENTS.md` | `AGENTS.md` |
| **Autonomous multi-step work** | Agent mode (+ terminal with approvals) | Agent / Edits in IDE; **Copilot coding agent** on GitHub for async PR workflows (plan-dependent) |
| **External tools** | MCP in `.cursor/mcp.json` | MCP (VS Code ecosystem) |
| **Procedural playbooks** | Skills (`SKILL.md`, product-dependent) | Instructions + custom agents; align with GitHub docs for your plan |

---

## Bundled Anthropic skills (optional)

Under **`skills/anthropic-official/`** you’ll find a **vendored snapshot** of Anthropic’s public skills repo ([`anthropics/skills`](https://github.com/anthropics/skills)).

- **You may delete this folder** if you want a minimal workspace.
- **You may copy ideas** into your own skill/instruction files.
- **Licenses differ by folder** (Apache-2.0 vs source-available document skills)—see upstream `README.md` and per-skill `LICENSE.txt`.

Read **`skills/README.md`** in this repo for a short overview.

---

## Challenge rules

### Theme

...

### Mandatory requirements

1. **It must run or be demonstrable**  
   Partial success is OK **if** you clearly show what works and what doesn’t.

2. **Use at least two distinct features of your assistant**  
   Examples: *Inline edit + Agent*, *Chat + custom instructions*, *Copilot Edits + terminal suggestions*, *@codebase + Plan mode*, *MCP tool + review pass*, etc.  
   **You must name them** during the final pitch.

3. **Transparency about authorship**  
   The expectation is AI-assisted work. If you typed critical parts manually, say so—interesting human steering counts as a plus in discussion.

### Freedom

- Any **language / framework**  
- Any **problem domain** (keep it respectful and legal)  
- **Team size** as announced live (solo/pair/team—follow facilitators)

---

## Final presentations

### Timebox (target)

About **3 minutes per team**, structured as:

1. **~30s** — What you built and why  
2. **~1m** — Demo (live preferred; screenshots/video OK)  
3. **~1m** — Which **tool features** you used; what worked / surprised / failed  
4. **~30s** — “Could I do this without AI? How long would it take?”

### How many teams present?

- **Many teams in the room:** we typically hear **3–4 representative teams** (selected for diversity of approach—not “only the best,” but a useful slice for discussion).  
- **Two large teams (e.g., Cursor vs Copilot):** **both** sides present.  
- Final selection is made **live** by the facilitators to fit the agenda.

---

## How teams are evaluated

Evaluation is **intentionally subjective**—this is a learning lab, not a certified exam.  
**Judges:** facilitators **plus a guest from the Social team**, aligned on the criteria below.

### Award-style categories (examples)

These mirror the spirit of the session and may be adjusted live:

| Category | Prompt | Who decides |
|----------|--------|-------------|
| **Best build** | Most useful, complete, or impressive *working* outcome | **audience vote** |
| **Most creative use of the tool** | Clever combinations, strong prompting, smart guardrails, unusual but valid workflow | **Judges** |
| **Best fail** | Funniest or most instructive autonomous mistake—what it taught you about oversight | **audience vote** |
| **Feature breadth** *(optional)* | Touched many meaningful capabilities *with intent* (not chaos) | **Judges** |
| **Innovation** *(optional)* | Novel pairing of features, MCP, instructions, tests, or human/AI split | **Judges** |

### What judges look for (rubric-style)

Scores are **not computed by a formula**—judges use this as a **shared lens**:

1. **Working software (40%)**  
   Runs end-to-end or honest partial with clear boundaries.

2. **Tool mastery (25%)**  
   At least **two** distinct features used *well*; clarity beats volume.

3. **Creativity & problem fit (20%)**  
   Interesting idea, good scoping for the timebox, thoughtful UX/DX.

4. **Engineering judgment (15%)**  
   Safety basics (no leaked secrets), sanity checks, tests or rationale when relevant.

**Tie-breakers (soft):** clearer demo, better explanation of failures, stronger ensemble collaboration.

### Extra recognition

- **Heavy feature exploration** is great **if** it’s purposeful—tell us what you tried and what you learned.  
- **Innovation** matters: unusual but effective use of **agents, rules, skills, MCP, plans, reviews**, etc.

---

## Safety, privacy & “would you merge this?”

- **No secrets** in chat, commits, or screenshots (tokens, passwords, customer data).  
- Use a **local `.env`** (gitignored). A commented template lives in **`docs/env-template.txt`**—copy what you need; never commit real keys.  
- **Review AI output** like a teammate’s PR: dependencies, auth, injection, and “too clever” abstractions.  
- If something breaks beautifully, bring it to **“Best fail”**—that’s valuable learning.

---

## Official documentation & further reading

- **Cursor:** [https://cursor.com/docs](https://cursor.com/docs) · [Quickstart](https://cursor.com/docs/get-started/quickstart)  
- **GitHub Copilot:** [https://docs.github.com/en/copilot](https://docs.github.com/en/copilot)  
- **Prompting guides:** [Anthropic](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) · [OpenAI](https://platform.openai.com/docs/guides/prompt-engineering)  
- **Agent Skills spec:** [https://agentskills.io](https://agentskills.io)

---

### License

The **starter files** (`README.md`, `AGENTS.md`, `.cursor/rules/*`, `.github/copilot-instructions.md`) are provided for the event.  
The **Anthropic skills bundle** retains its **upstream licenses**—see `skills/anthropic-official/README.md`.

---

**Good luck—build small, demo loud, and take great notes.**
