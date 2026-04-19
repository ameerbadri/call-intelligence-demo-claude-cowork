# Sales Battlecard — Q1 2026

> **9 competitive calls analyzed** | Top competitors: Vercel (5 calls), AWS Amplify (5 calls), Cloudflare Pages (3 calls)
> Period: Jan 1 – Mar 31 2026 · 2 Closed Won · 4 Active/Strong · 2 At Risk · 2 Early Stage

---

## ⚡ Top 5 Actions
*What sales should do differently starting this week*

1. **Lead every growth-stage deal with a TCO model, not features** — Vercel's per-invocation pricing spike ($6K→$22K at ZephyrMedia on an 8x traffic bump) is the #1 conversion lever we have. Build the cost model in call 2, before trial. Every AE should have a 2-slide pricing comparison ready for any deal where the prospect is running >5M req/month or projecting 3x+ growth.

2. **Design competitive trials head-to-head, not solo Acme demos** — Brightwave is at risk because Priya's "polished DX" preference for Vercel was never tested against us. Structure every trial as "Acme vs. [incumbent] on build time and deploy cycle" — not "try Acme and see what you think." TechFlow's POC is the right model. Solo demos default to incumbent.

3. **Book the economic buyer before trial results exist** — In 4 of 10 Q1 deals (TechFlow, PolarAnalytics, GlobalRetail, DataStack), the EB was absent when trial was running. A champion presenting results to a CTO they didn't prep is a 50% close rate at best. Book a "business case preview" call with the VP Eng/CTO before you have results to share.

4. **For any Cloudflare deal: lead with architecture clarity on day one** — "Acme sits behind your Cloudflare CDN as origin — you keep your network investment" nearly saved StrataCommerce from falling over the ecosystem objection. Don't wait for Wei Zhang to raise it. Say it in discovery: "You don't have to choose between us and Cloudflare."

5. **When champion hesitation is the blocker, design a discretionary-budget pilot** — DataStack was stalled 6+ weeks because Owen wouldn't advocate without executive air cover. Jordan's solution: a $5K/mo pilot under EM-level authority, no CTO approval needed. Position the champion as a data-advocate gathering evidence, not a vendor pusher taking a risk. This template works wherever organizational change is the blocker.

---

## Competitor Profiles

### vs. Vercel

**Their pitch to our prospects:** "We created Next.js — you get the best possible Next.js experience on our platform." Vercel leads with framework ownership, developer experience brand equity, and per-team simplicity. They don't have to sell hard; brand reputation does the work at early stage.

**Our strengths in this matchup:**

- **Pricing model is our primary lever.** At scale (5M+ req/month), Vercel's per-invocation model creates unpredictable bills. ZephyrMedia: $6K → $22K on a single traffic spike. Vercel's response (10% discount) doesn't fix the structure. Acme's bandwidth model is predictable. Build the TCO model early — don't wait for the prospect to discover pain.
- **Framework-agnostic is an enterprise risk story.** Vercel created Next.js and can deprecate, change pricing, or lock in behavior. Acme doesn't own any framework — your stack evolves and so do we. This lands with VPs and CTOs, not individual devs.
- **Enterprise motion is more mature.** RBAC, audit logs, contractual SLA, enterprise support SLAs, named CSMs. Vercel's enterprise tier is newer. Ironbridge, CascadeHealth, and Meridian all surfaced compliance/SLA as requirements — areas where Acme has documented answers and Vercel doesn't.
- **Build caching for monorepos.** Marcus's framing at TechFlow: "80-85% of commits skip rebuild with Acme's incremental caching." For large, multi-repo codebases (TechFlow, Brightwave), Acme's build system is measurably faster.

**Their genuine advantages (be honest):**

- **Next.js native** — Vercel created it, ships features first, and has framework-specific optimizations no one else can replicate. Every Next.js shop feels this. Don't dismiss it.
- **DX brand equity** — "Polished DX" is how Priya Patel at Brightwave described them without ever trialing us. That's a moat built over years. We don't win on DX reputation; we win on DX evidence in a side-by-side trial.
- **Simpler commercial story at small scale** — Individual dev or small team? Vercel is fast, easy, and well-documented. We need a team-scale problem to win.

**Objections they seed and how to defuse:**

