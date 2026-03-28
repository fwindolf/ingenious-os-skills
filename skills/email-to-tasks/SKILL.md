---
name: email-to-tasks
description: >
  This skill scans email for actionable items and creates backlog tasks, then
  processes agent-prep tasks by doing the prep work and moving them to Review.
  Use when the user asks to "check email for tasks", "triage my inbox", "process emails",
  "any new emails I need to act on", "email to tasks", "inbox review", or when
  the hourly-email-task-check schedule fires. Also trigger when the user asks
  "did anyone reply to my outreach", "any customer emails", "prep my tasks",
  or "run agent prep".
---

# Email to Tasks + Agent Prep

Two-phase workflow: (1) scan inbox and create tasks, (2) process agent-prep tasks autonomously.

## Context
Read the CLAUDE.md at the workspace root for label meanings, conventions, and the `agent-prep` label definition.

---

## Phase 1: Email to Tasks

### 1. Search Email
Use Gmail to find recent unread messages. Default query: `is:unread newer_than:1h`
Adjust timeframe based on context (e.g., `newer_than:24h` for daily review).

### 2. Classify Each Email

| Email Type | Label | Default Priority |
|---|---|---|
| Outreach reply (prospect responded) | `outreach` | high |
| Customer feedback | `product` | medium |
| Partner/investor inquiry | `gtm` | high |
| Bug report or support request | `engineering` | medium |
| Hiring related | `hiring` | medium |
| Financial/legal | `finance` | high |
| Newsletter, spam, notification | **skip** | — |

### 3. Deduplicate
```bash
backlog search "relevant keyword"
```
If a related task exists, update it instead of creating a duplicate.

### 4. Create Task
```bash
backlog task create "Verb + brief description" \
  -l <label> \
  --priority <priority> \
  -d "Sender: Name. Context: summary. Action needed: next step."
```

Link to parent epic with `-p <epicId>` when applicable.

### 5. Report Phase 1
Summarize what was created (or "No actionable emails found").

---

## Phase 2: Agent Prep

Process tasks labeled `agent-prep` in `To Do` status — do the prep work, write results into the task, advance to `Review`.

### 1. Find Agent-Prep Tasks
```bash
backlog task list --label agent-prep --status "To Do"
```
If none found, skip to final report.

### 2. For Each Agent-Prep Task

#### a. Read the task
```bash
backlog task view <taskId>
```
Locate the `## Agent Prep` section — this defines what to prepare.

#### b. Move to In Progress
```bash
backlog task edit <id> -s "In Progress"
```

#### c. Execute the prep work
Do what the `## Agent Prep` section asks for. Common patterns:
- **Research**: web search, competitor analysis, prospect profiling
- **Drafts**: email copy, outreach sequences, document outlines
- **Analysis**: synthesize knowledge files, compare options, build frameworks

Use all available tools (web search, Gmail, knowledge files, etc.).

#### d. Write results into the task
Read the task markdown file directly from `ops/backlog/tasks/`. Edit the `## Agent Prep` section:
- Strike through completed checklist items
- Add output/findings below each item
- Keep it concise but actionable — Flo should be able to act on it without further research

#### e. Move to Review
```bash
backlog task edit <id> -s "Review"
```

### 3. Report Phase 2
Per task: ID, title, what was prepped (1-2 lines), status → Review.

---

## Final Report
```
Email: X new tasks created (or "no actionable emails")
Agent Prep: Y tasks prepped → Review (or "no agent-prep tasks pending")
```

## Rules
- Be conservative — only genuinely actionable emails become tasks
- Titles start with a verb: Reply, Follow up, Review, Schedule, Fix
- Include enough context in description to act without re-reading the email
- Don't task FYI-only emails
- Agent prep should be thorough but not over-engineered — it's prep for Flo to review and act on
- If agent-prep requires info you can't access, note what's missing and still move to Review
- When uncertain about classification or prep scope, ask Flo
