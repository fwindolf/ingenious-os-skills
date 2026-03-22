---
name: feature-research
description: >
  This skill researches how to solve a specific product problem — looking at competitors,
  technologies, user flows, and approaches. Use when Flo asks "how do others solve X",
  "research how to build Y", "what's the best approach for Z", "competitive analysis for feature",
  "how does [competitor] handle this", "what technologies for X", "user flow for Y",
  "feature research", "solution research", or any request about exploring how to solve
  a product/feature problem before building it.
---

# Feature Research

Research how to solve a specific product problem for handwerk-saas. Explore competitors, technologies, UX patterns, and approaches before committing to implementation.

## Context
- Product: handwerk-saas — OS for German Handwerk trade contractors
- Stack: Next.js, Drizzle, Postgres, Inngest, Vercel AI SDK (see STACK.md in project knowledge)
- Architecture: event-driven modules (see CLAUDE.md conventions)

## Research Framework

Given a problem or feature area, investigate:

### 1. Problem Definition
- What exactly is the user problem? (not "we need feature X" but "contractors struggle with Y")
- Who has this problem? Which trades, company sizes?
- How urgent is it? Is it a blocker or a nice-to-have?

### 2. Competitor Analysis
- How do existing tools solve this? (Craftsman, Meistertask, Lexoffice, SevDesk, openHandwerk, Streit V.1, etc.)
- What do they do well? What sucks?
- Screenshots or descriptions of their UX approach
- What's their pricing model for this feature?

### 3. Technology Options
- What libraries, APIs, or services could help?
- Build vs buy vs integrate analysis
- How does it fit with our stack? (Next.js, Drizzle, Inngest, etc.)
- Any German regulatory requirements? (GoBD, ZUGFeRD, DATEV, ELSTER, etc.)

### 4. UX Patterns
- What user flows would work for mobile-first contractors?
- How do non-tech users interact with this type of feature?
- What's the minimum viable version that delivers value?
- Sketch the happy path in words

### 5. Implementation Estimate
- Which modules are affected?
- New module or extension of existing?
- Events needed
- Rough complexity: small (days), medium (week), large (weeks)

## Output
Save research to `backlog/docs/research-<feature-slug>.md` with this structure:

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

If the research leads to a clear next step, create an engineering task in the backlog.

## Rules
- Start from the problem, not the solution
- German Handwerk context always matters — regulations, trade specifics, mobile-first users
- Be concrete — "use library X because Y" not "consider various options"
- Link to sources
- Flag decisions that need Flo's input as open questions
