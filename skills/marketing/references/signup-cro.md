# Signup Flow CRO

Optimizing registration and trial activation for ingeniOS.

## Core Principles

- Minimize required fields (test each one)
- Show value before asking for info
- Reduce perceived effort (progress bar, defaults, pre-fill)
- Remove uncertainty (clear expectations: "Kostenlos, keine Kreditkarte nötig")

## Field Optimization

- **Email**: Single field start, inline validation, typo checking
- **Password**: Eye toggle, strength meter, allow paste
- **Name**: Single field > First/Last, optional if not used immediately
- **Social Auth**: Google prominent (most relevant for B2B), secondary option
- **Betrieb name / Trade / Size**: Defer to onboarding if possible

## Flow Patterns

**Single-step** (≤3 fields): Best for simple signup, high-intent visitors
**Multi-step** (>3 fields): Progress indicator, easy→hard sequence, save progress
**Progressive commitment**: Email only → Password + name → Betrieb details

## Trust & Friction Reduction

- "Keine Kreditkarte nötig"
- "Kostenlos testen — 14 Tage, voller Zugang"
- "Ihre Daten bleiben in Deutschland (Frankfurt)"
- "DSGVO-konform"
- Security badges near form
- Testimonial near CTA

## Mobile

- 44px+ touch targets
- Appropriate keyboard types (email keyboard for email field)
- Autofill support
- Single column layout
- Sticky CTA button

## Post-Submit

- Clear confirmation ("Willkommen bei ingeniOS!")
- Immediate next step (go to product, not "check your email")
- Email verification: explain why, easy resend, spam check tip

## Metrics

- Form start rate
- Completion rate (target: >60% for started)
- Field-level drop-off
- Mobile vs desktop completion
- Time to complete
