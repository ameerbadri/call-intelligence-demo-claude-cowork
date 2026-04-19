# MEDDPICC Reference — Generic B2B SaaS

**Purpose:** Framework definitions for scoring deal qualification from call transcripts.
Used by analysis subagents to assess what was learned about deal health on each call.

MEDDPICC is an acronym: **M**etrics, **E**conomic Buyer, **D**ecision Criteria,
**D**ecision Process, **P**aper Process, **I**dentified Pain, **C**hampion, **C**ompetition.

---

## Scoring Scale

Each component is scored as one of three values:

| Score | Meaning |
|-------|---------|
| `identified` | Clearly established with direct evidence from the call |
| `partially` | Touched on but incomplete, vague, or unconfirmed |
| `not_addressed` | Not raised, not explored, or not applicable to this call |

**Include a one-line evidence note per component** citing what was said.
If a component cannot be assessed (e.g., a pure technical call won't surface Paper Process),
mark as `not_addressed` and note why.

---

## Component Definitions

### M — Metrics

**What it measures:** The quantifiable success criteria the prospect will use to evaluate
whether your solution delivers value.

**Strong "identified" signals:**
- Prospect states specific, measurable targets: "We need to cut deploy time from 45 minutes to under 10"
- Quantified cost or inefficiency: "Our DevOps team spends 30% of their time on deployment tooling"
- Revenue or growth impact: "We're releasing features 2x slower than our roadmap requires"
- Benchmark comparisons: "Our competitor shipped 3 features while we were still in QA on one"

**"Partially" signals:**
- Prospect acknowledges the problem but can't quantify it: "Deploys are slow, it's painful"
- Vague scale: "We're a high-growth team" without specifics
- AE/SE asked but got deflected

**"Not addressed" signals:**
- No metrics discussion happened
- Too early (intro call with no agenda to go deep)
- Internal metrics not yet available

---

### E — Economic Buyer

**What it measures:** Whether the person who controls the budget and has final purchase
authority has been identified (and ideally engaged).

**Strong "identified" signals:**
- Economic buyer named and on the call, or explicitly referenced: "Our VP of Engineering
  will sign off — she's reviewing our platform spend this quarter"
- Budget authority confirmed: "I have discretionary budget for tools up to $50K"
- Next step is explicitly to meet the EB

**"Partially" signals:**
- Economic buyer mentioned but not engaged: "I'll need to loop in my manager"
- Role implied but not confirmed: "My CTO will care about this"
- Champion hasn't been asked directly who owns the budget

**"Not addressed" signals:**
- Single contact, no mention of anyone else in the decision
- Champion deflects or avoids the topic

---

### D — Decision Criteria

**What it measures:** The explicit factors the prospect will use to evaluate and compare vendors.

**Strong "identified" signals:**
- Prospect states evaluation criteria directly: "We're scoring vendors on DX, framework support,
  edge compute capability, and enterprise support quality"
- Criteria are prioritized: "Security and compliance is non-negotiable; everything else is secondary"
- Formal scorecard or RFP exists

**"Partially" signals:**
- Some criteria mentioned but not prioritized or complete
- AE/SE surfaced criteria but prospect gave vague answers
- Criteria mentioned in passing, not confirmed as evaluation factors

**"Not addressed" signals:**
- No discussion of how they'll choose
- Too early in the process

---

### D — Decision Process

**What it measures:** Who is involved in the decision, how they'll evaluate, and what the
formal process looks like.

**Strong "identified" signals:**
- Full stakeholder map: "It's me (technical), our CTO (strategic), and procurement"
- Process steps defined: "We'll do a 2-week trial, then bring it to the leadership team"
- Timeline established: "We need a decision by end of Q2 because of a board commitment"

**"Partially" signals:**
- Some stakeholders mentioned but others implied or unknown
- General process described but no timeline
- "We'll figure out the process as we go"

**"Not addressed" signals:**
- Single contact, no discussion of how decisions get made
- Champion hasn't been asked or deflected

---

### P — Paper Process

**What it measures:** The procurement, legal, and contracting steps required to execute
the deal — and how long they take.

**Strong "identified" signals:**
- Procurement process described: "We use Coupa for all vendor contracts over $10K"
- Legal review timeline known: "Our legal team typically takes 2-3 weeks for SaaS MSAs"
- Security review process surfaced: "We need to complete a vendor security questionnaire"
- Contract type established: "We'll need a PO, not a credit card purchase"

**"Partially" signals:**
- Procurement mentioned but process not described
- Security review implied but not scoped
- "There will be some procurement stuff, I'll find out"

**"Not addressed" signals:**
- No discussion of how contracts get signed
- Appropriate for early-stage deals where paper process is premature

---

### I — Identified Pain

**What it measures:** Whether the prospect's core business problem has been surfaced,
validated, and connected to urgency.

**Strong "identified" signals:**
- Pain is specific and described with consequences: "Every bad deploy costs us 2-3 hours
  of rollback time and we're releasing weekly"
- Pain is acknowledged by multiple stakeholders on the call
- Prospect has tried to solve it before: "We've patched this with scripts but it keeps breaking"
- Pain connects to a business outcome: "Slow releases are costing us customer commitments"

**"Partially" signals:**
- Pain acknowledged but not elaborated: "Yeah, deploys are painful"
- Pain is implied by the evaluation, not directly stated
- Only one stakeholder has expressed it

**"Not addressed" signals:**
- No problem discussion — purely exploratory / feature walkthrough
- Prospect seems happy with current state but is evaluating anyway

---

### C — Champion

**What it measures:** Whether there is an internal advocate inside the prospect organization
who is motivated for your solution to win, and has the ability to influence the decision.

**Strong "identified" signals:**
- Champion has taken initiative: "I've already been advocating for Acme internally"
- Champion shares internal context you wouldn't normally get: org dynamics, budget situation
- Champion commits to internal actions: "I'll set up a meeting with our CTO next week"
- Champion has credibility: title, tenure, relationship to the EB

**"Partially" signals:**
- Prospect seems positive but hasn't taken internal action
- Champion claimed but internal influence unconfirmed
- Champion is too junior to drive a decision

**"Not addressed" signals:**
- Single contact who doesn't describe any internal advocacy
- Multiple contacts but none showing champion behavior
- Champion gone quiet after initial enthusiasm

---

### C — Competition

**What it measures:** Whether the competitive landscape has been identified — who else
is being evaluated, and what the prospect's current solution is.

**Strong "identified" signals:**
- Specific competitors named: "We're also looking at Vercel"
- Current solution identified: "We're on Heroku, looking to modernize"
- Competitive position understood: "Vercel is our primary alternative because the team uses Next.js"
- Prospect has shared evaluation status: "We're down to you and Vercel"

**"Partially" signals:**
- "We're looking at a few options" without specifics
- Current solution known but no competitive evaluation mapped
- Competitor mentioned once in passing, not explored

**"Not addressed" signals:**
- No competitive discussion
- Appropriate if it's a clear-field evaluation with no competitive pressure

---

## Using MEDDPICC in Stage-Aware Analysis

Not every component is equally relevant at every stage. Use this to calibrate
what gaps are serious vs. expected:

| Stage | Critical to Have | Acceptable to Be Missing |
|-------|-----------------|------------------------|
| Discovery | Identified Pain, initial Metrics signal | Economic Buyer, Paper Process |
| Technical Eval | Decision Criteria, Competition | Paper Process, full Decision Process |
| Champion Building | Champion, Economic Buyer, Decision Process | Paper Process |
| Late Stage | Economic Buyer, Paper Process, Decision Process | Metrics (already established) |

A missing component that is critical for the deal's current stage is a **deal risk**.
A missing component that is premature for the stage is **expected and not a risk**.
