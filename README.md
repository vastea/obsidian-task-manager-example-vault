# Task Manager — example vault

A ready‑to‑open Obsidian vault demonstrating the
**[Task Manager Bases View](https://github.com/vastea/obsidian-task-manager-bases-view)**
plugin with a small **multi‑project** task dataset.

Open this folder as a vault in **Obsidian 1.10+**. The plugin is bundled under
`.obsidian/plugins/task-manager-bases-view/` and enabled — no extra install.
All grouping and filtering is done by **Bases**; the plugin only renders.

## Data

- `Tasks/` — 22 task notes (`type: task`) across **four projects** — `Alpha`,
  `Beta`, `Gamma`, `Personal` — with `status` (`backlog / todo / doing / review /
  done / archived`), `priority`, `assignee`, `start` / `end`, `description`, plus
  some `tags` and relation fields (`parent` / `blocks` / `relates`).
- `Journal/` — daily notes (2026‑06‑08 … 2026‑06‑12) each with a `## Log` section
  of `HH:MM-HH:MM (Category) [[Task]] note` time blocks (overlaps and category
  colours included).

## Bases — each demonstrates one capability

### 1 — All tasks, by status — `1 - All tasks (by status).base`
Native Bases **group‑by** (no predefined columns). Columns are whatever statuses
exist; cards show `status / project / assignee / priority / description`.
- **Filter** `type == "task"` and `status != "archived"`; **sort** by `priority`.
- **Record changelog** is on here (`recordChangelog: true`, `changelogSection: Changelog`):
  drag a card to a new status and a `- yyyy-MM-dd old->new` line is appended under
  a `## Changelog` section in that task's note (the section is created on first move).

### 2 — Pipeline with predefined colours — `2 - Pipeline (predefined colours).base`
`usePredefinedColumns: true` — fixed, ordered, **custom‑coloured** columns via
`value|color`: `backlog|#9aa0a6, todo|#6b7280, doing|#4c8bf5, review|#e0a458,
done|#3fb950`.
- `doneStatuses: [done]` → the done column shows the **Archive‑all** button.
- `archiveValue: archived` → **right‑click a card → Archive** (or Archive‑all)
  sets `status: archived`; the filter then drops it. Right‑click also offers
  **Move to <column>**.

### 3 — By project, via filters — `3 - By project (filters).base`  ⭐ multi‑project
The headline multi‑project example: **one kanban view per project**, each using a
per‑view **filter** (`project == "Alpha"`, `"Beta"`, `"Gamma"`, `"Personal"`),
all grouped by status with the same predefined colours. Flip the view tabs to
switch between project boards from a single base.

### 4 — Timeline: flat + grouped — `4 - Timeline.base`
Two timeline views over the same tasks:
- **Flat** (week scale) — one lane per task, sorted by `start`.
- **By project** (day scale) — one swim‑lane per project for a global overview.

Bars for start+end, milestone dots for a single end; the window is padded around
the data and scrolls to today.

### 5 — Weekly‑log calendar — command **Open weekly log**
Not a base (it's a leaf view). Open it from the ribbon clock icon or the command,
then page to **2026‑06‑08 … 2026‑06‑12**.
- **Parallel blocks** render side‑by‑side; clicking a block opens that day's
  journal at the log line.
- **Categories** are pre‑enabled (see the plugin's `data.json`) — `Dev / Meeting /
  Review / …` colour the blocks. Some lines use an **inline** colour, e.g.
  `(Admin|#9aa0a6)` and `(Break|green)`.
- Drag on empty grid (up or down) to create a block via a modal; right‑click a
  block to delete it.

## What the “done column” does
`doneStatuses` marks which column values count as completed. That column gets an
**Archive‑all** action. Completion is still just a normal `status` value, so you
filter / sort / archive on it with Bases like anything else.

## Divergent data (rendered, not specially supported)
Tasks also carry `parent` / `blocks` / `relates` relations, `tags`, and an
`## Activity` section. The plugin ignores relations as features — they render as
ordinary properties / note body. That's the point: arbitrary notes do no harm.

See [conventions.md](conventions.md) for the exact field conventions and
[AGENTS.md](AGENTS.md) for an optional agent cheat‑sheet.
