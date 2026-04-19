# GlobalRetail — Multi-Stakeholder / Champion Building
**Date:** 2026-03-18
**Participants:** Sarah Chen (Acme AE), Marcus Webb (Acme SE), Nadia Okonkwo (VP Engineering, GlobalRetail), Tom Herrera (Frontend Platform Lead, GlobalRetail), Christine Moss (Procurement Manager, GlobalRetail)
**Duration:** 48 minutes

*Note: This is a synthetic transcript created for demonstration purposes.*

---

## Full Transcript

**Sarah Chen (0:30):** Thanks everyone for joining. I see we have a few folks here — Nadia and Tom I know, but Christine, I don't think we've met. Can you tell me a bit about your role in this?

**Christine Moss (0:48):** Hi Sarah. I'm the Procurement Manager for GlobalRetail. Tom looped me in — any new vendor relationships go through my team before they get finalized. I just want to make sure I understand what we're looking at.

**Sarah Chen (1:05):** Absolutely, Christine. Happy to have you here. I'll make sure you have everything you need. Should we start with a quick recap for Christine's benefit, and then we can go into the technical detail Tom wanted to cover today?

**Nadia Okonkwo (1:22):** That makes sense. Christine, the short version: we're evaluating Acme as a replacement for our current frontend deployment setup. Tom has been leading the technical evaluation — he's probably the right person to summarize where we are.

**Tom Herrera (1:45):** Sure. So our current setup is a mix — we have some things on AWS CloudFront with custom build tooling, some legacy stuff still on a VM-based setup. It's been held together with scripts for a long time. We have 24 frontend engineers across three product squads, and the deployment experience is inconsistent. Some squads have it more figured out than others. We started talking to Acme because Tom on my team — different Tom, confusingly — did a proof of concept on a side project and it was dramatically simpler.

**Sarah Chen (2:38):** Tom, that matches what you told me in our earlier calls. You got the POC live in a couple of hours, right?

**Tom Herrera (2:48):** Less than that. That's what kicked off this whole evaluation. I showed Nadia and she said "why doesn't our main product work that way."

**Nadia Okonkwo (3:05):** Right. And my concern is scale — the POC was a simple marketing page. Our main product is much more complex. That's what I want to make sure works before we commit to anything.

**Marcus Webb (3:25):** That's a fair concern. Can you tell me more about the main product architecture — what are we actually talking about in terms of complexity?

**Nadia Okonkwo (3:42):** We run a retail commerce platform. Multiple brands under one parent company — four distinct storefronts, each with their own design language but sharing a common component library. Roughly 300 routes across the largest storefront. We use Next.js for the main storefronts and have a separate headless CMS — Contentful — that powers most of the product content.

**Marcus Webb (4:15):** Multi-brand, shared component library, Contentful-driven content — this is a common pattern for retail. Can you tell me how content changes propagate today? When a content editor updates something in Contentful, how does that get to production?

**Tom Herrera (4:38):** Manually, right now. Editor updates in Contentful, they submit a request to the frontend team, we kick off a rebuild manually. Depending on queue depth, that can take anywhere from 30 minutes to two days.

**Marcus Webb (5:05):** Two days for a content change to go live is significant for retail. Is that a pain point the content team has raised?

**Nadia Okonkwo (5:20):** Raised is an understatement. The head of merchandising is one of the loudest voices for this change. We've had content errors stay live for over a day because we couldn't get a rebuild prioritized.

**Marcus Webb (5:45):** With Acme Connect, content changes in Contentful can trigger an automatic partial rebuild of only the pages that depend on that content. So a product description update would rebuild and invalidate cache for that product's pages — not the entire site. For your scale, that typically means a content change is live within 3-5 minutes, automatically.

**Nadia Okonkwo (6:18):** That would solve a major internal headache. How does Acme Connect handle multiple brands — do they each need their own site?

**Marcus Webb (6:38):** You have two options. You can run four separate Acme sites — one per brand — which gives you full isolation and independent deploy pipelines per brand. Or you can use a monorepo configuration with shared components and run them as separate builds from the same codebase. Most multi-brand retail setups we work with prefer the four-site model because it gives squads autonomy without coordination overhead.

**Tom Herrera (7:08):** That matches my instinct. The squads operating independently is actually important for us culturally — we've tried shared deployment pipelines before and it creates coordination problems.

**Marcus Webb (7:30):** One more thing on the content propagation — for a retail environment, you'll want to think about cache invalidation strategy for high-traffic pages like PDPs and PLPs. We can set up granular cache invalidation so a price or inventory change on one product doesn't bust the cache for your entire catalog. Happy to go deeper on that architecture if it's relevant.

