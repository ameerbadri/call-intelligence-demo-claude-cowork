---
company: Ironbridge
date: 2026-01-27
ae_name: Sarah Chen
se_name: Marcus Webb
deal_stage: champion
deal_health: 72
deal_outcome: active
call_purpose: champion_building
next_step_quality: 5
discovery_quality: null
ae_discovery_score: 4
ae_multithreading_score: 4
ae_objection_handling_score: 5
ae_value_articulation_score: null
ae_next_step_score: 5
se_technical_depth_score: 5
se_demo_effectiveness_score: 5
se_discovery_contribution_score: 4
se_objection_handling_score: 5
meddpicc_metrics: partially
meddpicc_economic_buyer: not_addressed
meddpicc_decision_criteria: partially
meddpicc_decision_process: identified
meddpicc_paper_process: partially
meddpicc_identified_pain: identified
meddpicc_champion: identified
meddpicc_competition: identified
meddpicc_notes: "M:Deploy metrics tracked (frequency, duration, error rate, rollback rate) but no ROI quantified|E:Dmitri has budget influence but no CFO/EB engagement|DC:Cost, vendor risk, operational integration, DX named; no formal scoring|DP:Three-part gate clear (reference + contract + migration plan)|PP:Change-of-control clause flagged; procurement timeline unknown|IP:25-minute Amplify rollbacks, custom webhook fragility clearly quantified|Ch:Yuki strong internal advocate; trial-driven momentum|Co:Cloudflare Pages actively evaluated; Vercel mentioned as alternative"
spiced_situation: 4
spiced_pain: 4
spiced_impact: 4
spiced_critical_event: 3
spiced_decision: 5
tension_flag: false
behavioral_trust_trajectory: Improving
behavioral_emotional_mismatch: false
behavioral_champion_health: Strong
talk_ratio_seller: 58
talk_ratio_prospect: 42
competitive_mentions: ["Cloudflare Pages", "Vercel"]
product_signals: ["Deploy Previews", "Atomic Deploys", "Webhook System", "Log Drains", "Datadog Integration"]
red_flags: ["no_urgency"]
duration_minutes: 44
---

## Ironbridge Financial — Champion Building Call

**Company Profile:** 14 frontend engineers, 8 sites (production + internal tools). Currently on AWS Amplify. Fintech with compliance sensitivity and tight infrastructure margins.

**Deal Health:** 72/100 | **Stage:** Champion Building | **Outcome:** Active
**Risk Level:** Moderate | **Momentum:** Building (post-demo shift)

---

## Deal Summary

Three-stakeholder evaluation moving toward decision gate. Yuki (Frontend Lead) is established champion with trial proof; Dmitri (Director of Engineering) shifted position after demo—vendor risk and operational risk concerns now addressable. Samantha (Platform Engineering) moved from skeptical to cautiously positive on observability integration. Deal advances on three deliverables: fintech reference, change-of-control clause, phased migration plan.

---

## AE/SE Performance

| Dimension | Score | Evidence |
|-----------|-------|----------|
| **Sarah — Objection Handling** | 🟩🟩🟩🟩🟩 | Addressed vendor risk directly ("I want to address it directly rather than pretending it doesn't exist") and secured commitment on change-of-control language. |
| **Sarah — Multithreading** | 🟩🟩🟩🟩⬜ | Opened by asking each stakeholder's priority before demo; facilitated three different evaluation angles. Missed CFO/EB introduction. |
| **Marcus — Technical Depth** | 🟩🟩🟩🟩🟩 | Probed Datadog integration friction, diagnosed custom webhook fragility, positioned native log drains as operational advantage. |
| **Marcus — Demo Effectiveness** | 🟩🟩🟩🟩🟩 | Showed atomic deploy rollback (30 sec vs. 25 min) as operational risk quantification. Prospect immediately grasped the error-budget implication. |

---

## MEDDPICC + Competitive Position

