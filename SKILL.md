---
name: call-intelligence
description: |
  Analyzes B2B sales call transcripts and produces persona-specific intelligence
  for Sales, SE, Product, and Marketing leaders. Each transcript runs in its own
  opus subagent (1 per subagent, no cross-call contamination). Subagents write a
  single .md file with YAML frontmatter (structured data) + visual markdown body
  (the Intelligence Brief). Three competitive intelligence outputs (Sales, Marketing,
  Product) are produced on demand across a call corpus.
  See CLAUDE.md for full architecture and rules.
---

# Call Intelligence — Cowork Skill

## What This Does

Turns raw sales call transcripts into structured, persona-specific intelligence.
One transcript in → one Intelligence Brief out, plus optional cross-call CI.

**Per-call output (T1 Intelligence Brief):**
- AE coaching: discovery quality, objection handling, next-step execution
- SE coaching: technical depth, demo effectiveness, architecture coverage
- Deal health: MEDDPICC scoring, risk signals, momentum indicators
- Champion & Stakeholder Dynamics: trust trajectory, behavioral read, The Unsaid
- Product signals: what came up, at what intensity, and what was missing

**Cross-call output (Competitive Intelligence):**
- CI Sales: battlecard, objection handling, win/loss patterns
- CI Marketing: ICP messaging, competitive positioning, content gap priorities
- CI Product: feature gap analysis, competitive roadmap signals

---

## Workflow: Per-Call Analysis

### Step 1 — Confirm Scope

List the transcript files found in `transcripts/`. Show:
- Filename (company + date)
- Estimated call length (if determinable from file size)
- Whether it's in scope for analysis

Wait for user confirmation before proceeding.

### Step 2 — Load Reference Materials

Read ALL of the following into the parent context before launching any subagents:

```
reference/product-context.md
reference/qualification-criteria.md
reference/meddpicc-reference.md
reference/spiced-reference.md
reference/behavioral-dynamics-reference.md
reference/output-templates.md
```

### Step 3 — Launch Analysis Subagents

For each transcript, launch ONE opus subagent. Maximum 5 in parallel.

**Subagent prompt template:**

```
You are a Sales Intelligence Analyst. Analyze the following sales call transcript
and produce a single Intelligence Brief as specified in the output template.

COMPANY CONTEXT:
{full content of reference/product-context.md}

QUALIFICATION CRITERIA:
{full content of reference/qualification-criteria.md}

MEDDPICC REFERENCE:
{full content of reference/meddpicc-reference.md}

SPICED REFERENCE:
{full content of reference/spiced-reference.md}

BEHAVIORAL DYNAMICS:
{full content of reference/behavioral-dynamics-reference.md}

OUTPUT TEMPLATE:
{full content of reference/output-templates.md}

TRANSCRIPT:
{full content of the transcript file}

INSTRUCTIONS:
1. Identify the seller team members vs. prospect participants
2. Determine call purpose: discovery | technical_scoping | champion_building |
   commercial_contracting | relationship_checkin
3. Determine deal stage from signals: discovery | technical_eval | champion |
   late_stage | closed_won | closed_lost
4. Apply purpose-aware scoring — see output template for conditional section rules
5. Enumerate evidence for/against before scoring any dimension
6. Apply density caps strictly — do not exceed them
7. Write the output file to: outputs/calls/{Company_Name}-{YYYY-MM-DD}.md
8. File must begin with YAML frontmatter (all structured data) followed by
   the visual markdown body. See output template for exact format.
```

### Step 4 — Validate Output

After each subagent returns, verify:
- YAML frontmatter is present and valid
- All required sections are present
- Density caps were respected (3 risks, 3 next steps, 2 coaching points per person)
- File is saved to the correct path

### Step 5 — Confirm & Summarize

Report back to user:
- How many calls were analyzed
- Deal health scores for each
- Top 2-3 flags across the batch
- Offer to proceed to Competitive Intelligence aggregation

---

## Workflow: Competitive Intelligence

Triggered explicitly by the user after per-call analysis is complete.

### Step 1 — Identify Competitive Calls

Scan the YAML frontmatter of analyzed call reports for `competitive_mentions`.
List companies mentioned and call count per competitor. Wait for confirmation.

### Step 2 — Aggregation Subagent (Opus)

Launch ONE subagent with:
- All YAML frontmatter from competitive calls (not the full markdown bodies)
- Full content of `reference/product-context.md`
- Instruction to produce `outputs/competitive-intelligence/{period}-competitive-raw.md`

This is an intermediate artifact — structured competitive signal extraction,
not a polished deliverable.

### Step 3 — Output Subagents (Parallel)

Launch THREE subagents in parallel, each reading the raw competitive file:

**CI Sales:**
Produce `outputs/competitive-intelligence/{period}-CI-sales.md`
- Top 5 Actions (appears FIRST)
- Objection handling by competitor
- Win/loss pattern analysis
- Training scenarios (3-5 realistic prospect challenges)

**CI Marketing:**
Produce `outputs/competitive-intelligence/{period}-CI-marketing.md`
- Top 5 Actions (appears FIRST)
- ICP messaging playbook by buyer persona
- Competitive positioning by use case
- Content gap priorities

**CI Product:**
Produce `outputs/competitive-intelligence/{period}-CI-product.md`
- Top 5 Actions (appears FIRST)
- Feature gap analysis by competitor
- Competitive roadmap signals from prospect conversations
- Partner/ecosystem intelligence

### Step 4 — Design Rule Reminder

Every CI document must open with **Top 5 Actions**. Analysis exists to justify
actions, not the other way around. Every finding must pass: "does this change
what a leader does tomorrow?"

---

## Trigger Phrases

**Per-call analysis:**
- "Analyze the transcripts"
- "Run call intelligence on [company/date]"
- "Generate Intelligence Briefs"

**Competitive intelligence:**
- "Generate competitive intelligence"
- "Build the CI report"
- "Run CI for Q[N]-[YYYY]"

---

## Outputs

Run the pipeline on the existing transcripts to reproduce them — or drop in your own
transcripts and generate fresh intelligence.