**Tom Herrera (7:50):** Yes, that's very relevant. We've had caching problems before — too aggressive and content goes stale, too conservative and performance suffers.

**Sarah Chen (8:15):** Tom, I know you had a list of specific technical questions going into today — should we make sure we get through those?

**Tom Herrera (8:28):** Right, yes. A few things: edge rendering for personalization, handling for high-traffic peaks like seasonal sales, and — from David on my team who couldn't join today — questions about the build pipeline security.

**Marcus Webb (8:52):** Let me take those in order. Edge rendering for personalization — what kind of personalization are you doing? Is it segment-based, individual, something else?

**Tom Herrera (9:10):** Segment-based right now. We have about 8 customer segments based on purchase history and geo. Loyalty customers see different promotions than new visitors.

**Marcus Webb (9:30):** That's a good fit for Edge Functions. The pattern would be: read the segment cookie at the edge, serve the appropriate content variant, no round-trip to origin. The key is keeping the segment logic at the edge rather than doing it server-side — which means your server doesn't have to scale for personalization lookups on every request. What's your current approach?

**Tom Herrera (9:58):** We're doing it server-side via our Next.js middleware right now. It works but it adds latency and our server has to handle the load.

**Marcus Webb (10:15):** Moving that to the edge would reduce latency and take load off your server. For 8 segments, the edge function logic is simple. Do you use any CDP or customer data platform for segment resolution?

**Tom Herrera (10:35):** We use Segment.io. The segment data is in a cookie set by our client-side Segment integration.

**Marcus Webb (10:50):** Perfect. The edge function reads that cookie and routes accordingly. Straightforward. High-traffic peaks — Black Friday equivalent, seasonal launches?

**Tom Herrera (11:08):** Yes. We have a major sales event in Q4 — our traffic goes from roughly 500K daily uniques to 3-4 million on peak days. We've had the servers fall over before.

**Marcus Webb (11:32):** Acme's CDN is purpose-built for this. Static assets and edge-rendered pages don't hit your origin at all on cache hits — you can absorb most of that traffic spike at the edge. The origin pressure is reduced to cache misses and personalized requests. We have customers with similar peak profiles — I can get you case study data from a retail customer if that would help with Nadia's internal business case.

**Nadia Okonkwo (12:05):** That would actually be very useful. Our infrastructure team is skeptical that any single-vendor platform can handle our peak load. Seeing a real customer example with comparable traffic would help that conversation.

**Marcus Webb (12:28):** I'll follow up with that. On build pipeline security — what specific questions did your team have?

**Tom Herrera (12:45):** David wanted to know about secrets management in the build pipeline. We have API keys for third-party services that can't be exposed — how does Acme handle those?

**Marcus Webb (13:05):** Environment variables are encrypted at rest and injected at build time. They're never exposed in the build logs. You can scope them to specific deploy contexts — so your production API keys only inject in production deploys, not in branch deploys. For really sensitive values, you can also integrate with AWS Secrets Manager or HashiCorp Vault for runtime secret retrieval rather than build-time injection.

**Christine Moss (13:40):** Can I jump in here? I want to make sure I understand the commercial side. Sarah, what kind of contract are we talking about — is this a monthly subscription, an annual contract?

**Sarah Chen (14:02):** Great question, Christine. For GlobalRetail's scale — four storefronts, 24 engineers, your traffic volume — we'd be looking at an enterprise agreement. That means an annual contract, invoiced quarterly, with terms around SLAs, support, and security. We'd customize it based on your specific requirements. I don't have final pricing in front of me today because I want to make sure we're scoping it correctly first. Can I ask — what's your typical procurement cycle for a vendor agreement at this size? Just so I understand the timeline.

**Christine Moss (14:45):** For a new vendor under $100K annually, I can usually turn around a review in two to three weeks once I have a contract draft. If it's over $100K it goes to legal, which adds another two to three weeks.

**Sarah Chen (15:10):** That's helpful. What budget tier are you expecting this to fall in, Nadia — do you have a sense?

**Nadia Okonkwo (15:28):** I honestly don't know yet. I don't have visibility into what your enterprise pricing looks like at our scale. That's something I'd need before I can have a budget conversation with our CFO.

**Sarah Chen (15:50):** Understood. I'll prepare a detailed pricing proposal based on today's scope — four sites, your traffic volume, enterprise features — and get it to you by Friday. That gives you the numbers you need for internal conversations. Christine, does that work for your review timeline?

**Christine Moss (16:10):** Yes, as long as I have a draft contract or at least a term sheet, I can start my review in parallel with the technical evaluation.

