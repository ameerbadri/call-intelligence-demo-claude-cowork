# Strata Commerce — Won Deal (Cloudflare Pages Displacement)
**Date:** 2026-02-20
**Participants:** Sarah Chen (Acme AE), Priya Nair (Acme SE), Wei Zhang (CTO, Strata Commerce), Alicia Nguyen (Senior Frontend Engineer, Strata Commerce)
**Duration:** 30 minutes

*Note: This is a synthetic transcript created for demonstration purposes.*

---

## Full Transcript

**Sarah Chen (0:28):** Wei, Alicia — congratulations again on signing. We're really excited to have you on Acme. I wanted to do a quick debrief today — partly for our own learning, and partly because I want to make sure Alex, your CSM, has full context when he takes over. Is that okay?

**Wei Zhang (0:50):** Happy to. I've done enough vendor evaluations to appreciate when a company actually wants to understand what worked.

**Sarah Chen (1:08):** Let's start with the beginning — you were on Cloudflare Pages when we first talked. Walk me through what was wrong.

**Wei Zhang (1:28):** Cloudflare Pages worked fine for a long time. We're an e-commerce platform — we started small, grew fast. When we were a simple static site with a few functions, Cloudflare's performance was excellent and the price was hard to argue with. The problems started when we started building more complex user experiences — personalization, dynamic pricing, A/B testing on the checkout flow.

**Alicia Nguyen (2:02):** Cloudflare Workers and Pages have a more limited runtime compared to Acme Functions for the patterns we needed. We were doing a lot of workarounds to get logic to run at the edge correctly. And their DX for local development — testing workers locally is painful compared to Acme's dev server.

**Sarah Chen (2:35):** Alicia, what was the specific moment you started looking at alternatives?

**Alicia Nguyen (2:52):** I built a checkout personalization feature — different UI elements based on the customer's purchase history. On Cloudflare Workers, I had to work around memory and CPU limits in a way that felt wrong. I rewrote it as a Acme Edge Function and it was half the code and twice as fast. That was when I brought it to Wei.

**Wei Zhang (3:28):** Alicia showed me the comparison and I agreed it made sense to evaluate. My concern at that point was "we've invested in Cloudflare's ecosystem — DNS, DDoS, CDN, now Pages. Does switching Pages create fragmentation?"

**Sarah Chen (3:52):** And how did that concern resolve?

**Wei Zhang (4:10):** I realized I was conflating two separate things. Cloudflare's network product is excellent — we're keeping that. DNS, DDoS protection, the CDN for our static assets — none of that is changing. We're just moving the application deployment layer, which is actually less integrated with the rest of Cloudflare than I assumed. Alicia pointed out that our site was already behind Cloudflare's CDN and we could keep that while deploying on Acme.

**Priya Nair (4:55):** That's a common question. Acme can sit behind Cloudflare's CDN — you'd use Acme as the origin and Cloudflare's network would still front your traffic. You get Cloudflare's DDoS and network performance, and Acme's developer experience and deployment workflow. They're complementary, not competitive for that use case.

**Wei Zhang (5:28):** That was the technically correct answer that I didn't have until Marcus — sorry, Priya — explained it. Once I understood that, the conversation became much simpler.

**Sarah Chen (5:52):** What drove the decision — was it primarily Alicia's technical preference, or were there business factors?

**Wei Zhang (6:10):** Both. Alicia's technical conviction was necessary — if she wasn't enthusiastic, I wouldn't have pushed. But the business factor was the checkout personalization performance. We saw a 12% improvement in checkout completion rate when Alicia rebuilt the personalization logic on Acme Edge Functions during our trial. At our GMV, that's meaningful revenue.

**Sarah Chen (6:52):** That's a compelling number. How did you calculate the revenue impact?

**Wei Zhang (7:10):** We ran the trial on 20% of traffic for 2 weeks. The checkout completion rate lift was consistent. Extrapolated to full traffic, the annual revenue impact is significant — I don't want to share the exact number but it was enough to justify the platform change with a lot of room to spare.

