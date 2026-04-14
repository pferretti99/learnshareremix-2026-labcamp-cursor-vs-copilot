# Challenge brief — Agile task management (web app)

## One-line goal

Build a small **web app** where a team can **see a list of work items (tasks)**, **inspect one item in detail**, **add new items**, and **narrow the list** with filters or search—typical of **agile / backlog** style tools. This is **not** a formal Kanban exercise: you do **not** need columns, drag-and-drop, or a board unless you want them as extras.

## Why this shape

Same kind of app for every team (list + detail + create + persistence) so demos are comparable and assistants can scaffold quickly. You still choose **framework**, **visual design**, and **extra** features.

## User stories (minimum useful product)

1. **As a user**, I see a **primary list** of tasks (table, list, or cards) with enough information to tell items apart at a glance.
2. **As a user**, I can **open a single task** to see its full details and **return** to the list without losing my place.
3. **As a user**, I can **create a new task** with a short form and **basic validation** (e.g. required title—define what “valid” means in your UI).
4. **As a user**, I can **reduce clutter** on the list using **at least one** of: filter by a field (e.g. status or priority), **and/or** text search across titles (or titles + description if you have one).
5. **As a user**, after a **browser refresh**, **newly created tasks still appear** (e.g. `localStorage`, or another approach you document).

## Functional expectations


| Area            | Expectation                                                                         |
| --------------- | ----------------------------------------------------------------------------------- |
| List view       | Multiple tasks visible                                                              |
| Detail view     | Dedicated view or panel for one task; clear navigation back to the list.            |
| Create          | Form that adds a task to the data the app uses; invalid input handled in the UI.    |
| Filter / search | At least one meaningful mechanism (filter **or** search, or both if you have time). |
| Layout          | Intentional structure (e.g. header + main); readable typography and spacing.        |


## Technical expectations


| Topic                     | Expectation                                                                                                                                                                           |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Delivery                  | **Browser-based UI** you can demo from a local dev server or static server.                                                                                                           |
| Seed data                 | Ship **mock data in the repo** (e.g. JSON or inlined)—on the order of **~20 tasks** so filters/search are demonstrable. See [data-and-types.md](./data-and-types.md) for suggestions. |
| Persistence for new items | New tasks created in the session **survive refresh** (typical pattern: merge seed with `localStorage`; other patterns OK if documented).                                              |
| Run                       | Your app folder includes a **README** with **one primary command** to run locally (e.g. `npm run dev`, `npx vite`, `npx serve .`).                                                    |
| Dependencies              | Align with team rules in root `**AGENTS.md`** (no new packages without agreement).                                                                                                    |
| Secrets                   | No API keys in git. Use `**.env**` + `**.env.example**` only if you call external APIs—see [env-template.txt](./env-template.txt).                                                    |


## Out of scope (unless you finish early)

- Real authentication, multi-user backends, production hosting.
- Mandatory Kanban board, WIP limits, or drag-and-drop between columns.

## Acceptance checklist (demo-ready)

- App starts without errors using the documented command.
- List shows seeded tasks (~20) plus any tasks created in the session.
- Filter and/or search behaves predictably (say what you implemented in the pitch).
- Clicking a task opens detail; user can get back to the list.
- Create form adds a task that **still appears after refresh**.
- Team can name **≥ 2 distinct assistant features** used while building (lab requirement—see root `README.md`).

## Open decisions (team chooses)

- Exact field names, optional fields (e.g. due date, labels, epic).
- Framework: vanilla JS vs React/Vue/Svelte/etc.
- Routing: separate URL per task vs modal vs inline panel.
- Whether seed tasks are read-only, editable, or deletable.

Document your choices in `**AGENTS.md`** and in your app’s README.