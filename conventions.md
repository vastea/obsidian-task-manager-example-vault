# Conventions (this vault only)

The plugin needs **no** conventions — these are just the choices this sample vault
made so the bundled `.base` files and the calendar line up. Change them freely.

- **Task notes** live in `Tasks/`, marked `type: task` in frontmatter.
- **Projects**: `project` ∈ `Alpha` (web) · `Beta` (mobile) · `Gamma` (infra) ·
  `Personal`. The per‑project base filters on this field.
- **Status**: `status` ∈ `backlog` · `todo` · `doing` · `review` · `done` ·
  `archived`.
- **Completion**: `status: done` (the kanban `doneStatuses` option).
- **Archive**: `status: archived`; right‑click a card → Archive sets it. The
  active boards filter it out (`status != "archived"`, with `archiveValue: archived`).
- **Other fields**: `priority` (high/medium/low), `assignee`, `start` / `end`
  (ISO `YYYY-MM-DD`), `description`, `tags`.
- **Daily notes** live in `Journal/`, named `YYYY-MM-DD`, with a `## Log` section
  whose list items are `HH:MM-HH:MM (Category) [[Task]] note`. The `(Category)`
  token is optional and drives block colour when categories are enabled; the colour
  may be inline (`(Dev|blue)`) or come from the settings categories table.

These map to the plugin's global settings (journal folder `Journal`, date format
`YYYY-MM-DD`, week start Monday, log section `Log`, categories enabled) and the
per‑view options stored in each `.base`.
