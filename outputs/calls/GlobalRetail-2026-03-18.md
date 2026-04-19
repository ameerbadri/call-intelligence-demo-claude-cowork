---
call_metadata:
  company: GlobalRetail
  date: 2026-03-18
  duration_minutes: 48
  participants:
    - name: Sarah Chen
      role: Acme AE
      seller: true
    - name: Marcus Webb
      role: Acme SE
      seller: true
    - name: Nadia Okonkwo
      role: VP Engineering, GlobalRetail
      prospect: true
      influence: economic_buyer_gatekeeper
    - name: Tom Herrera
      role: Frontend Platform Lead, GlobalRetail
      prospect: true
      influence: champion_technical
    - name: Christine Moss
      role: Procurement Manager, GlobalRetail
      prospect: true
      influence: new_gatekeeper

deal_analysis:
  stage: champion_building
  health_score: 63
  health_category: Moderate
  red_flags:
    - no_urgency
    - economic_buyer_competing_priorities
    - cfo_not_engaged
  momentum: positive_but_conditional

ae_scores:
  value_articulation: 4
  multithreading: 5
  next_step_quality: 4
  coaching_summary: "Strong engagement across stakeholders; excellent addition of Christine to the process. Could have pushed more aggressively on ROI and CFO prioritization earlier in call."

se_scores:
  technical_depth: 5
  demo_effectiveness: 5
  discovery_contribution: 5
  objection_handling: 4
  next_step_quality: 5
  coaching_summary: "Exceptional. Identified the real pain (2-day content publishing), mapped to Acme Connect seamlessly, and offered phased migration approach that addressed change management fear."

meddpicc:
  metrics: identified
  economic_buyer: partially
  decision_criteria: identified
  decision_process: partially
  paper_process: identified
  identified_pain: identified
  champion: identified
  competition: not_addressed

behavioral_dynamics:
  trust_trajectory: Improving
  champion_health: Strong
  economic_buyer_health: Moderate
  participant_dynamics: "Tom is highly motivated and trusts Acme (POC success); Nadia is technically convinced but competing-priority constrained; Christine is neutral, scanning compliance. Emotional mismatch between Tom's urgency and Nadia's bandwidth scarcity is the real blocker."
  emotional_mismatch: true

product_signals:
  - product: Acme Connect
    signal_strength: high
    context: "Contentful integration addressing 2-day content publishing bottleneck; Tom indicated this solves major internal headache. Most resonant product."
  - product: Acme Edge Functions
    signal_strength: medium
    context: "Personalization use case (segment-based routing) at edge; Tom indicated this solves server-side latency problem but not a primary pain."
  - product: Acme Sites
    signal_strength: high
    context: "4-storefront multi-brand architecture; squad autonomy model a key decision factor."
---

# GlobalRetail — 2026-03-18

> **Champion Building** · 48 min · Deal Health: **63/100**

| | |
|---|---|
| **Seller Team** | Sarah Chen (AE), Marcus Webb (SE) |
| **Prospect** | Tom Herrera (Frontend Platform Lead), Nadia Okonkwo (VP Engineering), Christine Moss (Procurement) |
| **Deal Stage** | Champion Building |
| **Next-Step Grade** | 🟡 Proposal + deep-dive locked; CFO engagement timeline undefined |

---

## Deal Summary

GlobalRetail (4 storefronts, 24 engineers, fragmented CloudFront/scripts/VM setup) has a strong technical champion (Tom, POC success) and a technically convinced VP Eng (Nadia) — but Nadia is bandwidth-constrained by 3 competing infrastructure initiatives and won't take this to the CFO without quantified ROI. The Friday proposal and ROI model are the gatekeepers; the deal's fate hinges on Nadia's prioritization decision, not on technical fit.

---

## Scores

### AE — Sarah Chen

| Dimension | Score | Evidence |
|---|---|---|
| **Multithreading** | 🟩🟩🟩🟩🟩 | Surfaced Christine mid-call (new procurement gatekeeper), briefed her immediately, and turned a potential blocker into a collaborative participant who clarified timeline and compliance gates. |
| **Value Articulation** | 🟩🟩🟩🟩⬜ | Strong proposal structure committed for Friday; missed the moment when Nadia said "3 competing initiatives" — should have asked whether Acme could enable or accelerate one of them. |
| **Next-Step Commitment** | 🟩🟩🟩🟩⬜ | Proposal + ROI model by Friday, Contentful deep-dive booked (Wed Mar 26 2pm); gap is no explicit date for when Nadia needs to present to CFO. |

