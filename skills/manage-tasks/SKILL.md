---
name: manage-tasks
description: >
  This skill manages the backlog — creating, editing, completing, and organizing
  tasks and epics. Use whenever the user wants to "add a task", "create an epic",
  "update task status", "complete a task", "change priority", "list tasks", "show the backlog",
  "what's on my plate", "mark as done", "add a subtask", or any task/backlog management.
  Also trigger when the user mentions work items, todos, or action items that should be tracked.
---

# Manage Tasks

Operate the Business OS backlog using Backlog.md CLI.

## Setup

Read the CLAUDE.md at the root of this workspace for full conventions (labels, priorities, hierarchy, engineering task templates).

All commands run from the workspace root where `backlog/` lives.

## Core Operations

### List & Search
```bash
backlog task list                          # all active tasks
backlog task list --status "To Do"         # by status: To Do, In Progress, Review, Blocked, Done
backlog task list --label engineering      # by label: gtm, outreach, product, engineering, ops, design, finance, hiring
backlog search "keyword"                   # fuzzy search across all tasks
backlog task view <taskId>                 # full detail for one task
backlog board                              # terminal kanban
```

### Create Task
```bash
backlog task create "Verb + description" \
  -l <label> \
  --priority <high|medium|low> \
  -d "Description with context" \
  --ac "Acceptance criterion 1" \
  --ac "Acceptance criterion 2"
```

Task titles start with a verb: Add, Fix, Build, Research, Write, Set up, Review, ...

### Create Epic
An epic is a top-level task with children:
```bash
backlog task create "Epic: Launch Beta Program" -l gtm --priority high -d "Goals and scope"
# note the returned task ID, then:
backlog task create "Write beta email sequence" -l outreach -p <epicId>
backlog task create "Build beta landing page" -l product -p <epicId>
```

### Update & Complete
```bash
backlog task edit <id> -s "In Progress"
backlog task edit <id> --priority high
backlog task edit <id> -s "Done" --final-summary "What was accomplished"
```

### Engineering Tasks
For tasks that need implementation in handwerk-saas or beads-rs, include in the description:

```
## Repo
fwindolf/handwerk-saas

## Modules Affected
- @repo/[module]

## Acceptance Criteria
- [ ] Concrete, testable criteria
```

## Rules
1. **Search before create** — `backlog search "keyword"` to avoid duplicates
2. **Label everything** — no orphan tasks without a label
3. **Link to epics** — use `-p <epicId>` to maintain hierarchy
4. **Close the loop** — every Done task gets a `--final-summary`
