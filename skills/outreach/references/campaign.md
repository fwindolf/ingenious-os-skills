# Outreach Campaigns

Planning and executing outreach campaigns for ingeniOS.

## Campaign Creation Flow

### 1. Research the Angle

Every campaign starts with a real problem:
- What specific pain point? (e.g., "time wasted on paper Aufmaß")
- How bad is it? Find numbers — hours/week, error rates, money lost
- Who feels it most? Which trade, company size, role?
- What triggers the pain? (end of month invoicing crunch, tax season)

Save research to `backlog/docs/campaigns/<campaign-slug>-research.md`

### 2. Craft the Messaging

**Core message**: One sentence — problem + hint at solution
**Subject lines**: 3-5 options (short, curiosity-driven, problem-aware)
**Email sequence**:
- Email 1: Problem-aware intro (day 0)
- Email 2: Social proof or data point (day 3)
- Email 3: Direct ask / offer call (day 7)

Guidelines:
- Write in German — prospects are German contractors
- Keep it short — read on phones at Baustellen
- Be trade-specific — "als SHK-Meister kennen Sie das..." not generic
- No corporate speak — talk like a person
- Reference specific problems with numbers
- Use voice and language from `knowledge/product-marketing-context.md`

### 3. Select Targets

From `crm.yml`, filter:
- Right trade for this campaign
- Stage = `lead` (not yet contacted) or `nurture` (revisit)
- Right location/size if targeted

Present list to Flo for approval before sending.

### 4. Execute

After Flo approves:
- Draft emails in Gmail (one per prospect, personalized)
- Update CRM: stage → `contacted`, add interaction record
- Create follow-up tasks in backlog (label: `outreach`)
- Schedule follow-up emails as tasks (day 3, day 7)

### 5. Save Campaign

Save to `backlog/docs/campaigns/<campaign-slug>.md`:
```markdown
# Campaign: [Name]
**Angle**: [problem being targeted]
**Trade**: [target trade(s)]
**Created**: [date]
**Status**: active | paused | completed

## Research Summary
## Messaging
### Subject Lines
### Email 1 / 2 / 3
## Results
- Sent: X
- Replied: Y
- Meetings: Z
```

Create `backlog/docs/campaigns/` directory if it doesn't exist.

## Rules
- Never send without Flo's explicit approval
- Always personalize — no mail merge blasts
- Research before messaging
- Track everything in CRM
- German language for all prospect-facing content
