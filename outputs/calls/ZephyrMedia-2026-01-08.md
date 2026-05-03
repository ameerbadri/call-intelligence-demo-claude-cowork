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
ae_multithreading_score: 5
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
meddpicc_notes: "M:$6K→$22K baseline-to-spike; 350M→2.4B requests/month|E:VP Eng owns decision, CFO approval on budget|DC:ISR behavior under load is hard gate; pricing predictability required|DP:Cassandra+Raj drive; CFO approves on budget; March renewal deadline|PP:Not addressed—early discovery|IP:Per-invocation pricing + middleware create unpredictable scaling; CFO visibility pain|Ch:Cassandra initiated, owns internally, advocates; Raj technical gatekeeper|Co:Vercel incumbent 18mo; per-invocation pricing vs. Acme bandwidth model"
spiced_situation: 5
spiced_pain: 5
spiced_impact: 4
spiced_critical_event: 5
spiced_decision: 5
tension_flag: false
behavioral_trust_trajectory: Improving
behavioral_emotional_mismatch: false
behavioral_champion_health: Strong
talk_ratio_seller: 45
talk_ratio_prospect: 55
competitive_mentions: ["Vercel"]
product_signals: ["Acme Connect", "Bandwidth pricing model", "ISR support"]
red_flags: ["technical_feasibility_gate", "economic_buyer_partial"]
duration_minutes: 42
---

# ZephyrMedia — Discovery Brief

## Call Overview
**Deal Stage:** Discovery → Technical Eval | **Health:** 78/100 🟩🟩🟩🟩⬜ | **Outcome:** Active

**Prospect:** Zephyr Media (VP Engineering + Staff Engineer) | **Duration:** 42 min | **AE:** Jordan Reeves

---

## Deal Summary

Zephyr Media, a 6-brand digital publisher, is evaluating Acme to replace Vercel due to pricing unpredictability from per-invocation middleware costs. Pain: Vercel bill spiked $6K→$22K baseline during Q4 traffic surge (8x multiplier), creating CFO friction. VP Engineering Cassandra Bell is a strong champion with hard deadline: mid-February decision before March contract auto-renewal. ISR revalidation under load is Raj's technical gate.

---

## Scores — AE (Jordan Reeves)

| Dimension | Score | Evidence |
|-----------|-------|----------|
| Discovery | 🟩🟩🟩🟩🟩 | Opens with open questions, maps full stack (Vercel/Next.js/ISR/CMS), quantifies pain ($6K→$22K; 350M→2.4B requests/mo). |
| Multithreading | 🟩🟩🟩🟩🟩 | Identifies full decision map: VP Eng owns call, Staff Engineer gates technical, CFO approves budget. Clean stakeholder structure confirmed. |
| Objection Handling | 🟩🟩🟩🟩🟩 | Addresses ISR concern directly: acknowledges Vercel's edge, frames Acme's capability honestly ("standard patterns work; edge cases TBD"), commits to SE validation rather than overselling. |
| Value Articulation | 🟩🟩🟩🟩⬜ | Crisp bandwidth-vs-per-invocation framing; quantifies 50-60% cost reduction on spike. Could deepen non-pricing value case (build efficiency, Sanity integration). |
| Next Steps | 🟩🟩🟩🟩🟩 | Mutual commitments with dates: SE technical call Thursday, cost model Friday, decision Friday. No ambiguity. |

---

## MEDDPICC Snapshot

**M:** $6K baseline, $22K spike (8x traffic); 350M typical, 2.4B spike requests/month. **E:** Cassandra (VP Eng) owns decision; CFO approval needed on budget. **DC:** ISR stability under load is hard gate; pricing predictability is decision criteria. **DP:** Cassandra + Raj drive; CFO approves budget; March renewal is hard deadline. **PP:** Not addressed (appropriate for discovery). **IP:** Per-invocation + middleware create unpredictable cost scaling; CFO visibility is pain. **Ch:** Cassandra initiated, owns internally, advocates. Raj is technical gatekeeper. **Co:** Vercel incumbent (18mo); Acme's bandwidth model is key differentiator.

---

## Risk & Momentum

| Signal | Severity | Implication |
|--------|----------|-----------|
| **ISR feasibility unproven** | 🔴 | Raj gates decision on ISR revalidation under load. SE must validate rigorously. If technical eval fails, deal dies regardless of pricing value. |
| **Economic buyer partial** | 🟡 | CFO approval required but not on call. Cassandra understands CFO's concern and positioned to deliver business case. Plan CFO engagement post-technical validation. |
| **Hard March deadline** | 🟢 | Feb decision window before auto-renewal creates timeline pressure. Strong momentum signal. Vercel renewal motivates urgency. |

---

## The Unsaid

Cassandra's comment "The honesty matters" signals past vendor disappointment—she values candor over overselling. Raj's insistence on ISR testing before any commitment suggests technical skepticism about this specific dimension, not general doubt about Acme. Both behave like experienced evaluators: they know what breaks migrations and gate accordingly. CFO pricing concern is real but not a blocker if Acme's model is demonstrably predictable—Cassandra has internal credibility to make that case.

---

## Coaching Spotlight

**Jordan (Strength):** Exceptional discovery discipline—asks broadly before assuming, quantifies pain, validates concerns honestly rather than dismissing. **(Gap):** Could deepen secondary value levers (build efficiency, Sanity integration, phased risk mitigation) in case pricing gap is smaller than expected.

**Cassandra (Strength):** Clear internal advocate with CFO visibility. Drives decision with intellectual honesty and appropriate gatekeeping. **(Gap):** None flagged.

**Raj (Strength):** Technical gatekeeper with specific, testable concerns (ISR revalidation under load). Asks clarifying questions, commits to validation. **(Gap):** None flagged.

---

## Product Signals

| Product/Feature | Intensity | Context |
|-----------------|-----------|---------|
| **Bandwidth pricing** | High | Core differentiator vs. Vercel per-invocation; explicitly quantified as 50-60% cost reduction on spike scenario. |
| **Acme Connect (Sanity)** | Medium | Page-level cache invalidation vs. full rebuilds; Raj confirmed this is current Vercel pain point. |
| **ISR support** | High | Raj's technical gate; parity required but edge cases unproven at scale. |

---

## Next Steps

| Owner | Date | Action |
|-------|------|--------|
| **Jordan + Marcus (SE)** | Thursday | Technical deep-dive: ISR revalidation + middleware under Zephyr's real traffic load. |
| **Jordan (AE)** | Friday | Cost model: Vercel bill vs. Acme estimate using 350M typical / 2.4B spike requests. |
| **Cassandra + Jordan (AE)** | Friday | Decision call: review technical findings + cost model; confirm migration timeline. |
