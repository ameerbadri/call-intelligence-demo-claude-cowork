# Marketing CI Brief — Q1 2026

> **10 competitive calls analyzed** | Representing 10 prospect companies across healthcare, fintech, e-commerce, media, SaaS, and retail

---

## ⚡ Top 5 Actions
*What marketing should do differently starting this week*

1. **Create "TCO Reality Check" asset comparing per-invocation vs. bandwidth pricing across traffic scales** — Vercel's per-invocation model is Acme's primary vulnerability *and* primary value driver. ZephyrMedia's $6K→$22K cost spike and Meridian's 0.5 FTE maintenance tax are repeatable playbooks. Marketing must make TCO math visible early, not leave it to closing.

2. **Build "Atomic Rollback Operational ROI" calculator + case study library** — Ironbridge's 25-minute rollback window → 30-second atomic rollback, and Meridian's 5-minute Deploy Preview cycle vs. 40-minute staging, are visceral, repeatable proof points. Create a one-pager showing error budget math + revenue impact. This is Acme's strongest competitive wedge.

3. **Develop compliance responsiveness as enterprise positioning** — Healthcare/fintech prospects (CascadeHealth, Meridian, TechFlow) expect fast, specific BAA/SOC 2 documentation. Marcus's 24-hour written answers to CISO questions shifted Meridian's decision. Marketing should position "enterprise support responsiveness" as distinct advantage vs. AWS's generic bureaucracy.

4. **Launch comparative "Build Speed Matters" campaign with benchmarks** — Four calls (CascadeHealth 28-35 min, Ironbridge 25 min, Meridian 40+ min, Brightwave 30-40 min) show build time as universal pain at scale. Create benchmark data comparing Amplify/Vercel/Cloudflare across real monorepo scenarios. This content is shareable with engineering teams pre-sales.

5. **Reposition "Framework-Agnostic" from weakness to strength** — Brightwave and TechFlow both articulated Vercel's Next.js advantage, but it's not a product blocker (both companies explored Acme seriously). Marketing messaging should flip this: "Framework expertise matters; platform lock-in matters more at scale. Your stack will evolve—you want a platform that evolves with it."

---

## ICP Signals from Competitive Deals

*Who is actively evaluating competitors and choosing us (or not). Use to sharpen audience targeting.*

| Company Profile | Title/Role | Primary Pain | Competitor Context | What Tipped It |
|----------------|-----------|-------------|-------------------|---------------|
| **Media/Publishing, 350M→2.4B req/month, high growth** (ZephyrMedia) | Cassandra Bell (VP Eng), Raj Patel (Staff Eng) | Cost unpredictability at 8x traffic inflection | Vercel incumbent, 10% discount insufficient | Per-invocation model is structural problem; Acme bandwidth model = cost certainty |
| **Healthcare IT, 240-route Next.js, SOC 2 required** (CascadeHealth) | Priya Nair (Tech Lead), Leo (Security Lead) | Build time 28-35 min, security compliance timeline | AWS Amplify incumbent | Acme's specific BAA + pen test policy + 5-8 min builds > Amplify's generic AWS BAA |
| **Fintech, 14 FEs, 8 sites, atomic rollback critical** (Ironbridge) | Dmitri Volkov (Dir Eng), Samantha Cho (Platform), Yuki Tanaka (FE Lead) | 25-min rollbacks erode error budget; observability fragile | Amplify incumbent, Cloudflare Pages alternative | Atomic rollback ROI + native Datadog integration resolved operational skepticism |
| **E-commerce platform, checkout optimization** (StrataCommerce) | Alicia Nguyen (Senior FE), Wei Zhang (CTO) | Cloudflare Workers CPU limits block personalization logic | Cloudflare Pages incumbent | Acme edge function runtime + 12% conversion lift in trial > ecosystem consolidation concern |
| **SaaS, 65 engineers, 3.25x growth, staging bottleneck** (Brightwave) | Jordan Kim (EM), Priya Patel (Senior FE), Rebecca Lam (VP Eng) | 30-40 min deploys, 8 FEs sharing single staging env | Vercel preference (unstated) | Build speed + Deploy Previews isolate each engineer; Vercel trial pending |
| **B2B SaaS analytics, post-incident risk focus** (PolarAnalytics) | Theo Marsh (FE Lead), Yael (CTO, absent) | Atomic rollback, risk reduction post-outage | Amplify incumbent, Cloudflare Pages new | Atomic rollback value clear; champion hesitant to advocate (CTO risk-averse) |
| **Healthcare tech, CISO-driven procurement** (Meridian) | Rachel Kim (VP Eng), Daniel Osei (FE Lead) | Build cycle 30+ min, enterprise compliance, CFO budget pressure | Amplify incumbent | 5-min Deploy Preview UX demo + 0.5 FTE TCO savings + contractual SLA > Amplify's bureaucracy |

