---
company: CascadeHealth
date: 2026-01-16
ae_name: Jordan Reeves
se_name: Marcus Webb
deal_stage: technical_eval
deal_health: 75
deal_outcome: active
call_purpose: technical_scoping
next_step_quality: 5
discovery_quality: 4
ae_discovery_score: 4
ae_multithreading_score: 4
ae_objection_handling_score: 4
ae_value_articulation_score: 4
ae_next_step_score: 5
se_technical_depth_score: 5
se_demo_effectiveness_score: 5
se_discovery_contribution_score: 5
se_objection_handling_score: 5
meddpicc_metrics: identified
meddpicc_economic_buyer: partially
meddpicc_decision_criteria: partially
meddpicc_decision_process: identified
meddpicc_paper_process: partially
meddpicc_identified_pain: identified
meddpicc_champion: identified
meddpicc_competition: identified
meddpicc_notes: "M:28-35min builds,240 routes,8-10 deploys/wk|E:CISO controls security gate, budget authority TBD|DC:SOC2/BAA/data residency/pen test required|DP:Trial Fri+security review+contract by Jan22|PP:BAA template to follow, legal process TBD|IP:Build time bottleneck (4hrs/wk overhead), marketing content blocked by 30min manual loop, HIPAA compliance review Q2|Ch:Priya Das (Snr Platform Engr) driving PoC, internal advocate|Co:AWS Amplify incumbent, no formal competitive eval"
spiced_situation: 5
spiced_pain: 5
spiced_impact: 4
spiced_critical_event: 5
spiced_decision: 4
tension_flag: false
behavioral_trust_trajectory: Improving
behavioral_emotional_mismatch: false
behavioral_champion_health: Strong
talk_ratio_seller: 52
talk_ratio_prospect: 48
competitive_mentions:
  - AWS Amplify
product_signals:
  - Acme Sites (build caching)
  - Acme Connect (Contentful integration)
  - Data residency (US-only builds)
  - BAA (Business Associate Agreement)
red_flags: []
duration_minutes: 55
---

# CascadeHealth — Technical Validation + Security Clearance

## Deal Summary

Cascade Health (healthcare software for hospital systems) is evaluating Acme to replace AWS Amplify — driven by two discrete pains: build times degrading (28-35 min for 240-route Next.js app, 8-10 deploys/week = ~4 hours/week waste) and HIPAA compliance friction (CISO flagged Amplify's documentation gaps). Security review is the critical path (CISO approval needed by Jan 30); technical trial Friday validates build performance and Contentful integration. **Deal health: 75/100 — Strong momentum, but CISO gate and Jan 31 decision date create schedule risk.**

---

## Scores — SE

| Dimension | Score | Evidence |
|-----------|-------|----------|
| **Technical Depth** | 🟩🟩🟩🟩🟩 | Marcus mapped architecture (PHI backend, frontend shell), dependency caching logic, ISR vs SSR patterns, US-region data residency constraints — no confusion, all specifics confirmed with Priya. |
| **Demo Effectiveness** | 🟩🟩🟩🟩🟩 | Walked acme.toml build config with real numbers: 28-35 min → 5-8 min (10-15% changes), 15-18 min (major releases); tied to Priya's actual deploy frequency. |
| **Objection Handling** | 🟩🟩🟩🟩🟩 | Leo's pen test concern met with written policy + Amplify comparison; data residency objection solved with specific config (US-only builds, global CDN). Prospect gave "cleaner than Amplify." |

---

## Scores — AE

| Dimension | Score | Evidence |
|-----------|-------|----------|
| **Multithreading** | 🟩🟩🟩🟩⬜ | Identified Priya (technical champion), Leo (security gate), CISO (sponsor); created parallel workstreams (trial + security review), but economic buyer not yet engaged directly. |
| **Next Step Quality** | 🟩🟩🟩🟩🟩 | Four mutual next steps: (1) Jordan sends security materials today; (2) Marcus + Priya trial Friday; (3) Leo flags blockers by Jan 20; (4) contract discussions Jan 22. Each owned, dated, committed. |

---

## MEDDPICC Snapshot

- **Metrics:** Build time (28-35 min), deploy frequency (8-10/week), trial target (5-8 min for typical changes)
- **Champion:** Priya Das — driving trial scope, internal advocate, technical credibility
- **Decision Process:** Security review (2 weeks) → trial Friday → contract Jan 22 → decision by Jan 31
- **Critical Risk:** CISO review is external bottleneck; Jan 20 midpoint check-in prevents late surprises
- **Competition:** AWS Amplify incumbent; implicit differentiation (BAA responsiveness, pen test policy clarity)

---

## Risk & Momentum

| Signal | Severity | Implication |
|--------|----------|-------------|
| **CISO review (2 weeks) is critical path** | 🔴 | If Cascade's CISO raises new concerns after receiving materials today, only 10 days remain to resolve before Jan 20 check-in. Jordan's midpoint check-in mitigates but doesn't eliminate. |
| **Trial scope is specific and real** | 🟢 | Marcus running trial on actual Cascade app Friday, not a representative app. Caching behavior depends on dependency graph — real numbers by Monday validates promise. |
| **Security objections turning into validation gates** | 🟢 | Leo started skeptical ("documentation gaps"), is ending engaged ("cleaner than Amplify"). SOC 2, BAA, pen test policy materials send today; Leo's tone suggests he's looking for reasons to say yes, not no. |

---

## The Unsaid

Leo's caution about CISO veto is genuine but not blocking — his questions (SOC 2, BAA, data residency) were answered clearly and specifically, which Amplify didn't do. The real momentum is that Priya owns the technical decision and is ready to validate build performance Friday; if that trial delivers (5-8 min builds), Leo's security review becomes procedural rubber-stamp rather than a genuine gate. The tightness of the Jan 31 decision date suggests internal urgency — likely a Q1 budget cycle or migration window.

---

## Coaching Spotlight

**Marcus:** Exceptional discovery + technical translation. Asked clarifying questions before proposing (PHI storage, ISR usage), validated architecture assumptions, then showed impact with specific numbers tied to Cascade's actual workload. Strength: thinking like a partner, not a vendor.

**Jordan:** Strong facilitation and gate-keeping. Identified the critical path (CISO review), built in midpoint check-in to prevent surprise blockers, and staged parallel workstreams. One gap: didn't probe economic buyer/budget authority yet — wait for after trial success.

---

## Product Signals

| Product | Intensity | Context |
|---------|-----------|---------|
| **Build Caching** | High | Core pain driver: 28-35 min builds → 5-8 min for typical deploys. Directly tied to deploy frequency (8-10/week). |
| **Acme Connect (Contentful)** | Medium | Secondary pain: marketing content publishing bottleneck (30+ min manual loop). Trial scope includes automated flow demo. |
| **Data Residency (US-only)** | High | Security-specific requirement; CISO concern; Marcus's ability to configure US-region builds is table-stakes for healthcare. |

---

## Next Steps

1. **Jordan** — Send security materials (SOC 2 under NDA, BAA template, pen test policy, completed questionnaire) **today**
2. **Marcus + Priya** — Run live trial on actual app, demonstrating build caching and Contentful integration **Friday**
3. **Leo** — Flag security blockers to Jordan **by Jan 20**
4. **Jordan + Priya** — Move to contract negotiations **week of Jan 22** if trial delivers and security review is clean