**Alicia Nguyen (7:42):** The trial methodology was Priya's suggestion, actually. Running it on 20% of traffic using Edge Functions for the A/B split meant we had real production data without risking the full checkout flow.

**Priya Nair (8:08):** The A/B structure was important — it meant the trial was generating business data, not just technical validation. Wei could see the revenue lift in real time, which is a very different conversation than "our builds are faster."

**Sarah Chen (8:35):** Wei, were there any moments during the evaluation where you almost chose to stay on Cloudflare?

**Wei Zhang (8:55):** One. The pricing comparison. Cloudflare Pages on our scale is genuinely cheaper for pure hosting costs. When I first saw Acme enterprise pricing, I pushed back.

**Sarah Chen (9:18):** What resolved that?

**Wei Zhang (9:32):** The checkout revenue lift. The pricing difference is a rounding error compared to a 12% improvement in checkout completion. Once I had that data from the trial, the pricing conversation changed completely. I also realized we'd been underestimating how much developer time we were spending on Cloudflare Workers workarounds. Alicia, what was your estimate?

**Alicia Nguyen (10:00):** The checkout personalization feature alone — I had 3 weeks of work to get it functioning correctly on Cloudflare Workers. The Acme rebuild took 4 days. That's 2 weeks of engineer time saved on one feature. Over a year of shipping features, that compounds.

**Sarah Chen (10:35):** That's a quantified ROI case that wasn't in our proposal — did you calculate it separately?

**Wei Zhang (10:52):** Alicia did. She knew I'd ask about the economics so she built the spreadsheet without being asked. That's why she's the senior engineer.

**Sarah Chen (11:18):** Alicia, is there anything from the trial that gave you pause — a technical concern that didn't fully resolve?

**Alicia Nguyen (11:38):** One thing. Cloudflare Workers have a very tight CPU time limit per request — 10ms on the free plan, 50ms on paid. Acme Edge Functions have higher limits and behave more predictably under load. But I wanted to validate that behavior at our peak traffic — we have seasonal spikes during promotional events. I didn't have time to test that before we signed.

**Priya Nair (12:15):** That's on my list for the first 90 days — we should do a load test on your checkout flow Edge Functions before your next promotional event. When is that?

**Alicia Nguyen (12:32):** We have a spring sale in late March.

**Priya Nair (12:48):** Perfect. We have time. I'll schedule a load test session in early March — we'll run it at 3x your peak estimate and make sure the Edge Function behavior is confirmed before you're in a promotional window.

**Wei Zhang (13:10):** That's the kind of proactive support that made me comfortable signing before completing that validation. If you'd said "figure it out yourself," we would have waited.

**Sarah Chen (13:38):** Any advice for other CTOs evaluating a switch from Cloudflare Pages?

**Wei Zhang (14:02):** Three things. One: separate the Cloudflare network from the Cloudflare Pages decision. They're different products and the dependency is smaller than you think. Two: run a trial on something with a measurable business outcome, not just a technical benchmark. Checkout completion is more persuasive than build time. Three: talk to the engineers who will live with the platform, not just the architects who evaluate it. Alicia's conviction was as important as my economic analysis.

**Sarah Chen (14:52):** That's genuinely useful. Alicia, same question.

**Alicia Nguyen (15:10):** For engineers: don't evaluate on the demo. Get your actual code running on the platform and build one real feature. The workaround count is the honest signal — if you're writing workarounds in the first week, that tells you something. On Acme, I wasn't.

**Sarah Chen (15:42):** Wei, Alicia — thank you. This was more useful than most debriefs I do. I'm going to make sure Priya's load test is on the calendar before we hang up. Priya?

**Priya Nair (16:00):** I'll send a calendar invite for March 5th — does that work?

**Alicia Nguyen (16:12):** Works for me.

**Wei Zhang (16:20):** Good. We're looking forward to the spring sale being on Acme.

**Sarah Chen (16:35):** Looking forward to it with you. Talk soon.
