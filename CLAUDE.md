# Business Ops Skill — Claude Plugin

## What This Is

Claude plugin for running a solo startup. 
Skills automate CEO/CTO workflows — planning, outreach, email triage, research — on top of Backlog.md task management and a YAML CRM.

**Assumes sibling folder layout:**
```
business-os/
├── handwerk-saas/   # product repo (fwindolf/handwerk-saas)
├── os-skill/        # this repo (fwindolf/business-ops-skill)
└── ops/             # business data (local only, no remote)
    ├── backlog/     # backlog.md data
    ├── crm.yml      # single-file CRM
    └── CLAUDE.md    # ops conventions
```

## Structure

```
os-skill/
├── .claude-plugin/
│   └── plugin.json      # plugin manifest
├── .mcp.json            # backlog MCP server (cwd: ../ops)
├── skills/
│   ├── manage-tasks/    # CRUD for tasks and epics
│   ├── daily-ceo-planning/  # morning planning workflow
│   ├── email-to-tasks/  # inbox scan → task creation
│   ├── user-research/   # research users, problems, workflows
│   ├── outreach-research/   # find and qualify prospects → CRM
│   ├── outreach-campaign/   # ideate campaign → messaging → send
│   └── feature-research/    # research solutions before building
├── hooks/
│   └── hooks.json       # session debrief + compaction hooks
└── CLAUDE.md            # this file
```

## Skills Overview

Each skill lives in `skills/<name>/SKILL.md` — that file IS the skill definition.

| Skill | Trigger | Reads | Writes |
|-------|---------|-------|--------|
| manage-tasks | task CRUD requests | backlog | backlog |
| daily-ceo-planning | morning planning | backlog, email | backlog |
| email-to-tasks | inbox scan + agent prep | email, backlog, web | backlog |
| user-research | research a user/problem | web | backlog/docs |
| outreach-research | find prospects | web | crm.yml |
| outreach-campaign | run outreach | crm.yml | email, crm.yml |
| feature-research | research before building | web, codebase | backlog/docs |

## Conventions

- Skills read/write business data in `../ops/` (backlog, CRM)
- Skills reference `../handwerk-saas/` when they need product context
- Backlog MCP server runs with cwd `../ops` (configured in `.mcp.json`)
- Hooks fire on Stop and PreCompact to remind about session debrief