**ICP patterns observed:**

- **High-growth/scaling companies** (ZephyrMedia, Brightwave, TechFlow, StrataCommerce) are price-sensitive at 5M+ requests/month or 3x+ team growth inflection points. Per-invocation costs become visceral pain. **Opportunity:** Position Acme in landing pages targeting "rapid growth SaaS" with cost calculator.

- **Healthcare/fintech/compliance-heavy verticals** are most vulnerable to Amplify displacement. They weight compliance responsiveness (24-hour BAA turnaround) and contractual clarity (explicit SLAs) above feature comparison. **Opportunity:** Create vertical-specific compliance collateral; lead with support SLA clarity.

- **Operational pain compounds at scale:** Build times 25-40+ minutes, non-atomic rollbacks, fragile observability integrations. These are universal at 10+ engineers. **Opportunity:** Create "operational velocity benchmark" report showing build time + rollback speed across platforms.

- **Framework preference (Vercel/Next.js) is sticky but testable:** Brightwave and TechFlow both acknowledged Vercel's advantage but didn't rule out Acme. **Opportunity:** Frame trial design as "competitive comparison," not "Acme evaluation."

- **Infrastructure consolidation narrative (Cloudflare) is powerful but defeatable:** Ironbridge and PolarAnalytics tempted by "one throat to choke" but Acme's architecture clarity + operational advantages won. **Opportunity:** "Layering, not replacement" messaging for Cloudflare competition.

---

## Messaging Playbook by Persona

### Engineering Manager / Director of Engineering

- **What they care about (from Q1 calls):** Release velocity, staging bottlenecks, team friction on shared environments. Rachel (Meridian) cited 5-min Deploy Preview cycle vs. 40-min staging; Jordan (Brightwave) managing 8 engineers competing for single staging. Build time is measured in quarters of engineering capacity.

- **What resonates:** TCO math that includes engineering hours. Meridian CFO moved when Rachel showed 0.5 FTE Amplify maintenance tax. ZephyrMedia VP Eng (Cassandra) shifted when Acme quantified 50-60% cost savings. **Messaging:** "Your staging bottleneck costs 20-30% of your frontend team's velocity. Acme Deploy Previews isolate each engineer. Here's the math."

- **What falls flat:** Generic "better DX" claims without measurement. Brightwave's Priya acknowledged Vercel's "polished DX" but trial didn't validate Acme's alternative. **Fix:** Lead with specific metrics (deploy cycle time, preview environment isolation, rollback speed), not positioning claims.

- **Competitor framing they arrive with:** "We're all-in on Next.js, Vercel feels natural." (Brightwave, TechFlow, Ironbridge) / "AWS ecosystem lock-in reduces new vendor friction." (CascadeHealth, Ironbridge) / "Cloudflare consolidates our network and hosting." (Ironbridge, PolarAnalytics)

---

### VP Engineering / CTO

