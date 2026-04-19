---
name: competitive-intelligence
description: |
  Cross-call competitive intelligence aggregation. Runs after per-call analysis
  is complete for a target period. Reads YAML frontmatter from competitive calls,
  produces a raw aggregation artifact, then runs three parallel output subagents
  to produce Sales Battlecard, Marketing CI Brief, and Product Intelligence.
  Top 5 Actions appears first in every output document. Triggered explicitly —
  not part of the standard per-call pipeline.
---

# Competitive Intelligence — Aggregation Skill

## Purpose

Synthesizes competitive signals across all analyzed calls in a period into
three actionable documents: one each for Sales, Marketing, and Product.

This runs on-demand, after per-call Intelligence Briefs exist for the target period.

---

## Trigger Conditions

Run this skill when:
- The user explicitly requests competitive intelligence
- Per-call analysis is complete for the target period
- At least 3 calls have competitive mentions in their YAML frontmatter

**Check the precondition:** Scan YAML frontmatter of all analyzed calls for the
`competitive_mentions` field. If fewer than 3 calls have competitive mentions,
inform the user — the CI output will have limited signal.

---

## Period Naming

- Single quarter: `q1-2026`
- Multi-quarter range: `q1-q3-2026`

Determine the period from the date range of analyzed calls. Use consistently
across all filenames in that CI run.

---

## How It Works

The aggregation runs in two phases: signal extraction across all analyzed call
reports, followed by audience-specific document generation (Sales, Marketing, Product).
Each phase runs in dedicated subagents to avoid context exhaustion on large call volumes.

The raw aggregation artifact is written to `outputs/competitive-intelligence/{period}-competitive-raw.md`
as an intermediate step before the three audience outputs are produced.

---

## CI Sales Output

**File:** `outputs/competitive-intelligence/{period}-CI-sales.md`

**Design rule:** Top 5 Actions appears FIRST. Every section exists to justify
those actions. If a finding doesn't change what an AE or SE does on their next
call, cut it.

**Sections:** Top 5 Actions → Competitor Profiles (one per competitor: their pitch,
our strengths, their genuine advantages, objection table, win pattern) → Training
Scenarios → Win/Loss Summary.

See `outputs/competitive-intelligence/q1-2026-CI-sales.md` for a fully rendered example.

---

## CI Marketing Output

**File:** `outputs/competitive-intelligence/{period}-CI-marketing.md`

**Design rule:** Top 5 Actions appears FIRST. Every insight should connect
directly to a content piece, campaign, or messaging change.

**Sections:** Top 5 Actions → ICP Signals from Competitive Deals → Messaging
Playbook by Persona → Competitive Positioning by Use Case → Content Gap Priorities.

See `outputs/competitive-intelligence/q1-2026-CI-marketing.md` for a fully rendered example.

---

## CI Product Output

**File:** `outputs/competitive-intelligence/{period}-CI-product.md`

**Design rule:** Top 5 Actions appears FIRST. Product intelligence from sales
calls is a signal source, not a requirement list — frame it as "what we're
hearing" not "what we must build."

**Sections:** Top 5 Actions → Feature Gap Analysis (ranked by deal impact: 🔴🟡🟢)
→ Competitive Roadmap Signals → Partner/Ecosystem Signals → Voice of Prospect Quotes.

See `outputs/competitive-intelligence/q1-2026-CI-product.md` for a fully rendered example.

---

## HTML Presentations

The pre-generated HTML presentations in `outputs/competitive-intelligence/` show
what the three CI markdown documents look like when rendered in the FT editorial
design system. These are included as reference examples — see the live demo at
the link in the README.
