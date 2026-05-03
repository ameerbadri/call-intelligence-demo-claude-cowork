# Output Templates — Call Intelligence

**Purpose:** Canonical format for all output artifacts. Subagents must follow
these templates exactly — no improvised structures.

---

## Required Principles

All templates follow the **Compact Intelligence Rule:**

1. **Stage-and-purpose-aware framing** — Deal stage AND call purpose together determine what matters.
2. **Insight density over completeness** — Every line earns its place.
3. **The "so what" test** — Every finding includes why it matters and what to do next.
4. **Evidence on demand** — One well-chosen quote per major finding. Quotes support insights.
5. **~425 word hard cap** — The entire visual body (excluding YAML frontmatter) must fit in ~425 words. No exceptions, no high-signal exemptions.
6. **Hard density caps (ENFORCED):**
   - Deal Summary: 3 sentences MAX
   - AE/SE Scores: Evidence column = 1 sentence, no sub-bullets
   - MEDDPICC: Always one-line inline format (never a full table, except late stage)
   - Risk & Momentum: 3 rows max, 1 sentence per row
   - The Unsaid: 2 sentences MAX
   - Coaching Spotlight: 1 point per participant, 1 sentence each
   - Product Signals: 3 rows max, 1 sentence per row — columns MUST be: Product | Intensity | Context
   - Next Steps: 3 rows max, 1 line each — columns MUST be: Owner | Date | Action
7. **No extra sections.** Do NOT add "Competitive Intelligence," "Summary for Leadership," or any section not in this template. Every insight must fit inside the defined sections.

---

## File Naming Convention

- Per-call reports: `{Company_Name}-{YYYY-MM-DD}.md` (company first, date last)
- CI documents: `{period}-CI-{audience}.md` (e.g., `q1-2026-CI-sales.md`)
- Quarter labels: `Q{N}-{YYYY}` in folder names (e.g., `Q1-2026/`)
- Period labels: lowercase in filenames (e.g., `q1-2026`)

---

## Template 1: Per-Call Intelligence Brief

**Location:** `outputs/calls/{Company_Name}-{YYYY-MM-DD}.md`
**Format:** YAML frontmatter + visual markdown body
**Target length:** 1 page (~425 words of prose + tables — STRICT CAP)

### YAML Frontmatter Schema

```yaml
---
company: [Company name — match filename]
date: [YYYY-MM-DD]
ae_name: [Full name or null]
se_name: [Full name or null]
deal_stage: [discovery | technical_eval | champion | late_stage | closed_won | closed_lost]
deal_health: [0-100 integer]
deal_outcome: [active | at_risk | stalled | won | lost]
call_purpose: [discovery | technical_scoping | champion_building | commercial_contracting | relationship_checkin]
next_step_quality: [1-5 integer]
discovery_quality: [1-5 integer or null]
ae_discovery_score: [1-5 integer or null]
ae_multithreading_score: [1-5 integer or null]
ae_objection_handling_score: [1-5 integer or null]
ae_value_articulation_score: [1-5 integer or null]
ae_next_step_score: [1-5 integer or null]
se_technical_depth_score: [1-5 integer or null]
se_demo_effectiveness_score: [1-5 integer or null]
se_discovery_contribution_score: [1-5 integer or null]
se_objection_handling_score: [1-5 integer or null]
meddpicc_metrics: [identified | partially | not_addressed]
meddpicc_economic_buyer: [identified | partially | not_addressed]
meddpicc_decision_criteria: [identified | partially | not_addressed]
meddpicc_decision_process: [identified | partially | not_addressed]
meddpicc_paper_process: [identified | partially | not_addressed]
meddpicc_identified_pain: [identified | partially | not_addressed]
meddpicc_champion: [identified | partially | not_addressed]
meddpicc_competition: [identified | partially | not_addressed]
meddpicc_notes: "[M:note|E:note|DC:note|DP:note|PP:note|IP:note|Ch:note|Co:note]"
spiced_situation: [1-5 or null]
spiced_pain: [1-5 or null]
spiced_impact: [1-5 or null]
spiced_critical_event: [1-5 or null]
spiced_decision: [1-5 or null]
tension_flag: [true | false]
behavioral_trust_trajectory: [Improving | Stable | Declining | Mixed | null]
behavioral_emotional_mismatch: [true | false | null]
behavioral_champion_health: [Strong | Moderate | Weak | Absent | null]
talk_ratio_seller: [integer 0-100]
talk_ratio_prospect: [integer 0-100]
competitive_mentions: [list of competitor names, or empty list]
product_signals: [list of product/feature names mentioned]
red_flags: [list of flag codes — see below]
duration_minutes: [integer]
---
```

