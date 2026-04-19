---
call_date: 2026-01-27
company: Ironbridge Financial
duration_minutes: 44
call_type: champion_building
participants:
  - name: Sarah Chen
    role: Acme AE
    seller: true
  - name: Marcus Webb
    role: Acme SE
    seller: true
  - name: Dmitri Volkov
    role: Director of Engineering
    seller: false
  - name: Yuki Tanaka
    role: Frontend Lead
    seller: false
  - name: Samantha Cho
    role: Head of Platform Engineering
    seller: false

deal_health_score: 75
deal_health_label: "Moderate-to-Strong"

ae_value_articulation_score: 4
ae_multithreading_score: 5
ae_next_step_score: 5

se_technical_depth_score: 5
se_demo_effectiveness_score: 5
se_objection_handling_score: 5
se_next_step_quality_score: 4

trust_trajectory: Improving
champion_health: Strong
emotional_mismatch: false

red_flags:
  - competitor_threat
  - vendor_risk_gating

key_insights:
  - dmitri_position_shift: "Skeptic to conviction on operational pain (25-min rollback → 30-sec)"
  - samantha_conversion: "Technical skepticism to buy-in ('cleaner than what we built')"
  - champion_validation: "Yuki no longer alone; Dmitri + Samantha actively supporting"
  - competitive_pressure: "Cloudflare Pages real but not locked (infrastructure team preference; Samantha skeptical on maturity)"
  - gating_items: "Change-of-control clause + fintech reference required before pricing"

products_mentioned:
  - Deploy Previews: high_signal
  - Atomic Rollbacks: high_signal
  - Datadog Integration: high_signal

competitive_intel:
  - Cloudflare Pages: infrastructure_team_preference_but_samantha_skeptical
  - Vercel: positioned_as_most_comparable_enterprise_alternative
  - AWS Amplify: incumbent_with_25_minute_rollback_pain
---

# Ironbridge Financial — 2026-01-27

> **Champion Building** · 44 min · Deal Health: **75/100**

| | |
|---|---|
| **Seller Team** | Sarah Chen (AE), Marcus Webb (SE) |
| **Prospect** | Dmitri Volkov (Dir. Engineering), Yuki Tanaka (Frontend Lead), Samantha Cho (Head of Platform) |
| **Deal Stage** | Champion Building |
| **Next-Step Grade** | 🟢 Three gating items locked with owners and dates |

---

## Deal Summary

Ironbridge Financial (14 FEs, 8 sites on Amplify) entered skeptical and left with three active champions. Dmitri (Director Eng, skeptic) converted on quantified rollback pain — 25 min → 30 sec atomic. Samantha (Head of Platform) converted on native Datadog integration replacing her fragile custom webhook setup. Three gating items must clear before pricing: fintech reference (Wed), change-of-control clause (EOW), phased migration plan (EOW).

---

## Scores

### AE — Sarah Chen

| Dimension | Score | Evidence |
|---|---|---|
| **Multithreading** | 🟩🟩🟩🟩🟩 | Brought three stakeholders with distinct concerns, routed air time to each, extracted decision criteria from all three roles, locked next steps with named owners. |
| **Next-Step Commitment** | 🟩🟩🟩🟩🟩 | Fintech ref by Wed, change-of-control by EOW, migration plan by EOW, reconvene Thursday — every item has an owner and a date. |
| **Value Articulation** | 🟩🟩🟩🟩⬜ | Captured decision criteria across stakeholders but let Marcus own the quantified ROI narrative — missed the moment to connect 25-min rollbacks explicitly to Dmitri's stated risk concern. |

### SE — Marcus Webb

| Dimension | Score | Evidence |
|---|---|---|
| **Demo Effectiveness** | 🟩🟩🟩🟩🟩 | Rollback demo (30 sec vs. 25 min) moved Dmitri from skeptic to commitment; Datadog integration demo converted Samantha — "I'd be deleting my custom webhooks, not rebuilding them." |
| **Objection Handling** | 🟩🟩🟩🟩🟩 | Addressed vendor risk (acquisition, financial health) with concrete mitigations; validated Samantha's Cloudflare skepticism and explained why "network company adding hosting" matters as a product maturity signal. |

### MEDDPICC

**M:** 25-min rollbacks = eroded error budget; 14 engineers, 8 sites quantified · **E:** Dmitri (Dir. Eng) decision authority; budget not confirmed · **DC:** Deploy Previews, atomic rollbacks, Datadog native integration, fintech reference · **DP:** Gating items due EOW → reconvene Thu → pricing discussion · **PP:** Change-of-control clause required pre-pricing · **IP:** 25-min non-atomic rollbacks + fragile custom Datadog webhook setup · **Ch:** Yuki (original), Dmitri + Samantha (newly converted) — buying group aligned · **Co:** Cloudflare Pages (infra team interest; Samantha skeptical on maturity); Vercel (not active)

---

## Risk & Momentum

| Severity | Signal | Detail |
|---|---|---|
| 🟡 | **Cloudflare competitive threat** | Infrastructure team already interested ("one throat to choke"); Samantha is skeptical on product maturity but isn't the final decision-maker. |
| 🟡 | **Fintech reference availability** | Sarah committed a 2+ year fintech reference by Wednesday — if unavailable, it creates a credibility gap on vendor health claims. |
| 🟢 | **Multi-stakeholder conversion** | Two skeptics converted in real time on operational pain; buying group is aligned heading into gating items. |

---

## The Unsaid

Dmitri entered as a risk officer and left as a committed evaluator — the inflection point was quantified operational cost, not features or brand. Samantha's "I'd be deleting it, not rebuilding it" signals she has mentally moved past evaluation into adoption, which makes her a second strong champion if the deal stalls.

---

## Coaching Spotlight

**Sarah Chen:** Strength: Flawless multithreading — orchestrated three stakeholders with distinct concerns and locked specific deliverables with zero ambiguity. Gap: When Marcus quantifies rollback ROI, make the bridge explicit — connect the 25-min figure back to Dmitri's original risk concern in your own words.

**Marcus Webb:** Strength: Objection handling converted two skeptics in real time through technical depth and concrete ROI — especially the Datadog integration moment. Gap: None material this call.

---

## Product Signals

| Product | Intensity | Prospect Context |
|---|---|---|
| **Atomic Rollbacks** | 🔴 High | 25 min → 30 sec ROI moved Dmitri from skeptic to commitment — the deal anchor. |
| **Datadog Integration** | 🔴 High | Native webhooks + log drains converted Samantha: "cleaner than what we've built." |
| **Deploy Previews** | 🔴 High | Yuki validation: "exactly what I showed Dmitri in my trial." |

---

## Next Steps

1. **Sarah (AE):** Deliver fintech reference customer (2+ years, similar profile) — by Wed Jan 29
2. **Sarah (AE):** Draft change-of-control clause language for term sheet — by Fri Jan 31
3. **Marcus (SE):** Phased migration plan (8 sites, start with internal tool, 1-sprint cadence) + Datadog integration guide — by Fri Jan 31
