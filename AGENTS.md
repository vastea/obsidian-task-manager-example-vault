# AGENTS.md — operating on this vault's tasks

This is **optional** demo material. The plugin itself needs no agreement with any
agent; this file only helps an AI assistant count/operate on tasks in *this*
sample vault, following [conventions.md](conventions.md).

## Reading tasks
- Tasks are markdown files in `Tasks/` with `type: task`.
- Fields: `status` (`backlog/todo/doing/review/done/archived`), `project`
  (`Alpha/Beta/Gamma/Personal`), `priority`, `assignee`, `start` / `end`
  (`YYYY-MM-DD`), `description`, `tags`.

## Common recipes
- *Active work*: `status != "archived"`.
- *In progress*: `status == "doing"`.
- *Overdue*: `end < today` and `status != "done"`.
- *Per project*: filter `project == "<name>"` (see base 3).
- *Workload by person*: group by `assignee`.

## Safe-edit rules
- Only modify frontmatter you understand; never delete a note to "complete" it.
- Preserve relation fields (`parent` / `blocks` / `relates`) — they are user data,
  not plugin state.
- When writing a daily log, append a `- HH:MM-HH:MM [[Task]] note` line under the
  `## Log` heading; create the heading if absent.
