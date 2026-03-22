# User & Market Research

Detailed workflows for researching users, problems, and workflows.

## 1. Problem Research

Given a problem area (e.g., "invoicing pain", "Zettelwirtschaft", "scheduling chaos"):
- Search for industry reports, forum posts, articles about this problem in Handwerk
- Look at how contractors describe the problem in their own words (verbatim language is gold)
- Quantify the problem where possible (time wasted, money lost, error rates)
- Check trade publications: SBZ, IKZ, Handwerksblatt, DHZ
- Save findings to `backlog/docs/research-<topic>.md`

## 2. Workflow Analysis

Given a workflow (e.g., "how do SHK contractors handle Aufmaß today"):
- Map the current manual process step by step
- Identify pain points, bottlenecks, and workarounds
- Note what tools they currently use (Zettel, Excel, WhatsApp, etc.)
- Suggest where software could help most
- Note which parts are regulated (GoBD, BAG Zeiterfassung, etc.)

## 3. Feedback Synthesis

Given user feedback (from emails, calls, conversations):
- Extract key themes and patterns
- Categorize by: pain severity, frequency, willingness to pay
- Create product tasks in the backlog for validated needs (label: `product`)
- Update `backlog/docs/user-insights.md` with new learnings

## 4. Interview Prep

When preparing for a user conversation:
- Draft questions focused on understanding problems (not pitching solutions)
- Use "Jobs to be Done" style questions:
  - "Wann haben Sie zuletzt abends noch Rechnungen geschrieben?"
  - "Was passiert wenn ein Mitarbeiter seine Stunden vergisst?"
  - "Wie läuft das aktuell mit dem Steuerberater?"
- Prepare a brief on the specific trade and common pain points
- Focus on: current workflow, frustrations, what they've tried, what they'd pay for

## Output Format

Research docs go to `backlog/docs/research-<topic>.md`:
```markdown
# Research: [Topic]
**Date**: [date]
**Question**: [what we wanted to learn]

## Key Findings
## Evidence
## Implications for Product
## Open Questions
```