| Component | Status | Note |
|-----------|--------|------|
| **Identified Pain** | ✅ | 25-minute Amplify rollbacks eroding error budget; custom Datadog webhooks fragile and manual |
| **Champion** | ✅ | Yuki persistent trial advocate; team alignment visible ("the deploy preview workflow my team has been waiting for") |
| **Decision Process** | ✅ | Three-gate sequence clear: fintech reference → change-of-control clause → migration plan → Thursday decision call |
| **Competition** | ✅ | Cloudflare Pages actively considered ("one throat to choke"); Samantha skeptical of Pages' maturity level |
| **Metrics / ROI** | ⚠️ | Operational metrics sharp (deploy duration, rollback rate, error budget); business ROI not quantified |
| **Economic Buyer** | ⚠️ | Dmitri has budget influence but no CFO or VP Eng engagement. Late-stage risk if deal reaches commercial phase. |
| **Paper Process** | ⚠️ | Change-of-control clause confirmed in enterprise agreements; procurement timeline and legal review process not discussed |

---

## Risk & Momentum

| Signal | Severity | Implication |
|--------|----------|-----------|
| 🟢 **Trust improvement post-demo** | Improving | Dmitri and Samantha both shifted position after technical validation. Yuki's champion credibility reinforced. Momentum is real. |
| 🟡 **No hard close date** | Moderate | "Thursday next week" is set, but no forcing event (board commitment, product launch, budget cycle deadline) surfaced. Risk of timeline slip. |
| 🟡 **Economic buyer not yet engaged** | Moderate | Dmitri is Director-level but no CFO or VP Eng on call. If deal reaches commercial/legal, new stakeholder intro could surface new objections. |

---

## The Unsaid

Dmitri's skepticism about vendor health was the admission barrier—once Marcus addressed it head-on with open-source portability and change-of-control specificity, Dmitri became actively evaluative rather than defensive. The shift is real but contingent: he's buying the operational story (atomic rollbacks, better observability), not the Acme vision. Samantha's comment about "not rebuilding the integration, I'd be deleting it" signals she's solved for her technical objection; the remaining friction is internal politics (Cloudflare was infrastructure team's suggestion) and commercial terms.

---

## Coaching Spotlight

**Sarah Chen (AE):** *Strength* — Direct vendor risk engagement turned a potential showstopper into a contractual discussion rather than a deal-killer. *Gap* — Didn't introduce or discuss economic buyer gatekeeping; left that hole open for late-stage surprises.

**Marcus Webb (SE):** *Strength* — Pinpointed observability integration as Samantha's real concern and delivered unexpected value (native Datadog) rather than generic feature recitation. *Gap* — None significant on this call; execution was exemplary.

---

## Product Signals

| Feature/Product | Intensity | Context |
|-----------------|-----------|---------|
| **Deploy Previews** | High | Yuki's team waiting for this; "the same URL updating without breaking the reviewer" is the exact pain point from their staging environment |
| **Atomic Deploys + Instant Rollback** | High | 30-second rollback vs. 25-minute Amplify re-deploy is the operational risk quantification that moved Dmitri |
| **Datadog Integration** | High | Samantha: "cleaner than what we've built. I wouldn't be rebuilding the integration, I'd be deleting it." Native log drains + webhooks solved her technical objection. |

---

## Next Steps

1. **Sarah:** Identify fintech reference customer (2+ year tenure) + provide change-of-control clause in term sheet draft — **by Wednesday end of week**
2. **Marcus:** Document phased migration plan (start with internal tool, 1-sprint approach, 14 engineers / 8 sites) — **by Friday end of week**
3. **Sarah + Dmitri:** Reconvene to review reference, contract, migration plan — **Thursday next week (specific date to be confirmed)**

---

**Call Quality Notes:** 44 minutes of substantive technical and commercial discussion. No fluff; every section moved deal forward. Prospect engaged across three stakeholder perspectives (Director risk/cost, Platform operational, Frontend DX). Momentum is earned, not assumed.
