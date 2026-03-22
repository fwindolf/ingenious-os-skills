---
name: daily-ceo-planning
description: >
  This skill runs the daily CEO/CTO planning workflow. Use when Flo asks to
  "plan my day", "daily standup", "morning planning", "what should I work on today",
  "review my tasks", "daily review", "what's active", or any request about organizing
  the day's work priorities. Also trigger at the start of a planning session or when
  the daily-ceo-planning schedule fires.
---

# Daily CEO Planning

Run the morning planning session for Flo (solo founder — CEO + CTO).

## Context
Read the CLAUDE.md at the workspace root for label meanings and conventions.

## Workflow

### 1. Active Work
```bash
backlog task list --status "In Progress"
```
For each: brief status, any signs of being stuck.

### 2. Blocked Items
```bash
backlog task list --status "Blocked"
```
For each: what's needed to unblock, suggest concrete next action.

### 3. Recent Completions
```bash
backlog task list --status "Done"
```
Note wins. Flag any missing final summaries.

### 4. Priority Queue
```bash
backlog task list --status "To Do"
```
Identify top 2-3 candidates for today based on priority and momentum.

### 5. Email Scan
Search Gmail for unread messages from the last 24h. Flag anything actionable:
- Outreach replies → suggest task with `outreach` label
- Customer feedback → suggest task with `product` label
- Partner inquiries → suggest task with `gtm` label

### 6. Drafts
```bash
backlog draft list
```
Any ideas worth promoting today?

### 7. Present Plan
Output format:

```
## Today — [date]

**Carry Over** (In Progress)
- [task-X] Title — status

**Blocked** (needs action)
- [task-Y] Title — what's needed

**Focus Today** (2-3 picks)
1. [task-Z] Title — why
2. ...

**New from Email** (if any)
- Potential task — source

**Drafts to Consider** (if any)
- Draft — worth it?
```

Wait for Flo's confirmation before creating or modifying anything.

## Guardrails
- Be concise — no fluff, Flo is a staff engineer
- Suggest, don't decide — present options
- Flag WIP overload (>4 In Progress = context switching warning)
- Flag stale backlog (To Do items older than 2 weeks)
