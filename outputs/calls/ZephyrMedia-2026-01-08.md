---
company: ZephyrMedia
date: 2026-01-08
ae_name: Jordan Reeves
se_name: null
deal_stage: discovery
deal_health: 78
deal_outcome: active
call_purpose: discovery
next_step_quality: 5
discovery_quality: 5
ae_discovery_score: 5
ae_multithreading_score: 4
ae_objection_handling_score: 5
ae_value_articulation_score: 4
ae_next_step_score: 5
se_technical_depth_score: null
se_demo_effectiveness_score: null
se_discovery_contribution_score: null
se_objection_handling_score: null
meddpicc_metrics: identified
meddpicc_economic_buyer: partially
meddpicc_decision_criteria: identified
meddpicc_decision_process: identified
meddpicc_paper_process: not_addressed
meddpicc_identified_pain: identified
meddpicc_champion: identified
meddpicc_competition: identified
meddpicc_notes: "M:$6K→$22K (3.67x spike), 350M→2.4B requests, 50-60% cost reduction projected|E:Cassandra owns decision; CFO aware but not buyer|DC:ISR stability under load, pricing predictability, build efficiency|DP:Technical deep-dive (Raj+Marcus Thu), cost model (Jordan by end week), decision Friday with both inputs, Feb deadline hard gate|PP:Not discussed|IP:Per-invocation pricing unpredictable at scale, middleware invocations spike with traffic, can't explain to CFO|Ch:Raj (technical veto), Cassandra (exec/decision)|Co:Vercel (incumbent), offered 10% discount, doesn't solve structural problem"
spiced_situation: 5
spiced_pain: 5
spiced_impact: 4
spiced_critical_event: 5
spiced_decision: 5
tension_flag: false
behavioral_trust_trajectory: Improving
behavioral_emotional_mismatch: false
behavioral_champion_health: Strong
talk_ratio_seller: 40
talk_ratio_prospect: 60
competitive_mentions: ["Vercel"]
product_signals: ["Acme Functions (bandwidth model for middleware/ISR; Vercel per-invocation cost pain)", "Acme Connect + Sanity integration (granular invalidation; Vercel full-rebuild pain)", "Deploy Previews (not mentioned)"]
red_flags: ["no_paper_process", "economic_buyer_absent", "competitor_threat"]
duration_minutes: 42
---

# ZephyrMedia — 2026-01-08

> **Discovery — Vercel Displacement** · 42 min · Deal Health: **78/100**

| | |
|---|---|
| **Seller Team** | Jordan Reeves (AE) |
| **Prospect** | Cassandra Bell (VP Engineering), Raj Patel (Staff Engineer) |
| **Deal Stage** | Discovery |
| **Next-Step Grade** | 🟢 Dual-track validation locked with hard Feb deadline |

---

## Deal Summary

ZephyrMedia is evaluating Acme to replace Vercel, driven entirely by pricing unpredictability — not product gaps — after a $6K → $22K cost spike from an 8x traffic surge. Hard deadline: mid-February decision before Vercel's March auto-renewal. Raj Patel has set ISR stability under load as a technical veto gate, which creates a rigorous validation path that favors Acme's implementation depth.

---

## Scores

### AE — Jordan Reeves

| Dimension | Score | Evidence |
|---|---|---|
| **Discovery** | 🟩🟩🟩🟩🟩 | Mapped architecture, traffic, and spend without leading; quantified pain ($22K spike, 350M→2.4B req/mo) and surfaced urgency via March renewal deadline. |
| **Objection Handling** | 🟩🟩🟩🟩🟩 | Acknowledged Vercel's ISR advantage directly and reframed their 10% retention discount as structurally insufficient. Cassandra: "The honesty matters." |
| **Next-Step Commitment** | 🟩🟩🟩🟩🟩 | Dual-track locked: Marcus/Raj technical Thursday, Jordan cost model Friday, Cassandra decision meeting Friday — with hard Feb deadline reinforced. |

### MEDDPICC

**M:** $22K spike (3.67x), 350M→2.4B req/mo · **E:** Cassandra owns decision; CFO aware but not in vendor selection · **DC:** ISR stability under load, pricing predictability, build efficiency · **DP:** Technical Thu → cost model Fri → decision Fri; March renewal = hard gate · **PP:** Not discussed — potential late-stage blocker · **IP:** Per-invocation cost unpredictable at media scale; CFO scrutiny on budget surprises · **Ch:** Raj (technical veto) + Cassandra (exec decision), both aligned · **Co:** Vercel incumbent; 10% retention discount structurally insufficient

---

## Risk & Momentum

| Severity | Signal | Detail |
|---|---|---|
| 🔴 | **ISR edge-case failure** | Raj set ISR stability as a deal veto; Marcus must validate against Zephyr's real high-frequency traffic patterns, not synthetic tests. |
| 🟡 | **Economic buyer absent** | CFO is cost-aware but not in vendor selection — if the cost model misses, deal stalls at approval with Cassandra's credibility exposed. |
| 🟡 | **Paper process untouched** | No procurement, legal, or contract timeline discussed; could surface as a blocker after technical validation. |

---

## The Unsaid

Cassandra is trading Vercel's market-leadership comfort for budget predictability under active CFO pressure — her internal credibility is fragile if the cost model doesn't land. Raj's insistence on rigorous edge-case testing signals he expects to find solvable problems, not dealbreakers; his willingness to design a real-traffic PoC is a positive signal on migration confidence.

---

## Coaching Spotlight

**Jordan Reeves:** Strength: Quantified pain precisely, reframed Vercel's discount as structurally inadequate, and earned trust with honesty-first positioning. Gap: Value articulation was fragmented across individual features — unify bandwidth pricing + Sanity integration + phased migration into a single "structural predictability and operational efficiency" narrative before the Friday decision meeting.

---

## Product Signals

| Product | Intensity | Prospect Context |
|---|---|---|
| **Acme Functions** | 🔴 High | Bandwidth pricing vs. per-invocation is the structural differentiator — directly addresses the CFO-visible cost spike. |
| **Acme Connect + Sanity** | 🟡 Moderate | Granular page-level invalidation reduces full-site rebuild overhead; secondary benefit but meaningful at Zephyr's publish volume. |
| **Deploy Previews** | ⬜ Not mentioned | — |

---

## Next Steps

1. **Marcus (SE):** ISR deep-dive with Raj — design PoC against Zephyr's real traffic patterns — Thu
2. **Jordan (AE):** Cost model comparing Vercel per-invocation vs. Acme bandwidth (350M typical / 2.4B spike) — by Fri
3. **Jordan (AE):** Decision meeting with Cassandra — present both inputs, confirm Feb 15 migration start — Fri
