# Feature & Solution Research

Detailed workflows for researching how to solve a specific product problem.

## 1. Problem Definition

Before researching solutions, nail the problem:
- What exactly is the user problem? (not "we need feature X" but "contractors struggle with Y")
- Who has this problem? Which trades, company sizes?
- How urgent is it? Blocker or nice-to-have?
- Check `knowledge/product-marketing-context.md` for existing pain point documentation

## 2. Competitor Analysis

How do existing tools solve this?
- **Direct**: Craftnote, Plancraft, openHandwerk
- **Indirect**: Lexware Handwerk, SevDesk, Streit V.1
- **Status quo**: Excel, paper, WhatsApp

For each competitor approach:
- What do they do well? What's bad?
- Describe their UX approach
- What's their pricing model for this feature?
- Search web for reviews and user complaints

## 3. Technology Options

Build vs buy vs integrate:
- What libraries, APIs, or services could help?
- How does it fit our stack? (Next.js, Drizzle, Inngest, Vercel AI SDK, Mastra)
- German regulatory requirements? (GoBD, ZUGFeRD, DATEV, ELSTER, BAG Zeiterfassung)
- Event-driven implications — what events are needed?

## 4. UX Patterns

Design for mobile-first contractors on Baustellen:
- What user flows work for non-tech users?
- What's the minimum viable version?
- Sketch the happy path in words
- Consider offline scenarios

## 5. Implementation Estimate

- Which modules are affected?
- New module or extension of existing?
- Events needed (check `docs/STACK.md` event catalog)
- Rough complexity: small (days), medium (week), large (weeks)

## Output Format

Save to `backlog/docs/research-<feature-slug>.md`:
```markdown
# Feature Research: [Title]
**Date**: [date]
**Problem**: [one sentence]

## Competitor Approaches
## Technology Options
## Recommended Approach
## UX Flow (happy path)
## Implementation Notes
## Open Questions
```

If research leads to a clear next step, create an engineering task in the backlog (label: `engineering`).

## Rules
- Start from the problem, not the solution
- German Handwerk context always matters — regulations, trade specifics, mobile-first
- Be concrete — "use library X because Y" not "consider various options"
- Link to sources
- Flag decisions that need Flo's input as open questions