### SE — Marcus Webb

| Dimension | Score | Evidence |
|---|---|---|
| **Discovery Contribution** | 🟩🟩🟩🟩🟩 | Asked "how does a content update reach production?" — uncovered the real pain: 2-day publishing bottleneck, with the head of merchandising as the loudest internal voice demanding a fix. |
| **Technical Depth** | 🟩🟩🟩🟩🟩 | Mapped Contentful → partial cache invalidation (3-5 min vs. 30 min–2 days today), edge personalization pattern, and peak traffic architecture (3-4M daily uniques). |
| **Objection Handling** | 🟩🟩🟩🟩⬜ | Handled peak load and caching concerns well; gap was offering a case study for the infrastructure skeptic instead of asking for a name and an intro. |

### MEDDPICC

**M:** 24 engineers, 4 storefronts; ROI model quantification pending (hours saved × $150/hr) · **E:** Nadia (VP Eng) — not pricing-aware; Christine approves <$100K; CFO required above · **DC:** Edge rendering, peak traffic, Contentful integration, quantified ROI · **DP:** Proposal Fri → Nadia reviews → CFO prioritization; no CFO engagement date set · **PP:** SOC 2 + vendor questionnaire → 2-3 weeks; legal adds 2-3 weeks if >$100K · **IP:** 2-day content publishing bottleneck + server-side personalization latency + change management risk · **Ch:** Tom Herrera (POC success, high credibility, motivated) · **Co:** Not addressed — incumbent is custom CloudFront/scripts

---

## Risk & Momentum

| Severity | Signal | Detail |
|---|---|---|
| 🔴 | **Competing priorities** | Nadia: "3 other infrastructure initiatives competing for the same engineering capacity" — capacity rationing, not skepticism, is the actual blocker. |
| 🔴 | **CFO not engaged** | Nadia won't escalate without quantified ROI; the Friday proposal is a prerequisite for that conversation, not a close in itself. |
| 🟡 | **Infrastructure skeptic unnamed** | Nadia flagged infrastructure team skepticism; Marcus offered a case study instead of asking for a name and an intro — delays resolution. |

---

## The Unsaid

Nadia said "important but" three times — she's torn, not opposed. Her ROI request wasn't a stall; it was a signal of what she needs to advocate internally. Tom's urgency is personal and daily; Nadia's hesitation is organizational and about capacity allocation. The proposal has to make this a "must-do" not a "nice-to-have competing with three other things."

---

## Coaching Spotlight

**Sarah Chen:** Strength: Turned a mid-call procurement surprise (Christine) into a trust-building moment by briefing her on the spot and letting her set the compliance timeline. Gap: When Nadia mentions "3 competing initiatives," push back with curiosity — ask which is highest-priority and whether Acme could enable or accelerate one.

**Marcus Webb:** Strength: Uncovered the real pain (2-day content publishing) and proactively addressed change management fear with a phased migration approach that Tom visibly responded to. Gap: Ask for the infrastructure skeptic's name and an intro rather than offering a case study — direct engagement closes the risk faster.

---

## Product Signals

| Product | Intensity | Prospect Context |
|---|---|---|
| **Acme Connect (Contentful)** | 🔴 High | 2-day publishing bottleneck — Nadia: "That would solve a major internal headache." Deep-dive booked. |
| **Acme Sites** | 🔴 High | 4-storefront multi-brand architecture with squad autonomy — Tom: "That matches my instinct." |
| **Acme Edge Functions** | 🟡 Moderate | Personalization at edge reduces server-side latency; important but not the primary pain driver. |

---

## Next Steps

1. **Sarah + Marcus (AE/SE):** Proposal with ROI model (hours saved × $150/hr + merchandising escalation reduction) + SOC 2 + term sheet — by Fri Mar 21
2. **Marcus (SE):** Contentful Connect deep-dive with Tom — caching + invalidation for multi-brand setup — Wed Mar 26 2pm
3. **Sarah (AE):** CFO alignment call with Nadia — surface prioritization timeline and CFO presentation date — week of Mar 31
