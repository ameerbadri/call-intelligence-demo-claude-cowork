# Ironbridge Financial — Champion Building (Cloudflare Pages Competitive)
**Date:** 2026-01-27
**Participants:** Sarah Chen (Acme AE), Marcus Webb (Acme SE), Dmitri Volkov (Director of Engineering, Ironbridge Financial), Yuki Tanaka (Frontend Lead, Ironbridge Financial), Samantha Cho (Head of Platform Engineering, Ironbridge Financial)
**Duration:** 44 minutes

*Note: This is a synthetic transcript created for demonstration purposes.*

---

## Full Transcript

**Sarah Chen (0:32):** Dmitri, Yuki, Samantha — thanks for having us back. Last time was just Yuki and me. Good to get more of the team together. Before we get into the demo today — Dmitri, Samantha, can you tell me how you're thinking about this from your respective angles? I want to make sure Marcus covers what matters to each of you.

**Dmitri Volkov (0:55):** Sure. I'm focused on a few things. One is cost — we're a fintech with tight margins on infrastructure. Two is risk — changing our deployment platform is not a trivial decision and I need to understand the failure modes. Three is vendor health — I don't want to bet on a platform that gets acquired or changes strategy in two years.

**Samantha Cho (1:28):** From a platform perspective, I care about the operational story — how do we manage this at scale, what's the monitoring and alerting look like, and how does it integrate with our existing observability stack. We use Datadog heavily.

**Sarah Chen (1:52):** Marcus, both good technical angles for you. Yuki, anything to add to what you've told me previously?

**Yuki Tanaka (2:05):** I want the team to actually see the deploy preview workflow. My team has been waiting for this demo since I told them about my trial experience.

**Marcus Webb (2:25):** Before I demo anything — Samantha, you mentioned Datadog. Tell me about your current observability setup. What are you monitoring on the deployment side?

**Samantha Cho (2:45):** We track deploy frequency, deploy duration, error rates post-deploy, and rollback rate. We have custom dashboards in Datadog and we alert on build failures and elevated error rates within 5 minutes of a deploy.

**Marcus Webb (3:10):** Does that monitoring hook into Amplify today, or is it custom instrumentation?

**Samantha Cho (3:25):** Custom instrumentation. Amplify doesn't have native Datadog integration that's worth anything, so we've built webhooks that fire into our monitoring pipeline. It's fragile.

**Marcus Webb (3:48):** Acme has a webhook system that's designed for exactly this — you can emit deploy events (start, success, failure, rollback) into any endpoint, including Datadog's event API. We can also use Acme's log drains to ship build and function logs directly to Datadog. So rather than custom webhooks, you'd have native integration. Happy to walk through that architecture.

**Samantha Cho (4:20):** Yes, show me that. The fact that it's designed rather than hacked together matters to me.

**Marcus Webb (4:38):** Let me do that in a moment. First — Dmitri, you raised vendor risk. That's a fair concern and I want to address it directly rather than pretending it doesn't exist. Acme is a private company — we don't have the public financial reporting that would let you do a traditional vendor health analysis. What I can tell you: we've been operating since 2014, we're well-capitalized, and we're not experiencing the kind of growth pressure that forces acquisition decisions. Beyond that, I'd point you to our open-source footprint — our CLI, our build plugins, and core libraries are open source. If Acme disappeared tomorrow, the toolchain is portable. How does Ironbridge typically assess vendor risk for a strategic platform dependency?

**Dmitri Volkov (5:40):** We look at financial backing, customer reference quality, contract terms around data portability and service continuity, and we've started asking vendors to detail their acquisition policy — specifically, what happens to existing contracts if there's a change of control.

**Marcus Webb (6:10):** Change of control clause in our enterprise contracts — yes, we include those. Your contract would specify service continuity obligations and data portability rights in the event of acquisition. Jordan, can you confirm that?

**Sarah Chen (6:28):** Yes. It's standard in our enterprise agreements. I'll make sure that clause is clearly flagged in the term sheet.

**Dmitri Volkov (6:45):** Good. The other thing — you said "well-capitalized." That's what everyone says. Can you give me anything more specific?

**Marcus Webb (7:02):** I can't share financial details but I can tell you we're not burning cash to maintain market share in a way that creates existential pressure. The business model — subscription SaaS with high retention — is fundamentally sound. Beyond that, I'd encourage you to speak with reference customers who've been on Acme for 3+ years and ask them about the platform stability they've experienced.

**Dmitri Volkov (7:38):** Fair answer. What's the alternative you'd recommend for a company like ours if Acme didn't exist?

**Marcus Webb (7:55):** For your profile — fintech, compliance-sensitive, wanting enterprise support — Vercel is the most comparable enterprise-grade alternative. Cloudflare Pages is growing but their enterprise motion is less mature.

**Yuki Tanaka (8:18):** Speaking of Cloudflare — our infrastructure team looked at Cloudflare Pages after I showed them my Acme trial. They're interested in it because we're already using Cloudflare for DNS and DDoS protection. The argument was "one throat to choke."

**Sarah Chen (8:40):** Good to know. Samantha, is that the infrastructure team's preference, or is it still open?

**Samantha Cho (9:00):** It's their suggestion, not a decision. I'm more skeptical — Cloudflare's Pages product is much less mature than their core network product. They're a network company adding a hosting layer, not a hosting company with a network. That's different in practice.