- **What they care about (from Q1 calls):** Operational resilience, enterprise support clarity, compliance/procurement speed. Rachel (Meridian, VP Eng) drove decision based on atomic rollback operational ROI + contractual SLA. Dmitri (Ironbridge, Dir Eng) moved from skeptic to conviction when shown 25-min → 30-sec rollback impact on error budget.

- **What resonates:** Risk-reduction framing, not feature innovation. PolarAnalytics' Theo was technically convinced but hesitant to advocate until Acme positioned as "incident recovery speed," removing political risk from championing change. Ironbridge's Dmitri shifted when atomic rollback was quantified as error-budget preservation, not abstract architecture. **Messaging:** "Every production incident costs. Atomic rollback cuts recovery time 50x. Here's your error budget impact."

- **What falls flat:** "We support all frameworks" without explaining why it matters at their scale. TechFlow's Raj Kumar (absent) would care about framework roadmap risk; messaging to Elena (Principal Eng) that Acme is "framework-agnostic" didn't translate to a reason to switch. **Fix:** "Your framework choice will change in 3 years. Your platform shouldn't force that choice again."

- **Competitor framing they arrive with:** "Atomic rollbacks and compliance SLAs are table-stakes enterprise features." (Meridian, CascadeHealth) / "We're concerned about vendor lock-in and framework-specific optimization." (Brightwave, TechFlow, ZephyrMedia)

---

### Frontend Lead / Staff Engineer

- **What they care about (from Q1 calls):** Build speed, developer experience, edge function capabilities, trial-validated proof points. Alicia (StrataCommerce, Senior FE) unprompted built ROI spreadsheet when trial showed Acme's edge runtime could power checkout personalization. Samantha (Ironbridge, Platform Eng) moved to conviction when told "Acme native Datadog integration lets you delete custom webhook logic" (operational burden reduction).

- **What resonates:** Hands-on proof points from real trials. StrataCommerce's Alicia's business case (12% conversion lift from edge personalization) was more persuasive than any vendor benchmark. Meridian's Daniel's phone demo (5-min preview cycle) was visceral and repeatable. **Messaging:** "Run a 1-week trial on your real codebase. Measure build time, preview stability, and rollback speed. We'll show you the math."

- **What falls flat:** "Faster than X" without context on what "faster" means at their scale. Brightwave needs to know "faster deploy = unblocked engineers sharing staging," not just "5-min faster." **Fix:** "Your team shares one staging environment and can't all work in parallel. Deploy Previews give each engineer an isolated environment per PR."

- **Competitor framing they arrive with:** "Vercel's DX is genuinely strong." (Brightwave, TechFlow) / "We're building custom observability integrations because Amplify doesn't have native Datadog support." (Ironbridge) / "Cloudflare Workers' CPU limits force us to move logic server-side." (StrataCommerce)

---

### Security / Compliance Lead

- **What they care about (from Q1 calls):** BAA specificity, SOC 2 documentation speed, contractual SLA clarity, enterprise support responsiveness. Leo (CascadeHealth, Security Lead) said "Acme's BAA is better than Amplify's" after Marcus provided Amplify-specific language (not generic AWS). Rachel's CISO (Meridian) approved after Marcus delivered 24-hour written answers to technical security questions + explicit SLA in contract.

- **What resonates:** Fast, specific documentation response. Meridian's CISO concern was "I need guarantees" and Rachel said "Could show my CISO a contract that said here's what happens when something goes wrong." Speed (24-hour response) + specificity (named CSM, response-time SLA) > generic enterprise process. **Messaging:** "BAA turnaround: 24 hours. SOC 2 questionnaire: 48 hours. Named CSM with escalation path. Here's the contract language."

- **What falls flat:** Vague "enterprise support" claims or referral to "AWS enterprise support" as safety net. Amplify's slow compliance documentation was the primary objection in two healthcare deals. **Fix:** Provide pre-templated BAA, SOC 2 questionnaire responses, and pen-test policy documentation as standard collateral, not "upon request."