**Red flag codes:**
- `missing_discovery` — AE didn't conduct adequate discovery
- `no_champion` — No champion identified or showing advocacy behavior
- `no_urgency` — No compelling event surfaced
- `no_multithreading` — Single contact, no stakeholder mapping
- `deferred_without_close` — Call ended without a committed next step
- `competitor_threat` — Strong competitive alternative in play
- `champion_risk` — Champion showing signs of disengagement or loss of influence
- `economic_buyer_absent` — Deal in late stage but EB never engaged
- `stalled_deal` — Deal hasn't progressed in 3+ weeks

---

### Visual Body Format

Each brief opens with a header block (call metadata, deal stage, next-step grade), then flows through the following sections in order. See `outputs/calls/` for fully rendered examples across all deal stages and call types.

| Section | Content | Density Cap |
|---------|---------|-------------|
| **Deal Summary** | Who the prospect is, core pain, deal health/key risk | 3 sentences max |
| **Scores — AE** | Scored dimensions with one-sentence evidence per row | 3–4 rows; only dims relevant to call purpose |
| **Scores — SE** | Same format; omitted if no SE on the call | 3–4 rows |
| **MEDDPICC** | One-line inline note per component (early stage); full table (late stage) | Inline format preferred |
| **Risk & Momentum** | Severity-coded signals (🔴🟡🟢) with one-sentence implication each | 3 rows max |
| **The Unsaid** | Behavioral read — what the prospect signaled but didn't say | 2 sentences max |
| **Coaching Spotlight** | One strength + one gap per participant | 1 sentence each |
| **Product Signals** | Features/products that came up, at what intensity, in what context | 3 rows max |
| **Next Steps** | Owned actions with owner and date | 3 rows max |

The section mix is call-purpose-aware — a discovery call leads with qualification gaps and SPICED execution; a post-close debrief leads with win drivers and handoff clarity. See the stage-and-purpose weighting table below.

---

### Required Table Column Orders (ENFORCED)

Subagents MUST use exactly these column sequences — no reordering, no substitutions.

**Product Signals:**
```
| Product | Intensity | Context |
|---------|-----------|---------|
| [feature name] | 🔴 High / 🟡 Secondary / 🟢 Low | [one-sentence context] |
```

**Next Steps:**
```
| Owner | Date | Action |
|-------|------|--------|
| [Name (Role)] | [Day or date] | [Specific action] |
```

**Risk & Momentum:**
```
| Signal | Status | Implication |
|--------|--------|-------------|
| [signal name] | 🔴 / 🟡 / 🟢 | [one-sentence implication] |
```

**AE / SE Scores:**
```
| Dimension | Score | Evidence |
|-----------|-------|----------|
| [dimension] | 🟩🟩🟩🟩⬜ | [one sentence] |
```

---

## Score Bar Reference

Use emoji bars to represent scores visually:

| Score | Bar |
|-------|-----|
| 5/5 | 🟩🟩🟩🟩🟩 |
| 4/5 | 🟩🟩🟩🟩⬜ |
| 3/5 | 🟩🟩🟩⬜⬜ |
| 2/5 | 🟩🟩⬜⬜⬜ |
| 1/5 | 🟩⬜⬜⬜⬜ |

---

## Stage-and-Purpose-Aware Content Weighting

**Which sections to include by call purpose:**

| Section | Discovery | Technical Scoping | Champion Building | Late Stage |
|---------|-----------|------------------|------------------|------------|
| Deal Summary | ✅ Always | ✅ Always | ✅ Always | ✅ Always |
| AE Scores | Full SPICED dims | Partnership/facilitation only | Value articulation, multithreading | Commercial progression |
| SE Scores | If present | Full dims | Demo, objection handling | If present |
| MEDDPICC | One-line notes | DC, Competition focus | EB, Champion, DP focus | Full table |
| Risk & Momentum | ✅ Always | ✅ Always | ✅ Always | ✅ Always |
| The Unsaid | If behavioral signal | Skip if routine | ✅ Always | ✅ Always |
| Coaching Spotlight | ✅ Always | ✅ Always | ✅ Always | ✅ Always |
| Product Signals | If raised | ✅ Always | If relevant | Skip |
| Next Steps | ✅ Always | ✅ Always | ✅ Always | ✅ Always |

**Stage-determines narrative emphasis:**

| Deal Stage | Lead With | De-emphasize |
|------------|-----------|--------------|
| Discovery | Qualification gaps, SPICED execution | Product features |
| Technical Eval | Technical blockers, architecture fit | Early-stage discovery |
| Champion / Business Case | The Unsaid, EB access, competitive threats | Full framework grids |
| Late Stage | Champion health, last-mile blockers, trust trajectory | Discovery frameworks |
