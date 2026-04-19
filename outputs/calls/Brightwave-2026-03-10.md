---
company: Brightwave
call_date: 2026-03-10
call_duration_minutes: 38
participants:
  - name: Sarah Chen
    role: AE (Acme)
    seat: sales
  - name: Jordan Kim
    role: Engineering Manager
    seat: prospect
  - name: Priya Patel
    role: Senior Frontend Engineer
    seat: prospect
call_purpose: discovery
deal_stage: discovery
deal_health_score: 65
deal_health_status: moderate
frameworks:
  meddpicc:
    M: identified
    E: identified
    DC: partially
    DP: identified
    PP: not_addressed
    IP: identified
    Ch: identified
    Co: partially
  spiced_composite: 4
  spiced_breakdown:
    S: 5
    P: 5
    I: 4
    C: 5
    D: 4
ae_scores:
  ae_name: Sarah Chen
  spiced_discovery: 4
  multithreading: 3
  next_step_commitment: 5
  objection_handling: 4
  commercial_progression: 3
behavioral_dynamics:
  trust_trajectory: improving
  champion_health: moderate
  emotional_mismatch: false
se_scores: null
red_flags:
  - no_multithreading
  - competitor_threat
  - incomplete_discovery
product_signals:
  - product: Deploy Previews
    intensity: high
    evidence: Staging conflict is primary pain; 8 frontend engineers competing for shared staging
  - product: Acme Sites (build system)
    intensity: high
    evidence: 18-22 min Next.js builds critical bottleneck; build optimization is deal-make factor
  - product: Acme Functions
    intensity: low
    evidence: Not mentioned; all backend on AWS ECS

---

# Brightwave — 2026-03-10

> **Discovery** · 38 min · Deal Health: **65/100**

| | |
|---|---|
| **Seller Team** | Sarah Chen (AE) |
| **Prospect** | Jordan Kim (Engineering Manager), Priya Patel (Senior Frontend Engineer) |
| **Deal Stage** | Discovery |
| **Next-Step Grade** | 🟢 Trial, technical session, and EB conversation all scheduled |

---

## Deal Summary

Brightwave (65 engineers, Next.js on Heroku) is spending 25-30% of engineering time on deployment maintenance — 30-40 min deploys and a staging environment overloaded by 8 frontend engineers competing for one shared slot. Q2 product launch is locked for May; platform must be live by mid-April. Budget exists ($2k/month discretionary), but Vercel is actively in consideration and the economic buyer (Rebecca Lam, VP Eng) has not been engaged.

---

## Scores

### AE — Sarah Chen

| Dimension | Score | Evidence |
|---|---|---|
| **Discovery** | 🟩🟩🟩🟩⬜ | Mapped situation → pain → impact → timeline in proper sequence; quantified 25-30% eng time and 18-22 min build cycles without leading. |
| **Objection Handling** | 🟩🟩🟩🟩⬜ | Acknowledged Vercel's Next.js DX as "genuinely strong" rather than dismissing it — builds credibility for a nuanced competitive play. |
| **Next-Step Commitment** | 🟩🟩🟩🟩🟩 | Trial (EOW), technical session with Marcus (Tue Mar 17), business-case call with Rebecca — all locked with owners and dates. |

### MEDDPICC

**M:** 25-30% eng time on maintenance; 18-22 min builds; 2 missed customer commitments · **E:** Rebecca Lam (VP Eng) — $2k/month discretionary; not yet engaged · **DC:** Build time optimization, Deploy Preview staging fix — pricing model not yet discussed · **DP:** Jordan owns eval → Rebecca approves; hard deadline mid-April · **PP:** Not discussed · **IP:** Staging conflict (8 engineers, 1 environment) + 30-40 min deploys + 25-30% eng time bleed · **Ch:** Jordan Kim (strong, owns decision) + Priya Patel (moderate — Vercel preference is a risk) · **Co:** Vercel in active consideration; Priya leans toward it on DX; no trial yet

---

## Risk & Momentum

| Severity | Signal | Detail |
|---|---|---|
| 🔴 | **Vercel preference + no competitive trial** | Priya controls the trial outcome; if she's already decided Vercel's DX is superior, trial defaults to "Vercel is great." Trial must be reframed as head-to-head, not solo validation. |
| 🟡 | **Economic buyer not engaged** | Rebecca Lam hasn't been in any conversation; if she has pricing or ROI questions, deal stalls after trial results come back. |
| 🟡 | **Pricing not discussed** | If Acme's pricing at Brightwave's scale is materially higher than Vercel, the deal ends. Sarah needs a payback calculation before trial. |

---

## The Unsaid

Neither Jordan nor Rebecca has been sold on the business case — they see the pain but haven't had the ROI story made explicit. If Sarah can show Acme cuts 15+ min off build time and solves the staging conflict, engineering time savings alone justify the switch; but that math needs to be built and presented to Rebecca before she sees trial results, not after.

---

## Coaching Spotlight

**Sarah Chen:** Strength: Structured discovery with credibility-first competitive positioning — quantified pain without pitching, and acknowledged Vercel's DX strength rather than dismissing it. Gap: Engage Rebecca before trial results arrive and reframe the trial as a head-to-head comparison — otherwise Priya's Vercel preference becomes the default outcome.

---

## Product Signals

| Product | Intensity | Prospect Context |
|---|---|---|
| **Deploy Previews** | 🔴 High | Staging conflict is the #1 pain — 8 engineers sharing one environment. Deal-make feature. |
| **Acme Sites (build system)** | 🔴 High | 18-22 min builds are unacceptable; build optimization is critical to trial outcome. |
| **Acme Functions** | ⬜ Not mentioned | Backend is AWS ECS — not in scope. |

---

## Next Steps

1. **Priya Patel (Prospect):** Deploy feature branch to Acme, test Deploy Preview + build time vs. Heroku — by EOW Mar 13
2. **Sarah + Marcus (AE/SE):** Technical session with Jordan/Priya — Next.js build caching, Deploy Previews, SOC 2 — Tue Mar 17
3. **Sarah (AE):** Business-case call with Rebecca Lam — quantify engineering time ROI (~$80K/yr saved) before trial results — before Mar 20