- **Competitor framing they arrive with:** "AWS Amplify gave us their generic AWS BAA, not Amplify-specific language." (CascadeHealth) / "My peer told me Acme has vague enterprise support." (Meridian) / "We need SOC 2 and explicit contract language before technical evaluation can proceed." (CascadeHealth, Meridian, TechFlow)

---

## Competitive Positioning by Use Case

*How to position Acme against specific alternatives for common use cases*

| Use Case | Their Go-To Alternative | Our Winning Angle | Proof Point Needed |
|----------|------------------------|-------------------|-------------------|
| **High-traffic site scaling past 5M req/month** | Vercel (per-invocation model) | Bandwidth pricing predictability; 50-60% cost savings at scale | Real customer TCO comparison (e.g., ZephyrMedia: $6K→$22K Vercel vs. Acme fixed bandwidth) |
| **Healthcare/fintech compliance procurement** | AWS Amplify | 24-hour BAA turnaround + contractual SLA + explicit pen-test policy | Case study: Meridian 2-week approval vs. Amplify 6-week generic BAA process |
| **Operations/SRE team reducing production risk** | AWS Amplify | Atomic rollback (30 sec vs. 25-min Amplify re-deploy); error budget impact quantified | Incident recovery simulation: RTO 30 sec vs. 25 min; cost of 25-min outage (revenue/SLA impact) |
| **Developer team productivity (staging contention)** | Heroku or custom staging | Deploy Previews per PR; isolated environments; concurrent work unblocked | Brightwave use case: 8 engineers, 1 staging env → each engineer isolated preview (8x parallel velocity) |
| **Edge compute + personalization (checkout, A/B testing)** | Cloudflare Workers | Higher CPU/memory limits; sub-10ms cold starts; checkout personalization without rewrite | StrataCommerce trial data: 12% conversion lift from edge-personalized checkout; Cloudflare Workers forced server-side rewrite |
| **Observability/monitoring at platform scale** | AWS Amplify + custom webhooks | Native Datadog integration; log drains; no custom webhook fragility | Ironbridge case: custom webhooks fragile; Acme native integration "cleaner than what we've built" |

---

## Messaging That Moved Deals Forward

*Specific framings, narratives, and proof points that worked in Q1 — use these as content templates*

### The TCO Reframe: Engineer Time > Infrastructure Cost
From Meridian (Rachel, VP Eng) and ZephyrMedia (Cassandra, VP Eng), per-invocation pricing or "cheap at small scale" platforms create hidden TCO burden.

**The framing:** "Your Amplify bill looks cheap at $500/month, but 0.5 FTE of your engineering team is babysitting builds, staging cycles, and observability integrations. That's $150K+/year in opportunity cost. Acme's faster builds and atomic rollbacks save that FTE, flipping the math to net-negative cost."

