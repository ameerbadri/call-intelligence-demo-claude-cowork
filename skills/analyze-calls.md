---
name: analyze-calls
description: |
  Deep per-call analysis skill. Reads one transcript at a time in an opus subagent.
  Applies MEDDPICC, SPICED, and Behavioral Dynamics frameworks. Produces a single
  .md file per call with YAML frontmatter (structured data) + visual Intelligence
  Brief (markdown body). Purpose-aware: adjusts scoring dimensions and output
  sections based on call type and deal stage.
---

# Analyze Calls — Deep Analysis Skill

## Purpose

This skill governs how individual transcript subagents behave. It is invoked
by the parent (SKILL.md) when launching per-call analysis subagents.

Reference this file when building subagent prompts to ensure consistent behavior
across all calls in a batch.

---

## Subagent Behavior Rules

### Identify Participants First

Before scoring anything:
1. List all speaker names found in the transcript
2. Classify each as: **seller** (your team) or **prospect**
3. Identify roles where determinable (AE, SE, VP Eng, Security Lead, etc.)
4. Note the call duration (last timestamp in transcript)

Seller team members are defined in `reference/product-context.md` under `## Team`.
If a name isn't in the roster, use context clues (questions they ask, products they
pitch) to classify.

### Determine Call Purpose

Classify the call into one of five types. This drives which sections appear:

| Purpose | Definition | AE Dims Scored | SE Dims Scored |
|---------|-----------|----------------|----------------|
| `discovery` | First/early call, qualifying the prospect | All 5 | Technical depth if SE present |
| `technical_scoping` | SE-led architecture/evaluation call | Partnership/Facilitation only | All 5 |
| `champion_building` | Advancing deal, working the champion/stakeholders | Value articulation, multithreading | Demo effectiveness, objection handling |
| `commercial_contracting` | Negotiation, legal, procurement | Commercial progression | Not scored |
| `relationship_checkin` | Existing customer or post-sale | Relationship health only | Not scored |

### Enumerate Evidence Before Scoring

For EVERY scored dimension, the subagent must:
1. List evidence FOR that score (direct quotes or paraphrased moments)
2. List evidence AGAINST (what was missing or done poorly)
3. Then assign the score

Do not assign scores without evidence. If a dimension cannot be assessed from the
call (e.g., an SE-led tech scoping call won't surface SPICED discovery), mark as
`null` in frontmatter — do not guess.

### Apply Density Caps Strictly

These caps are enforced regardless of call complexity:
- **Deal Summary:** 3-4 sentences. One optional blockquote.
- **Risk & Momentum:** 3 rows max (4 on exceptional calls)
- **The Unsaid:** 2-3 sentences only
- **Critical Moments:** 3 rows max
- **Coaching Spotlight:** 2 points per participant, 2 sentences each
- **Product Signals:** 3 rows max
- **Next Steps:** 3 action items max

If you hit a cap and want to include more, cut the weakest entry. The cap is
more important than completeness.

---

## Scoring Scales

### AE Dimensions (1-5)

Each AE dimension is scored 1-5 based on what was observed on this call:

| Score | Meaning |
|-------|---------|
| 5 | Exceptional execution — model behavior to share with team |
| 4 | Strong — minor gaps, overall effective |
| 3 | Adequate — some good moments, clear improvement areas |
| 2 | Below standard — missed key opportunities |
| 1 | Concerning — significant gaps that put the deal at risk |

**Dimensions by call purpose:**
- Discovery: SPICED Discovery, Multithreading, Next-Step Commitment, Objection Handling, Commercial Progression
- Technical scoping: Partnership/Facilitation, Next-Step Commitment only
- Champion building: Value Articulation, Multithreading, Next-Step Commitment
- Commercial: Commercial Progression, Next-Step Commitment

### SE Dimensions (1-5)

Same 1-5 scale as AE. Dimensions:
- Technical Depth
- Demo Effectiveness (if demo occurred)
- Discovery Contribution (how well SE participated in qualification)
- Objection Handling (technical objections)
- Next-Step Quality (technical next steps defined)

### MEDDPICC Components

Each component scored as:
- `identified` — clearly established with evidence
- `partially` — touched on but incomplete
- `not_addressed` — not raised or not applicable to this call

Include a one-line evidence note per component.

### Deal Health (0-100)

Composite score derived from:
- MEDDPICC coverage depth (40%)
- Risk signal severity (30%)
- Momentum indicators (20%)
- Next-step quality (10%)

**Reference ranges:**
- 80-100: Strong — multiple components identified, clear next steps, no major gaps
- 60-79: Moderate — some gaps but deal is progressing
- 40-59: At risk — multiple unaddressed components, weak next steps
- 0-39: Critical — major qualification failures or deal stalled

---

## Output File Structure

File path: `outputs/calls/{Company_Name}-{YYYY-MM-DD}.md`

```
---
[YAML frontmatter — all structured data]
---

# {Company} — {YYYY-MM-DD}

> **{Call Purpose label}** · {N} min · Deal Health: **{score}/100**

[Visual Intelligence Brief — markdown body]
```

See `reference/output-templates.md` for the complete YAML schema and
visual body format.

---

## Quality Checks

Before writing the output file, verify:

1. YAML frontmatter is complete — no missing required fields
2. All scored dimensions have corresponding evidence in the markdown body
3. Density caps are respected — count rows/items in each section
4. The "so what" test is passed — every finding includes an implication or action
5. The report fits in 1 page (approximately 400-600 words of prose + tables)
6. Coaching is specific — "Lucy should have asked X instead of Y" not "Lucy could improve discovery"
7. Next steps are owned — each has a clear owner (AE, SE, or prospect) and timeframe
