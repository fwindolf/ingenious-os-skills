---
name: email-to-tasks
description: >
  This skill scans email for actionable items and creates backlog tasks. Use when
  the user asks to "check email for tasks", "triage my inbox", "process emails",
  "any new emails I need to act on", "email to tasks", "inbox review", or when
  the hourly-email-task-check schedule fires. Also trigger when the user asks
  "did anyone reply to my outreach" or "any customer emails".
---

# Email to Tasks

Scan Flo's inbox for actionable items and create tasks in the backlog.

## Context
Read the CLAUDE.md at the workspace root for label meanings and conventions.

## Workflow

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

### 5. Report
Summarize what was created (or "No actionable emails found").

## Rules
- Be conservative — only genuinely actionable items become tasks
- Titles start with a verb: Reply, Follow up, Review, Schedule, Fix
- Include enough context in description to act without re-reading the email
- Don't task FYI-only emails
- When uncertain about classification, ask Flo
