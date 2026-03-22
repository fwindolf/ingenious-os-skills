# Prospect Research

Finding and qualifying prospects for ingeniOS.

## 1. Find Companies

Based on criteria (trade, location, size):
- Search web for companies matching the profile
- Look at Google Maps, Handwerker portals, Innungen member lists
- Check company websites for size indicators (team page, project portfolio)
- Target: 1-15 employees, Meisterbetriebe

## 2. Qualify

For each prospect, assess:
- **Size**: employees, approximate revenue (fleet size, team photos, project scope)
- **Digital maturity**: modern website? Online booking? Or fax-and-paper?
- **Pain signals**: job postings mentioning "Büroorganisation", reviews mentioning delays
- **Decision maker**: Geschäftsführer, Meister, Büroleiterin?

## 3. Find Contacts

For each qualified company:
- Decision maker's name and role
- Email (website impressum, LinkedIn, XING)
- Phone number (impressum, Google listing)
- LinkedIn/XING profile

## 4. Add to CRM

Read `crm.yml`, then append:

```yaml
- id: company-slug        # kebab-case, unique
  name: "Company GmbH"
  trade: "SHK"
  location: "Stadt"
  website: "https://..."
  size: "5-10"
  stage: "lead"
  source: "how-we-found-them"
  notes: "Key qualification notes"
  contacts:
    - name: "Name"
      role: "Geschäftsführer"
      email: "..."
      phone: "..."
      linkedin: "..."
  interactions: []
  tags: []
```

Always check for duplicates first — search by company name and domain.

## 5. Report

Summarize: X companies found, Y qualified, Z added to CRM. Note any needing manual verification.

## Rules
- Quality over quantity — don't spam
- Only use publicly available information
- German context: Impressum is legally required and a good info source
- Always add `source` so we know how we found them
- Flag uncertain data (e.g., "email not confirmed — found on old page")