**Proof point:** Meridian CFO approved when Rachel showed $150K build-cycle burden on Amplify vs. Acme operational ROI (built from prospect's own metrics: 30+ min staging, 5 engineers affected, hourly rate).

**Use:** In any enterprise sales motion with multi-year platform decisions. Quantify prospect's engineering time spent on deploy/rollback/staging overhead. Show Acme's operational improvements (build caching, atomic rollback, Deploy Previews) as FTE savings, not feature comparison.

---

### The Stability Narrative: Velocity = Risk Reduction
From PolarAnalytics (Theo, FE Lead) and Ironbridge (Dmitri, Dir Eng), post-incident risk aversion is a blocker. Reframe Acme from "capability addition" to "risk reduction."

**The framing:** "Atomic rollback isn't a nice-to-have. It's incident response insurance. When something breaks, you recover in 30 seconds instead of 25 minutes. That preservation of your error budget, your customer trust, and your SLA compliance is why this decision matters."

**Proof point:** Ironbridge's Dmitri moved from skeptic to conviction when shown 25-minute rollback window erodes error budget math. Quantified: "You budget 5 incidents/quarter at 30-min each = 2.5 hours downtime. Non-atomic rollbacks double that to 5 hours, violating your 99.95% SLA."

**Use:** In any post-incident account or risk-averse CTO environment. Lead with operational resilience, not feature innovation. Quantify error-budget impact and SLA preservation. This narrative addresses champion hesitation (political risk) by positioning decision as data-driven, not opinionated.

---

### The "Complementary, Not Competing" Architecture
From StrataCommerce (Wei Zhang, CTO), ecosystem consolidation fear is real. Reframe Acme from replacement to layering.

**The framing:** "You've invested in Cloudflare's network (DNS, DDoS, CDN). Acme sits as your origin behind Cloudflare's network. You keep their infrastructure advantage and add Acme's hosting, Deploy Previews, and edge functions. This is additive, not rip-and-replace."

**Proof point:** StrataCommerce's Wei initially feared fragmentation. When Priya showed architecture (Acme as origin, Cloudflare as CDN layer), he said "That changes the conversation; we can layer this instead of replace." He then approved based on Alicia's business case.

**Use:** When Cloudflare Pages, AWS ecosystem, or infrastructure consolidation concerns surface. Create an architecture diagram showing Acme at the origin layer. Position layering as cost-neutral consolidation (same vendor count) with operational benefit (Acme's Deploy Previews, observability integration, atomic rollbacks).

---

### The Build Time Reality Check: Monorepo Math
From CascadeHealth, Ironbridge, Meridian, TechFlow—build time compounds at scale. Create benchmark reality.

**The framing:** "Full-stack rebuild on every deploy is the Amplify default. That's 25-40 minutes for a 200-file monorepo. Incremental caching + dependency analysis (Acme) rebuilds only what changed. 80-85% of commits skip rebuild entirely. That's 30-40x faster for most PRs."

**Proof point:** Marcus at CascadeHealth explained "Amplify rebuilds full codebase; Acme uses incremental caching." Specificity (200-file monorepo, 80-85% cache hit rate) makes this repeatable. Monetize: 35 engineers × 10 commits/day × 20 min saved per commit = 116 FTE-hours/week.

**Use:** In any platform evaluation with >10 engineers. Create a "build time benchmark" report comparing Vercel, Amplify, Cloudflare on monorepos of 200+ files. Include cache hit rates and engineering time ROI. This content is shareable with engineering teams pre-sales.

---

### The Compliance Responsiveness Advantage
From CascadeHealth and Meridian, healthcare/fintech buyers expect agility from vendors. Amplify's bureaucratic BAA process is the blocker.

**The framing:** "Your CISO needs SOC 2, BAA, and pen-test policy documentation. AWS Amplify will give you their generic AWS BAA (6-week turnaround) because you're not their primary customer. Acme gives you Amplify-specific BAA documentation within 24 hours, plus a named CSM who answers your security architect's technical questions in writing."

**Proof point:** CascadeHealth's Leo said "Acme's BAA is better than Amplify's." Meridian's Rachel said "Could show my CISO a contract that said here's what happens when something goes wrong." Marcus's 24-hour written answers shifted Meridian's entire approval path.

**Use:** In healthcare, fintech, and regulated verticals. Position "enterprise support responsiveness" as distinct advantage. Provide pre-templated BAA, SOC 2 responses, and pen-test policy as standard collateral (not "upon request"). Lead with contractual SLA clarity (named CSM, response-time guarantee, escalation path).

---

## Content Gap Priorities

*What prospects wanted to see that we couldn't provide — prioritized by deal frequency*

1. **Build time benchmark report (comparative, multi-platform)** — Heard in 4 calls (CascadeHealth, Ironbridge, Meridian, TechFlow); engineering teams want hard data on Amplify/Vercel/Cloudflare build caching. **Why it matters:** Monorepo build time is visceral; prospect wants to measure (not trust vendor claims). Create benchmark across 3+ monorepo sizes (50-file, 200-file, 500-file) with cache hit rates, incremental rebuild speeds, and engineering time ROI.

2. **TCO calculator (infrastructure cost + engineering time)** — Heard in 3 calls (ZephyrMedia, Meridian, TechFlow); economic buyers need math before committing. **Why it matters:** "Cheap" platforms create hidden maintenance costs. Create interactive calculator: prospect inputs team size, monthly requests, current platform, get projected FTE savings + 3-year cost comparison vs. Amplify/Vercel/Cloudflare.

3. **Compliance responsiveness playbook (BAA, SOC 2, pen-test policy templates)** — Heard in 3 calls (CascadeHealth, Meridian, TechFlow); security/compliance leads want pre-written documentation, not "upon request" bureaucracy. **Why it matters:** Healthcare/fintech procurement speed is competitive advantage. Provide BAA template specific to hosting vendors, pre-filled SOC 2 questionnaire, explicit pen-test policy statement. Position as "24-hour turnaround" collateral.

4. **Atomic rollback operational ROI case study** — Heard in 3 calls (Ironbridge, Meridian, PolarAnalytics); incident recovery and error-budget impact are quantifiable but rarely modeled. **Why it matters:** Post-incident risk focus is universal at scale. Create case study: "25-minute rollback window vs. 30-second atomic. Cost of 25-minute outage: $X revenue loss + Y SLA penalty + Z customer churn. Acme ROI: 4 months."

5. **Framework-agnostic positioning content (Next.js alternatives)** — Heard in 2 calls (Brightwave, TechFlow); Vercel's "Next.js creator" narrative is sticky. **Why it matters:** Acme works equally well for Remix, Astro, SvelteKit, Nuxt. Create one-pager: "Vercel optimizes for Next.js; Acme optimizes for your framework choice. Your stack will change; your platform shouldn't force that decision again."

---

## Competitive Messaging to Counter

*What competitors are saying that's gaining traction with prospects*

| Competitor | Their Narrative | Why It Works | Our Counter |
|-----------|----------------|-------------|------------|
| **Vercel** | "We created Next.js; best-in-class DX for React/Next.js teams" | Framework ownership is sticky; developers trust creator; "polished DX" is credible reputation | Position as framework-agnostic: "Vercel optimizes for one framework; Acme lets your platform evolve with your stack choices. Also: Vercel's per-invocation pricing becomes unpredictable at scale (ZephyrMedia $6K→$22K example). Lead with TCO + build time benchmarks." |
| **AWS Amplify** | "We're AWS-native; SSO, Cognito, DynamoDB integration; enterprise support from AWS" | Procurement friction reduction (already on AWS contract); perceived safety of known vendor | Counter: "Amplify is generic AWS support applied to hosting. Your CISO needs SOC 2 + BAA turnaround in days, not weeks. Acme gives 24-hour compliance documentation response + named CSM. Also: Amplify's operational pain (25-40 min builds, non-atomic rollbacks, slow observability integration) scales with you. Acme's operational velocity is faster." |
| **Cloudflare Pages** | "One vendor for DNS, DDoS, CDN, and hosting; network consolidation reduces vendor friction" | Infrastructure teams love simplicity ("one throat to choke"); Cloudflare's global network is credible | Counter: "Cloudflare's edge function CPU limits (10ms free, 50ms paid) block personalization logic that Acme edge functions handle easily (StrataCommerce example: 12% checkout conversion lift). Also: architect as layering, not replacement. 'You keep Cloudflare's network advantage, add Acme's hosting, Deploy Previews, atomic rollbacks.' Architecture clarity removes ecosystem fear." |

---

## Verticals with Strongest Signal

*Where competitive patterns suggest concentrated opportunity*

| Vertical | Competitor Pain | Acme Angle | Evidence |
|---------|----------------|-----------|---------|
| **Healthcare Tech** | Amplify: slow compliance documentation, generic BAA; security procurement delays | "Enterprise support responsiveness + contractual SLA clarity." Lead with 24-hour BAA turnaround, named CSM, explicit pen-test policy. | Meridian (closed won) + CascadeHealth (active); both cite compliance speed advantage vs. Amplify's bureaucracy. Rachel (Meridian VP Eng): "Could show my CISO a contract that said here's what happens when something goes wrong." |
| **Fintech** | Amplify/Vercel: operational risk (slow rollbacks, build time variability); error-budget concern | "Atomic rollback operational ROI + risk-reduction framing." Lead with incident recovery speed, error-budget preservation, SLA protection. | Ironbridge (deal health 75/100, moving to proposal); Dmitri converted from skeptic when shown 25-min → 30-sec rollback impact. "25-minute rollback window erodes our error budget." |
| **High-Growth SaaS** | Vercel: per-invocation pricing unpredictability at traffic inflection (5M+ req/month) | "TCO model + bandwidth pricing predictability." Lead with cost calculator, traffic-scale benchmarks, 50-60% savings projection. | ZephyrMedia (active, Feb 15 hard deadline); Cassandra: $6K→$22K cost spike from 8x traffic. "The math breaks at scale; can't explain to CFO why costs spike with traffic." |
| **E-Commerce / Retail** | Cloudflare Workers: CPU limits block checkout personalization; custom server-side rewrites required | "Edge function capability + personalization revenue impact." Lead with trial design measuring conversion lift (A/B test edge vs. server-side). | StrataCommerce (closed won, Cloudflare displaced); Alicia's unprompted ROI spreadsheet: 12% conversion lift from edge personalization. "Cloudflare's limits forced us to rewrite; Acme let us keep it at the edge." |
| **Media / Publishing** | Vercel: per-invocation cost spike at scale; pricing unpredictability; ISR invalidation concerns | "Bandwidth + per-request cost predictability + Sanity integration for granular cache invalidation." | ZephyrMedia (active); 350M→2.4B requests/month inflection; Vercel's 10% discount insufficient; ISR stability a technical veto gate. Lead with Sanity integration + granular invalidation strategy. |

---

## Summary: Q1 2026 Marketing Strategy

**Competitive Position:**
- **Strongest:** Operational velocity (build caching, atomic rollbacks, Deploy Previews) + compliance responsiveness (healthcare/fintech) + TCO models that include engineering time.
- **Vulnerable:** DX perception vs. Vercel (unstated preference, not tested in trials) + framework-specific optimization reputation + ecosystem consolidation appeal (Cloudflare).

**Top Marketing Investments (next 90 days):**

1. **Build time benchmark report** (multi-vendor, monorepo-focused, engineering time ROI) — Sharable with prospects pre-sales; addresses 4+ Q1 calls' request for hard data.

2. **TCO calculator** (infrastructure + FTE) — Interactive tool for economic buyers; flips "cheap platform" narrative by quantifying hidden engineering burden.

3. **Compliance responsiveness collateral** (pre-templated BAA, SOC 2, pen-test policy) — Fast-track healthcare/fintech procurement; position as distinct advantage vs. Amplify bureaucracy.

4. **Atomic rollback operational ROI case study** — Quantified incident recovery + error-budget math; addresses post-incident risk aversion (universal at scale).

5. **Competitive trial design guide** (internal sales enablement) — Ensure comparative trials (vs. Vercel/Amplify/Cloudflare), not solo Acme trials. Prospect's DX preference should be tested, not assumed.

**Vertical Prioritization:**
1. Healthcare (compliance responsiveness) — 2 Q1 examples, fastest compliance speed advantage
2. Fintech (operational risk) — 1 Q1 example, atomic rollback ROI quantified
3. High-growth SaaS (TCO/pricing) — 2 Q1 examples, per-invocation pricing pain visceral at scale
4. E-commerce (edge personalization) — 1 Q1 example, conversion revenue impact measurable

