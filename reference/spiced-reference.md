# SPICED Reference — Generic B2B SaaS

**Purpose:** Framework for scoring AE discovery quality from call transcripts.
SPICED measures *how well the AE conducted discovery*, not what information was
established. It is the counterpart to MEDDPICC.

SPICED stands for: **S**ituation, **P**ain, **I**mpact, **C**ritical Event, **D**ecision.

---

## SPICED vs. MEDDPICC — The Key Distinction

**MEDDPICC** measures what you know about the deal (the output of good discovery).
**SPICED** measures how well the AE ran the discovery conversation (the quality of the process).

An AE can have a high MEDDPICC score because a prospect volunteered information without
being asked — and a low SPICED score because the AE didn't drive the conversation.
Conversely, strong SPICED execution usually leads to strong MEDDPICC outcomes over time.

Assess them independently.

---

## Composite Score: 1-5

SPICED is scored as a single composite dimension (1-5) based on how many stages were
covered and the depth achieved in each:

| Score | Meaning |
|-------|---------|
| 5 | Exceptional — all 5 stages covered with depth; AE drives insight, not just information |
| 4 | Strong — 4 of 5 stages covered well, minor gaps |
| 3 | Adequate — situational foundation + some pain exploration; impact and critical event weak |
| 2 | Below standard — mostly situational; pain surface-level; no impact or urgency work |
| 1 | Concerning — AE collected basic context but didn't discover; feels like a tour not a conversation |

---

## The Five Stages

### S — Situation

**What to assess:** Did the AE understand the prospect's current state *before* proposing solutions?

**Strong Situation exploration looks like:**
- AE maps the current environment: tools, processes, team structure, scale
- Questions are open and broad before going narrow: "Walk me through how you currently handle X"
- AE doesn't assume the current state — they ask and listen
- Situation is confirmed with specifics, not generalities

**AE behaviors that signal strong Situation:**
- "Walk me through your current deployment workflow"
- "How does your team structure work — who owns the frontend infrastructure?"
- "What does your stack look like today?"
- "How long have you been on [current solution]?"

**Warning signs:**
- AE launches into demo or pitch before understanding current state
- AE assumes the situation based on company size or industry
- Questions are closed: "Are you using GitHub?" instead of "Tell me about your version control setup"

---

### P — Pain

**What to assess:** Did the AE surface the specific, felt problem — not just acknowledge
that problems exist?

**Strong Pain exploration looks like:**
- AE probes below surface symptoms to root cause: "When deploys take 45 minutes, what happens
  to your release cycle? What does that cost you?"
- Multiple pain sources surfaced (not just the first one mentioned)
- Pain is validated as real, not hypothetical: "Has this cost you a customer or a release yet?"
- Pain is specific and owned: "Our DevOps lead spends 30% of their time on this"

**AE behaviors that signal strong Pain:**
- "Can you say more about why that's painful — what actually happens when it breaks?"
- "How long has that been a problem? Have you tried to fix it before?"
- "Who else feels this pain — is this just your team or is it wider?"
- "What's the worst thing that's happened because of this?"

**Warning signs:**
- AE accepts "deploys are slow" at face value without probing
- AE moves on to the next topic after first acknowledgment of pain
- AE pitches their solution as soon as pain is mentioned

---

### I — Impact

**What to assess:** Did the AE connect the pain to business consequences — revenue,
cost, risk, or strategic delay?

**Strong Impact exploration looks like:**
- Pain quantified in business terms: "So this is costing you roughly 2 engineer-weeks per quarter?"
- Impact tied to what leadership cares about: "If releases slip, how does that affect commitments
  you've made to the product org or customers?"
- Impact is confirmed by the prospect, not just asserted by the AE
- Both quantitative (time, money) and qualitative (risk, morale, competitive position) impact surfaced

**AE behaviors that signal strong Impact:**
- "If you fixed this tomorrow, what would change for your team?"
- "What's the business impact of releasing features 2x slower than you want?"
- "Has this affected any commitments you've made to customers or the business?"
- "How much engineer time is this consuming — have you ever tried to quantify it?"

**Warning signs:**
- AE never connects pain to business consequences
- AE talks about their product's impact instead of asking the prospect to describe theirs
- Prospect can't describe impact — AE didn't probe

---

### C — Critical Event

**What to assess:** Did the AE surface a compelling event that creates urgency —
a reason this gets decided now rather than later?

**Strong Critical Event exploration looks like:**
- Specific date or event identified: "We're launching in Q3 — we need this resolved before then"
- Consequence of inaction is clear: "If we don't solve this before the product launch, we'll miss the window"
- Critical event is external (not just "we'd like to get this done")
- AE explicitly asks: "What happens if you don't solve this in the next 90 days?"

**AE behaviors that signal strong Critical Event work:**
- "What's driving the timing on this? Is there a specific event or deadline?"
- "If this slips to next quarter, what does that mean for you?"
- "What changes after [event]? Does the urgency shift?"
- "Is there anything that would make this more urgent — a product launch, a compliance date, a headcount decision?"

**Warning signs:**
- No urgency discussion — AE accepts "we'll figure out the timeline" without probing
- Critical event is discovered to be soft ("it would be nice to get this done Q2")
- AE doesn't ask about consequences of inaction

---

### D — Decision

**What to assess:** Did the AE map how the prospect makes decisions — who's involved,
what the process is, and what criteria will be used?

**Strong Decision exploration looks like:**
- Decision-maker map established: "So it's you and your CTO making this call together?"
- Process understood: "What does a typical vendor evaluation look like for your team?"
- Criteria surfaced: "What would make this a clear yes for you?"
- Timeline agreed: "What's your target decision date?"

**AE behaviors that signal strong Decision work:**
- "Beyond you, who else needs to weigh in on this?"
- "How have you made decisions like this in the past?"
- "What would it take for you to feel confident recommending this internally?"
- "Is there a specific date you need a decision by — a budget cycle, a project kickoff?"

**Warning signs:**
- AE doesn't ask who else is involved in the decision
- No mutual next steps — AE proposes the next step but prospect doesn't commit
- Decision criteria never surfaced
- AE assumes the process based on company size

---

## Scoring Examples

**SPICED = 5:**
AE opens with broad situational questions, maps the current stack and team structure.
Surfaces specific pain ("we've missed two release windows this quarter"). Quantifies
impact ("that's roughly $40K in delayed features"). Uncovers a hard deadline ("we need
to be production-ready before Black Friday"). Confirms who's in the decision and
what criteria they'll use. Closes with a mutual next step both parties commit to.

**SPICED = 3:**
AE gets good situational context — understands the team structure, current tool,
and scale. Surfaces pain clearly ("deploys are slow and manual"). Doesn't quantify
impact — accepts the pain acknowledgment without going deeper. Asks about timeline
vaguely ("what's your target?") but gets a soft answer ("this quarter maybe?") and
doesn't probe. Misses critical event entirely. Next step is seller-proposed, not mutual.

**SPICED = 1:**
AE asks a few situational questions then moves into a product overview. Pain is
mentioned by the prospect but AE immediately pivots to "great — here's how we solve
that." No impact, no urgency, no decision process explored. Call ends with "I'll
send you some materials" — no committed next step.
