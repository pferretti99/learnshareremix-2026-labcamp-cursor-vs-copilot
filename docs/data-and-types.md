# Data model — suggestions (not strict law)

Teams may **adapt** field names and enums. Keep the **spirit**: enough structure for list, detail, filter, and seed data.

## Suggested task object

A task is a **plain object** (JSON-serializable). Example shape:


| Field       | Example                    | Notes                                 |
| ----------- | -------------------------- | ------------------------------------- |
| `id`        | `"task-1"` or `1`          | Stable unique key.                    |
| `title`     | `"Draft API contract"`     | Short label; **required** for create. |
| `status`    | `"OPEN"`                   | See enum suggestions below.           |
| `priority`  | `"MEDIUM"`                 | See enum suggestions below.           |
| `assignee`  | `"jdoe"` or `"Unassigned"` | String is enough for the lab.         |
| `createdAt` | ISO date string            | e.g. `2026-04-01T10:00:00.000Z`       |


Optional extras if useful: `description`, `updatedAt`, `tags[]`, `estimate`.

## Enum suggestions

**Status** (pick a small set and stick to it in seed + UI):

- `OPEN` | `IN_PROGRESS` | `DONE` — or rename to `TODO` / `DOING` / `DONE` if you prefer.

**Priority**:

- `LOW` | `MEDIUM` | `HIGH` — or `P1` / `P2` / `P3`.

Filters should map to **whatever values you actually store** in seed data.

## Seed data (~20 tasks)

- Keep a file such as `public/seed-tasks.json`, `src/data/seedTasks.json`, or equivalent **in the repo**.
- Mix statuses and priorities so **filters** are interesting (not 20 identical rows).
- Use **fictional** names and text—no real customer or employee data.

## Merging seed + localStorage (common pattern)

1. On load, read seed array.
2. Read `localStorage` for user-created tasks (if any).
3. Combine (avoid duplicate `id`s).
4. On create, append to the in-memory list and write the “user” subset back to `localStorage`.

Document your merge rules in the app README if non-obvious.