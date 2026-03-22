# SEO

Auditing and improving SEO for ingeniOS.

## Priority Order

1. **Crawlability & Indexation**: robots.txt, XML sitemap, index status
2. **Technical Foundations**: Core Web Vitals (LCP<2.5s, INP<200ms, CLS<0.1), HTTPS, mobile, URL structure
3. **On-Page**: Title tags (50-60 chars, keyword early), meta descriptions (150-160 chars, CTA), heading hierarchy (one H1), keyword in first 100 words, image alt text
4. **Content Quality**: E-E-A-T signals, content depth, topical coverage, freshness
5. **Authority & Links**: Internal linking, external backlinks, domain authority

## Technical Checklist

- robots.txt allows key pages, blocks admin/staging
- XML sitemap exists, submitted to Search Console, auto-updated
- Site architecture: every page reachable in ≤3 clicks
- Canonical tags on all pages (especially paginated/filtered)
- Core Web Vitals passing (test with PageSpeed Insights)
- Mobile-friendly (test with Mobile-Friendly Test)
- HTTPS everywhere, no mixed content
- Clean URLs: `/zeiterfassung` not `/features?id=3`

## On-Page Checklist

- Title: primary keyword + brand, 50-60 chars
- Meta description: compelling with CTA, 150-160 chars
- One H1 per page, logical heading hierarchy
- Primary keyword in first 100 words
- Images: descriptive alt text, WebP format, lazy loading
- Internal links with descriptive anchor text

## German Handwerk SEO Notes

- Target German-language keywords (not English)
- Trade-specific long-tail: "zeiterfassung app shk betrieb", "rechnung schreiben handwerker"
- Local SEO if relevant: Google Business Profile
- Schema markup: Software, FAQ, HowTo where applicable
- Consider trade portals and Innungen for backlinks

## Output

Save audit to `backlog/docs/seo-audit-<date>.md`. Create prioritized fix tasks in backlog (label: `gtm`).
