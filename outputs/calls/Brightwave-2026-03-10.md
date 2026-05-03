---
company: Brightwave
date: 2026-03-10
ae_name: Sarah Chen
se_name: null
deal_stage: discovery
deal_health: 82
deal_outcome: active
call_purpose: discovery
next_step_quality: 5
discovery_quality: 5
ae_discovery_score: 5
ae_multithreading_score: 4
ae_objection_handling_score: 5
ae_value_articulation_score: 5
ae_next_step_score: 5
se_technical_depth_score: null
se_demo_effectiveness_score: null
se_discovery_contribution_score: null
se_objection_handling_score: null
meddpicc_metrics: identified
meddpicc_economic_buyer: partially
meddpicc_decision_criteria: partially
meddpicc_decision_process: identified
meddpicc_paper_process: not_addressed
meddpicc_identified_pain: identified
meddpicc_champion: identified
meddpicc_competition: partially
meddpicc_notes: "M: Deploy 25-45min, 25-30% eng time on deployment maintenance | E: Jordan has $2K/mo budget, VP Eng Rebecca as approver but not engaged | DC: Build perf + framework support mentioned, no formal scorecard | DP: Clear timeline (mid-April go-live), stakeholders mapped, trial + tech session planned | PP: SOC 2 mentioned but no procurement process explored | IP: Staging bottleneck 6mo, missed customer commitments ($renewal impact), specific business consequence | Ch: Jordan showing internal advocacy, credibility, committed to trial | Co: Vercel evaluated, no others mentioned"
spiced_situation: 5
spiced_pain: 5
spiced_impact: 5
spiced_critical_event: 5
spiced_decision: 5
tension_flag: false
behavioral_trust_trajectory: Improving
behavioral_emotional_mismatch: false
behavioral_champion_health: Strong
talk_ratio_seller: 45
talk_ratio_prospect: 55
competitive_mentions: ["Vercel"]
product_signals: ["Next.js 14 App Router", "Deploy Previews", "Build optimization", "TypeScript"]
red_flags: []
duration_minutes: 38
---

# Brightwave — Discovery Brief

**Deal Health: 82/100** | **Stage: Discovery → Technical Eval** | **Next Steps Quality: 5/5**

Brightwave (65 engineers, growing 3x in 18 months) is outgrowing Heroku's frontend deployment pipeline. Current bottlenecks: 30-40 minute deploys + staging environment conflicts are consuming 25-30% of Priya's and one other engineer's time. Jordan Kim (Eng Manager, champion) has quantified the business impact — two product feature commitments missed last quarter due to deployment overhead; one customer renewal delayed, revenue held flat. Hard go-live deadline: mid-April, before Q2 product launch in May. Budget available: $2K/month discretionary (current Heroku spend: $800/mo). VP Engineering Rebecca Lam will approve but isn't yet involved. Next.js 14 stack, backend on AWS, looking at Vercel as primary alternative but open to framework-agnostic solution with better economics.

---

## Scores — AE (Sarah Chen)

| Dimension | Score | Evidence |
|-----------|-------|----------|
| **Discovery Quality** | 🟩🟩🟩🟩🟩 | Mapped situation (Heroku, team growth, current stack), probed pain layering (staging conflicts, eng time cost, business impact), quantified urgency (mid-April deadline), confirmed decision process and stakeholders |
| **Objection Handling** | 🟩🟩🟩🟩🟩 | Addressed Vercel head-on with honest differentiation: framework-agnostic + predictable pricing long-term beats Next.js-first approach |
| **Multithreading** | 🟩🟩🟩🟩⬜ | Engaged Jordan (champion) + Priya (technical), identified Rebecca (approver) but didn't map Rebecca's specific concerns or criteria |
| **Value Articulation** | 🟩🟩🟩🟩🟩 | Positioned Acme within Brightwave's context (Next.js parity + team-scale economics) rather than generic feature tour |

---

## MEDDPICC

**M:** Deploy time quantified (25-45 min), engineering cost quantified (25-30% time allocation) | **E:** Jordan has $2K/mo authority; Rebecca Lam (VP Eng) final approver but not yet engaged | **DC:** Build performance + framework support mentioned; no formal scorecard or RFP | **DP:** Stakeholders clear (Jordan, Priya, Rebecca), process mapped (trial → technical deep-dive → recommendation), timeline firm (mid-April) | **PP:** Not addressed (premature for discovery) | **IP:** Staging conflict (6 months), missed customer commitments, renewal impact ($2-3K delayed revenue) | **Ch:** Jordan showing internal advocacy and credibility | **Co:** Vercel active alternative, no others mentioned

---

## Risk & Momentum

| Signal | Severity | Implication |
|--------|----------|------------|
| **Vercel preference in technical layer (Priya)** | 🟡 | Priya stated preference for Vercel's Next.js DX; trial must demonstrate equivalent developer experience + build speed advantage to shift preference |
| **Economic buyer not yet engaged** | 🟡 | Rebecca hasn't evaluated alternatives; Jordan's weight as champion is high but EB sign-off required before close — plan intro before end of March |
| **Tight timeline creates momentum** | 🟢 | 6-week window to go-live pressures prospect to move decisively; vendor who ships trial proof fastest wins |

---

## The Unsaid

Jordan framed this as exploratory evaluation, but his specificity on business impact (quantified missed commitments), engineering cost, and internal stakeholder awareness suggests he's already building the business case internally for Rebecca. If the trial shows equivalent performance + better long-term economics, this moves fast.

---

## Coaching Spotlight

**Sarah Chen — Strength:** Opened with permission-based discovery and systematically layered pain before positioning, building trust visibly. **Gap:** Didn't explicitly map Rebecca Lam's decision criteria or concerns — plan a brief intro call with her in the technical eval phase to confirm alignment on the evaluation framework.

---

## Product Signals

| Signal | Intensity | Context |
|--------|-----------|---------|
| **Next.js 14 App Router** | High | Core framework; Acme's Next.js parity + framework-agnostic long-term positioning is core differentiation vs. Vercel |
| **Deploy Previews** | High | Direct pain point — staging conflict solution is top value driver; must demo live in trial |
| **Build optimization** | High | 18-22 minute builds growing slower; Marcus's Next.js caching expertise is critical next-step differentiator |

---

## Next Steps

| Owner | Action | Target Date |
|-------|--------|------------|
| Priya Patel | Deploy feature branch to Acme, test preview experience + compare build times vs. Heroku | Fri, 2026-03-15 |
| Sarah Chen + Marcus Webb | Technical session: Next.js App Router deep-dive, build optimization, security posture | Tue, 2026-03-18, 10am PT |
| Jordan Kim | Present trial results + recommendations to Rebecca Lam | Before Fri, 2026-03-28 |
