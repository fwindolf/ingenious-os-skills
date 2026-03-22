# Competitor & Alternative Pages

Creating comparison pages for SEO and sales enablement.

## Page Formats

1. **[Competitor] Alternative** (singular) — "Craftnote Alternative"
   - URL: `/alternative/craftnote`
   - Target: people unhappy with that competitor

2. **[Competitor] Alternativen** (plural) — "Lexware Handwerk Alternativen"
   - URL: `/alternativen/lexware-handwerk`
   - Target: people comparing options

3. **ingeniOS vs [Competitor]** — "ingeniOS vs Plancraft"
   - URL: `/vergleich/ingenios-vs-plancraft`
   - Target: people directly comparing

## Page Structure

For each format:
1. TL;DR summary (who should switch, key differences)
2. Paragraph comparisons by category (not just a table)
3. Feature comparison table
4. Pricing comparison
5. Who it's best for (be honest — acknowledge competitor strengths)
6. Migration section (how to switch)
7. Social proof / testimonials
8. CTA

## Competitor Data

Maintain centralized data per competitor in `backlog/docs/competitors/`:
```yaml
name: Craftnote
positioning: "Digital project documentation for trades"
pricing: "Free tier, Pro €X/month"
strengths: ["project docs", "photo documentation", "mobile app"]
weaknesses: ["no invoicing", "no time tracking", "no DATEV export"]
best_for: "Teams focused on project documentation only"
migration_notes: "Export projects as PDF, re-create in ingeniOS"
```

## Key Competitors

- **Craftnote**: Project docs, no invoicing/accounting
- **Plancraft**: Quoting + project management, weak on invoicing
- **openHandwerk**: All-in-one but dated UX
- **Lexware Handwerk**: Accounting-focused, complex, not for trades
- **SevDesk**: Generic invoicing, not trade-specific
- **Excel + Zettel**: The real competitor — status quo

## Rules

- Be honest — acknowledge competitor strengths
- Focus on differences that matter to our ICP (small Handwerk, 1-15 people)
- German language, trade-specific examples
- Keep competitor data centralized and updated
