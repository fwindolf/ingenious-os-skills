---
name: research
description: >
  Research skill covering both user/market research and feature/solution research.
  Use when Flo asks to "research users", "understand the problem", "what do contractors
  struggle with", "interview prep", "synthesize feedback", "user pain points",
  "how do they do X today", "workflow analysis", "how do others solve X",
  "research how to build Y", "what's the best approach for Z", "competitive analysis
  for feature", "how does [competitor] handle this", "what technologies for X",
  "feature research", "solution research", "product discovery", or any question about
  understanding users, markets, or exploring solutions before building.
---

# Research

Research users, problems, markets, and solutions for ingeniOS — the operating system for German Handwerk trade contractors.

## Context

Read CLAUDE.md at workspace root for conventions. The product targets small Handwerksbetriebe (SHK, Elektro, Maler, Dachdecker, 1-15 employees). For product positioning and ICP details, read `knowledge/product-marketing-context.md`.

## Routing

This skill covers two domains. Identify which one the request falls into and read the corresponding reference:

**User & Market Research** — understanding people, problems, and workflows
- "what do contractors struggle with", "research the invoicing problem", "interview prep"
- → Read `references/user-research.md`

**Feature & Solution Research** — evaluating how to build something
- "how do others solve time tracking", "what tech should we use for X", "competitive analysis"
- → Read `references/feature-research.md`

Some requests span both (e.g., "research how contractors handle Aufmaß and what we should build"). Start with user research to understand the problem, then move to feature research for the solution.

## General Principles

- Start from the problem, not the solution
- German Handwerk context always matters — regulations (GoBD, ZUGFeRD, DATEV), trade specifics, Innungen, mobile-first users on Baustellen
- Quantify when possible — "X% of contractors" beats "many contractors"
- Be skeptical of generic AI-generated insights — look for real data, forum posts, trade publications
- Cite sources
- Save research to `backlog/docs/research-<topic>.md`
- Create backlog tasks for actionable findings (label: `product` for user research, `engineering` for feature research)