| Objection | Context | Response Framework |
|-----------|---------|-------------------|
| "Our team is all-in on Next.js — Vercel feels natural" | Brightwave, TechFlow | "Acme fully supports Next.js including SSR, ISR, and Edge Middleware. The question isn't which platform knows Next.js best — it's which one you want to be locked into as your stack evolves." |
| "Vercel offered us a discount" | ZephyrMedia | "A discount on a broken pricing model is still a broken pricing model. The math breaks at your next traffic spike — let me show you what that looks like at 3x your current volume." |
| "Vercel has better developer experience" | Brightwave (unstated) | Don't debate it. Say: "Let's test that head-to-head on your actual codebase — build time, preview cycle, rollback. If their DX wins on your stack, you should know that. If ours does, so should you." |
| "Vercel is the market leader for frontend hosting" | Multiple (implied) | "They lead in Next.js mindshare. We lead in enterprise deployment velocity, pricing predictability, and compliance documentation. For a team your size, which matters more in 12 months?" |

**Win pattern:** Against Vercel, we win in growth-stage accounts where traffic is scaling and per-invocation math is becoming a line item. The trigger is: prospect has recently had a bill surprise, is modeling growth, or is running financial forecasting on infrastructure costs. Lead with TCO. Get Raj Kumar / Cassandra Bell types (VP Eng + Staff Eng) in the same conversation. Don't pitch features — pitch predictability.

---

### vs. AWS Amplify

**Their pitch to our prospects:** "You're already in AWS. We're the native frontend hosting layer — no new vendor, no new contract, no migration." The pitch is convenience and consolidation within an AWS-committed organization.

**Our strengths in this matchup:**