**Sarah Chen (16:28):** I'll include a term sheet in the proposal. One question for me: Christine, is there an approved vendor list I need to be aware of, or any specific certifications GlobalRetail requires from vendors at this tier?

**Christine Moss (16:50):** We require SOC 2 Type II or equivalent, and we'd want to run a vendor risk questionnaire. Also, for any platform handling our deployment pipeline, our security team will want to review.

**Sarah Chen (17:12):** SOC 2 Type II — covered. The vendor risk questionnaire — I can have Marcus pull up our pre-filled questionnaire right now or send it today. Security team review — we'd welcome that, Marcus is the right point of contact.

**Marcus Webb (17:32):** Happy to do a dedicated security architecture session with David and whoever else from GlobalRetail's security team needs to be there.

**Nadia Okonkwo (18:00):** I'll make sure David is included going forward.

**Tom Herrera (18:15):** Can I ask about the migration itself? I'm a little worried about the practical side — we have 24 engineers who all have their own way of doing things today. Changing the deployment platform means changing how every single one of them works. That change management problem scares me more than the technical problem.

**Marcus Webb (18:48):** That's the right thing to be worried about, honestly. The technical migration is usually the easier part. For a team your size, we'd recommend a phased approach — start with one squad and one storefront, build familiarity and create internal champions, then expand. We have a structured onboarding process for enterprise customers that includes engineering team enablement — documentation, a workshop session, and a period where our technical team is available for questions. It's not a throw-the-docs-over-the-wall approach.

**Nadia Okonkwo (19:32):** How long does that typically take for a team this size?

**Marcus Webb (19:48):** For four storefronts with proper phasing — first storefront live in 4-6 weeks, full migration in 10-12 weeks. That's with active engineering capacity on your side. If your team is constrained, it takes longer.

**Sarah Chen (20:12):** I want to make sure we leave enough time for next steps. Tom, where does this sit in terms of priority on your end — is this something that has executive urgency, or are we on a more exploratory timeline?

**Tom Herrera (20:35):** It has urgency for me — the current setup is a drag on my team's velocity every day. The question is how it registers with Nadia. Nadia?

**Nadia Okonkwo (20:52):** My honest answer is that it's important but I have three other infrastructure initiatives competing for the same engineering capacity. I need to see a clear ROI case — not just faster deploys, but what that translates to in actual business value — before I can prioritize it over the other things.

**Sarah Chen (21:22):** That's fair. Can I get clarity on what the ROI case needs to show? Is it engineering time saved, content velocity, incident reduction, something else?

**Nadia Okonkwo (21:40):** All of the above, but quantified. I can't take "faster deploys are better" to our CFO. I need to be able to say "we project X hours saved annually, which at our fully-loaded engineering cost is $Y, and the content publishing velocity improvement translates to Z fewer escalations from merchandising per month."

**Sarah Chen (22:08):** Understood. I'll build that into the proposal — a quantified ROI model based on the specifics you've shared today. I'll need one input from you: what's your approximate fully-loaded cost per engineering hour? I can use an industry average if you'd rather not share internal numbers.

**Nadia Okonkwo (22:35):** Use $150 as a blended rate. That's close enough.

**Sarah Chen (22:48):** Perfect. I'll work with Marcus on the model. Anything else before we close?

**Christine Moss (23:00):** Can you send me the SOC 2 report directly? I'll need it for our vendor file regardless of how the evaluation goes.

**Sarah Chen (23:18):** I'll include it in my follow-up today — just needs a quick NDA signature, which I'll attach.

**Tom Herrera (23:30):** And Marcus, the Contentful Connect deep dive we talked about — can we do that in a separate session? I want to get deeper into the caching and invalidation specifics.

**Marcus Webb (23:45):** Absolutely. Let's book that for next week. I'll include a specific agenda around cache architecture for high-traffic retail. What day works?

**Tom Herrera (23:58):** Wednesday next week, afternoon Pacific.

**Marcus Webb (24:10):** I'll send an invite. Let's say 2pm.

**Sarah Chen (24:22):** Great. So to recap: I'll send the proposal with pricing, term sheet, ROI model, and SOC 2 report by Friday. Marcus and Tom have a deep dive on the Contentful architecture Wednesday. And I'd like to schedule a call with you and Nadia the following week to walk through the proposal together — does that work?

**Nadia Okonkwo (24:50):** That works. Copy me on the proposal when you send it so I can review it before that call.

**Sarah Chen (25:05):** Will do. Thank you all — Christine, it was great to meet you, and Tom, as always, good to see you.