**Marcus Webb (9:28):** Samantha is right to make that distinction. Cloudflare Pages has excellent performance — their network is world-class. But the developer experience, build system sophistication, and enterprise workflow tooling is earlier-stage. For a team like Yuki's that cares about preview environments, review workflows, and CI/CD integration, Cloudflare Pages is further behind. For a pure static site with minimal deploy complexity, they're competitive on price and performance.

**Dmitri Volkov (10:05):** What's the cost difference between Acme and Cloudflare Pages for a company our size?

**Sarah Chen (10:22):** Cloudflare Pages has a very generous free tier. For enterprise features — SSO, audit logs, SLAs, support — you're looking at a commercial conversation with them, and the product's enterprise offering is less defined than ours. I'd need to understand your team size and usage to give you an honest comparison.

**Dmitri Volkov (10:52):** We have 14 frontend engineers and probably 8 sites between the main product and various internal tools.

**Sarah Chen (11:15):** For that scale with enterprise features, you'd be in our Business or Enterprise plan — Marcus, can we save the cost comparison for the proposal rather than guessing on the call?

**Marcus Webb (11:32):** Agreed. Let me pivot to the demo Yuki's team has been waiting for.

[Marcus shares screen]

**Marcus Webb (11:50):** This is a real Acme account — not a demo environment. I'm going to open a PR on this Next.js repo... the PR triggers a build automatically... and you can see the build log running in real time here. This particular app builds in about 4 minutes — I'll skip ahead in the log to show you the output...

**Yuki Tanaka (14:15):** The preview URL is already there? That fast?

**Marcus Webb (14:28):** Yes. The preview URL is live as soon as the build succeeds. You can share it immediately — no deploy step, no staging push. The URL is stable for the lifetime of the PR. If you push another commit to the same branch, the same URL updates with the new build. You never break a reviewer's tab.

**Yuki Tanaka (14:55):** This is exactly what I showed Dmitri in my trial. The same URL updating without breaking the reviewer — that's the key behavior that our staging environment can't do.

**Dmitri Volkov (15:18):** Show me the rollback story. What happens when a deploy goes wrong?

**Marcus Webb (15:35):** [navigates to deploy list] Every deploy is immutable and atomic. Here's the deploy history. If I wanted to roll back to any previous deploy — say this one from Tuesday — I click "Publish deploy" and within 30 seconds, that deploy is live. It's not a re-deploy — it's literally restoring the previously built artifact. No re-run of the build pipeline, no risk of a different build producing a different result.

**Dmitri Volkov (16:05):** 30 seconds. Our current rollback on Amplify takes 25 minutes because we have to re-run the build.

**Samantha Cho (16:22):** And during that 25 minutes you're running degraded or you've taken the site down.

**Marcus Webb (16:35):** That's the real cost of a non-atomic deploy system. 25-minute rollbacks mean your error budget erodes quickly on any bad deploy. With atomic deploys, your recovery window is effectively zero plus the 30-second switch.

**Samantha Cho (16:58):** The Datadog integration — can you show me the webhook setup?

**Marcus Webb (17:15):** [navigates to site settings] Here's the notification settings. You can configure webhooks for: deploy started, deploy succeeded, deploy failed, and rollback. Each fires a payload to your configured endpoint. For Datadog, you'd point it at their Events API. The payload includes deploy ID, branch, deploy time, and status. I'll send you the Datadog integration guide after this — it's a 15-minute setup.

**Samantha Cho (17:52):** And log drains?

**Marcus Webb (18:08):** [navigates to log drain settings] Here. You select the destination — Datadog is a native option — and log types: build logs, function logs, edge function logs. All ship to Datadog automatically. No custom webhooks, no Lambda that forwards logs.

**Samantha Cho (18:35):** That's cleaner than what we've built. I wouldn't be rebuilding the integration, I'd be deleting it.

**Sarah Chen (19:00):** Dmitri, Samantha — where does this sit in terms of priority for your team right now? I know Yuki has been driving this, but I want to understand if this has cross-team momentum.

**Dmitri Volkov (19:28):** Yuki has been persistent, and the demo today has moved my position. The rollback story in particular — that's a real operational risk we have today that I hadn't fully quantified. Samantha?

**Samantha Cho (19:52):** The observability integration is better than I expected. I was prepared to be skeptical. I'm less skeptical now.

**Sarah Chen (20:18):** Good. Dmitri, what would it take to move this from evaluation to decision?

**Dmitri Volkov (20:40):** Three things. One — a reference customer in fintech who's been on Acme for at least 2 years. Two — the change-of-control clause in writing before we see pricing. Three — a clear migration plan, because I'm not going to shut down our Amplify setup and switch overnight.

**Sarah Chen (21:10):** All three are achievable. I'll find you a fintech reference — I have two in mind I'll check with. The change-of-control clause goes in the initial term sheet. And Marcus, can we put together a phased migration plan?

**Marcus Webb (21:30):** Yes. For 14 engineers and 8 sites, I'd recommend starting with your lowest-risk site — probably an internal tool — and migrating it over one sprint. That gives the team Acme familiarity before touching any customer-facing sites. I'll document that plan.

**Dmitri Volkov (22:00):** That approach makes sense. Timeline — when can you have the reference, term sheet, and migration plan to me?

**Sarah Chen (22:20):** End of this week for the term sheet and migration plan. The reference customer — I'll have a name for you by Wednesday. Can we reconvene next week — say Thursday — to go through everything?

**Dmitri Volkov (22:45):** Thursday next week. Let's do it.