- **Operational velocity is our primary lever.** Amplify's build times are catastrophically slow at scale: CascadeHealth at 28-35 min, Ironbridge at 25-min rollbacks, Meridian at 30+ min staging cycles. Acme: 5-8 min builds, 30-second atomic rollbacks, 5-min Deploy Preview cycles. These numbers are visceral and quantifiable. Lead with them.
- **Atomic rollbacks.** "25-minute rollback window erodes your error budget" — Dmitri Volkov at Ironbridge, skeptic turned advocate after Marcus showed the architecture. In fintech and healthcare, a bad deploy that takes 25 minutes to revert isn't a DX problem — it's an operational risk.
- **Compliance responsiveness.** CascadeHealth: Leo asked Amplify for BAA language specific to their deployment role. AWS sent them the generic AWS BAA. Marcus sent a pre-templated Amplify-specific BAA, pen test policy, and SOC 2 documentation in under 24 hours. In healthcare and fintech, support velocity on compliance requests is a deal factor, not a checkbox.
- **Native observability integrations.** Ironbridge built fragile custom webhooks to bridge Amplify and Datadog. Acme: native log drain, no custom logic. Samantha Cho: "Cleaner than what we've built; I'd be deleting it."
- **TCO model flips the cost story.** Amplify looks cheap. Add 0.5 FTE maintenance overhead (Meridian's exact number) + 30+ min staging cycles + build system toil = Acme is net negative cost. Rachel Kim and her CFO approved after this framing. Build this model from the prospect's own numbers.

**Their genuine advantages (be honest):**

- **AWS procurement already approved.** No legal review, no new vendor contract, no InfoSec questionnaire for a net-new vendor. In large enterprises with slow procurement, this is real friction we add.
- **AWS ecosystem integration.** Cognito, AppSync, DynamoDB, IAM — all native. For teams with heavy AWS backend dependencies, Amplify's integration story is simpler than ours.
- **Default safety for AWS-committed orgs.** CIOs and CTOs with AWS Enterprise Agreements don't want more vendors. This is an organizational inertia force, not a product argument.

**Objections they seed and how to defuse:**

| Objection | Context | Response Framework |
|-----------|---------|-------------------|
| "We're an AWS shop — adding another vendor is friction" | CascadeHealth, Ironbridge, Meridian | "Acme runs on AWS under the hood. It's not a competing cloud — it's the best interface for deploying your frontend on your existing AWS investment. Your backend, auth, and data stays in AWS." |
| "Amplify is cheaper — we're already paying for AWS" | Meridian (CFO initial position) | "Let's build the TCO together: Amplify maintenance overhead, build time cost in eng hours, staging cycle overhead. Meridian found it was 0.5 FTE + 30 min/cycle. What's your number?" |
| "Our CISO needs to review any new vendor" | CascadeHealth, Meridian | Provide: pre-templated BAA, SOC 2 Type II, pen test policy in writing, 24-hr turnaround on follow-up questions. Speed and specificity are the differentiator, not the documents themselves. |
| "Why migrate when what we have works?" | (Implied) | "Let's run a side-by-side build benchmark on your codebase. You tell us how many minutes you lose per day. Then we tell you what your team could do with them back." |

**Win pattern:** Amplify displacement wins on operational pain quantification + compliance responsiveness. The sequence: (1) Get a build time benchmark in the first technical call. (2) Show atomic rollback architecture — especially to ops/platform personas (Samantha Cho archetype). (3) In compliance-heavy verticals, own the documentation review lane — fast, specific, contractual. (4) Build TCO with the champion before the CFO conversation.

---

### vs. Cloudflare Pages

**Their pitch to our prospects:** "One throat to choke — your DNS, DDoS protection, CDN, and hosting in a single vendor. Plus our free tier is very generous." The pitch is network consolidation and cost, especially in infrastructure-centric organizations.

**Our strengths in this matchup:**

- **Edge function runtime limits are a concrete product gap.** StrataCommerce: Cloudflare Workers imposed 10ms (free) / 50ms (paid) CPU limits that blocked checkout personalization logic. They had to move logic server-side — creating complexity and latency. Acme's Edge Functions have higher CPU/memory allowances and a cleaner runtime model. This is a product limitation that cost Alicia Nguyen a feature she wanted at the edge.
- **Ecosystem objection has a clean reframe.** Wei Zhang's concern: "We've invested in Cloudflare — switching means losing our network." Priya's answer: "Acme as origin behind Cloudflare's CDN is architecturally sound. You keep your DNS, DDoS, and CDN. You just swap the origin hosting layer." Wei: "That changes the conversation." Use this proactively, not defensively.
- **DX maturity and enterprise feature completeness.** Marcus's framing at Ironbridge: "Network company adding hosting vs. hosting company with network." Acme has Deploy Previews maturity, dedicated enterprise support, contractual SLAs — none of which Cloudflare Pages has at equivalent depth.
- **Trial-validated revenue impact.** StrataCommerce won on a 12% checkout conversion lift in a 2-week trial on 20% of production traffic. Real revenue metrics beat benchmark comparisons with economic buyers every time.

**Their genuine advantages (be honest):**

- **Consolidation narrative is powerful in infrastructure-centric orgs.** Ironbridge's infrastructure team: "one throat to choke." This resonates for platform engineers who manage sprawl. We don't have a single-vendor pitch.
- **Generous free tier and bandwidth-included pricing.** For small/startup-scale workloads, Cloudflare is genuinely cheaper. Don't fight this at that scale — we don't win.
- **Global network + edge compute in one vendor.** Teams already using Cloudflare Workers have natural pull toward Pages. The stickiness is real.

**Objections they seed and how to defuse:**

| Objection | Context | Response Framework |
|-----------|---------|-------------------|
| "We've invested in Cloudflare's ecosystem — switching means fragmentation" | StrataCommerce | "You don't have to choose. Acme as origin behind Cloudflare's CDN is architecturally sound — you keep your network investment, swap the hosting layer. Layer, don't replace." |
| "Cloudflare Pages is free for us right now" | (Implied at Ironbridge) | "Free is right for side projects. At team scale — multiple contributors, preview environments, enterprise auth, compliance SLAs — the economics shift. What's the cost of one deploy outage or compliance gap?" |
| "We want one throat to choke / fewer vendors" | Ironbridge | "Consolidation makes sense for infrastructure. For developer tooling, you want best-of-breed: Cloudflare's network is excellent; their hosting DX and enterprise support aren't their core product. Acme is." |
| "Cloudflare Workers already handles our edge compute" | StrataCommerce (before trial) | "It handles most cases well. The question is whether CPU/memory limits on complex logic (personalization, checkout, A/B) become a ceiling. Let's trial one of those specific flows." |

**Win pattern:** Cloudflare displacement requires a concrete product limitation, not a feature comparison. The StrataCommerce model: identify a specific edge use case that hits Workers CPU/memory limits → design a 2-week trial that measures real business impact (conversion rate, not benchmarks) → resolve ecosystem separation concern on day 1. The architecture reframe ("complementary not competitive") must come in discovery, not after the objection.

---

## Training Scenarios

*Realistic prospect challenges with suggested responses — based on actual language from Q1 calls*

**Scenario 1: The Vercel Loyalist (Brightwave / TechFlow archetype)**

> *"Our whole team uses Next.js. Vercel created it — they're the obvious choice for us."*

**What not to say:** "Acme supports Next.js too." (True, but doesn't move the conversation.)

**What works:** "I hear you — Vercel's Next.js story is genuinely strong, and if you're a small team shipping a single Next.js app, they're excellent. What we're hearing from teams your size is that the platform choice looks different when you factor in pricing at scale, compliance requirements, and a stack that might evolve beyond Next.js. Would it be worth running a side-by-side build time comparison on your actual codebase — not a demo, your repo — before you make that call?"

**Leave-behind:** Build time benchmark proposal. "If Vercel is faster on your stack, you should know that. If we are, so should you."

---

**Scenario 2: The Amplify Incumbent (CascadeHealth / Meridian archetype)**

> *"We're deep in AWS. Swapping Amplify out means another vendor, another contract, another security review."*

**What not to say:** "We're really easy to migrate." (Minimizes their concern.)

**What works:** "That friction is real and I don't want to pretend it isn't. Here's the flip side: Acme runs on AWS under the hood — it's not a new cloud, it's a better interface for deploying your frontend on your existing AWS investment. I can send you our BAA, SOC 2, and pen test policy today — most security reviews close within two weeks. And we can start with a single low-risk site in one sprint to validate before any larger migration."

**Leave-behind:** Compliance documentation packet + phased migration plan.

---

**Scenario 3: The Stalled Champion (DataStack / PolarAnalytics archetype)**

> *"I'd love to move this forward, but my CTO is risk-averse right now and I don't want to be the person pushing something new."*

**What not to say:** "Let's get your CTO on a call." (Creates the political risk they're trying to avoid.)

**What works:** "That makes sense — I wouldn't want you in that position either. Here's a path that doesn't require executive approval: we run a 2-week pilot under your existing engineering budget. Pick your highest-pain use case, we instrument it, you gather the data. You're not pushing a new tool — you're running an experiment. If the data doesn't support it, we close it down. If it does, you have evidence to present, not an opinion."

**Leave-behind:** Pilot scope document. Budget under EM discretionary authority (~$5K/mo). No CTO approval path.

---

**Scenario 4: The Cloudflare Consolidator (Ironbridge archetype)**

> *"We want fewer vendors, not more. We already use Cloudflare for DNS and DDoS — adding Acme is going the wrong direction."*

**What not to say:** "But we're better at hosting." (Misses the consolidation concern.)

**What works:** "The consolidation instinct is right — and it doesn't require choosing between us and Cloudflare. Architecturally, Acme works cleanly as your origin server behind Cloudflare's CDN. You keep your DNS, DDoS protection, and network investment intact. You're not replacing Cloudflare — you're using a better tool for the hosting layer. [Show architecture diagram.] Teams that have done this found it cleaner, not messier."

**Leave-behind:** Architecture diagram showing Acme-as-origin behind Cloudflare CDN. Reference the StrataCommerce displacement pattern.

---

**Scenario 5: The CFO Blocker (Meridian / GlobalRetail archetype)**

> *"The VP Eng is on board, but our CFO isn't convinced the economics justify a migration."*

**What not to say:** "We're competitively priced." (Not what CFOs care about.)

**What works:** "Let's build the ROI model using your own numbers. What's your current staging cycle time per PR? How many engineers are in the review loop? What's your rough burdened engineer cost? At Meridian the math showed 0.5 FTE in Amplify maintenance overhead alone — that flipped the CFO conversation from 'expensive alternative' to 'net negative cost.' Can we put 20 minutes on the calendar with you and your VP Eng to walk through your version of that model?"

**Leave-behind:** TCO model template with engineer-hour inputs. Pre-fill with industry benchmarks; let prospect validate.

---

## Win/Loss Summary

| Competitor | Q1 Wins | Q1 Active | Q1 At Risk | Key Differentiator |
|------------|---------|-----------|------------|-------------------|
| **AWS Amplify** | 2 (Meridian, Ironbridge¹) | 2 (CascadeHealth, TechFlow) | 1 (PolarAnalytics) | Atomic rollback (30s vs 25 min), build caching (5-8 min vs 28-35 min), compliance documentation speed |
| **Vercel** | 0 | 3 (ZephyrMedia, Brightwave, TechFlow) | 0 | Pricing predictability at scale; framework-agnostic risk story |
| **Cloudflare Pages** | 1 (StrataCommerce) | 1 (Ironbridge) | 1 (PolarAnalytics) | Edge function runtime limits, enterprise DX maturity, "complementary not competitive" architecture reframe |

*¹Ironbridge not closed won yet — 75/100 deal health, moving to proposal*

**Top 3 deal risk patterns this quarter:**

1. **Economic buyer absent in late-stage deals** — TechFlow, PolarAnalytics, DataStack all have EB gap. This is the #1 deal-loss risk in Q2.
2. **Champion political hesitation blocking progression** — PolarAnalytics and DataStack (pre-pilot) stalled because champions wouldn't advocate without air cover. Pilot model is the fix.
3. **Competitive trial design gap** — Brightwave running a solo Acme trial with no head-to-head comparison. Risk: "Vercel is familiar" wins by default.

**Q2 must-win matchups:**
- **ZephyrMedia** (Vercel displacement, TCO model validation) — hard close window driven by traffic cost pain
- **TechFlow** (Vercel finalist, POC result + CTO engagement both critical before Mar 26 working group)
- **CascadeHealth** (Amplify displacement, compliance-led close) — Jan 31 deadline passed; urgency reset needed
- **Ironbridge** (Amplify + Cloudflare, multi-threaded conviction, fintech reference is the final gate)
