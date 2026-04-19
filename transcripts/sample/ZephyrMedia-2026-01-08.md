# Zephyr Media — Discovery Call (Vercel Displacement)
**Date:** 2026-01-08
**Participants:** Jordan Reeves (Acme AE), Cassandra Bell (VP Engineering, Zephyr Media), Raj Patel (Staff Engineer, Zephyr Media)
**Duration:** 42 minutes

*Note: This is a synthetic transcript created for demonstration purposes.*

---

## Full Transcript

**Jordan Reeves (0:35):** Cassandra, Raj — appreciate you taking the time. I saw you reached out through our website so I want to make sure I understand the context before we get into anything. What's driving the evaluation?

**Cassandra Bell (0:52):** Happy to get into it. We've been on Vercel for about 18 months. It's been fine technically — not the problem. The problem is we've had two pricing surprises in the last two quarters that I can't explain to my CFO. We had a traffic spike during one of our editorial campaigns and our Vercel bill jumped 140% that month. Then Q4 holiday traffic and another spike we didn't budget for.

**Jordan Reeves (1:28):** That's a very specific and concrete problem. Walk me through the architecture — what are you running on Vercel?

**Cassandra Bell (1:42):** We're a digital media company — we publish about 400 articles a week across 6 editorial brands. Our main platform is Next.js 14 on Vercel. We have high read traffic with occasional large spikes when a piece goes viral. The editorial cycle means deploys are frequent — we push 40-50 times a week.

**Raj Patel (2:10):** From a technical standpoint, we use a lot of ISR — Incremental Static Regeneration — because of our content volume. Vercel's ISR is very tightly integrated. That's the part I'm most worried about if we move platforms.

**Jordan Reeves (2:35):** Raj, that's the right thing to be worried about. Before I address it — Cassandra, when you say pricing surprises, is it specifically function invocations, bandwidth, something else?

**Cassandra Bell (2:52):** Function invocations and edge middleware invocations. We use Vercel's middleware for locale detection and personalization. Every request runs through middleware. When traffic spikes, the invocation count spikes with it, and the cost model is per-invocation.

**Jordan Reeves (3:20):** Got it. That's a known friction point with Vercel's pricing model at media scale. Our model is bandwidth-based — you pay for data transferred, not for the number of times your functions execute. For a media company with middleware-heavy traffic, that's a significant structural difference.

**Raj Patel (3:45):** Can you quantify that? Like, roughly what would our Vercel bill have looked like on Acme's model?

**Jordan Reeves (4:02):** I'd need your traffic numbers to be precise, but here's the framing: if you're paying for middleware invocations at scale, and your traffic spikes 10x during a campaign, your bill spikes 10x. On a bandwidth model, a campaign that generates 10x traffic might only generate 3-4x in bandwidth if the content is well-cached. What was your high-water mark Vercel bill?

**Cassandra Bell (4:32):** The Q4 spike took us from our typical $6,000/month to just over $22,000 that month.

**Jordan Reeves (4:48):** And what was your traffic multiple that month versus typical?

**Cassandra Bell (5:02):** About 8x typical traffic for roughly 3 weeks.

**Jordan Reeves (5:18):** If that same traffic came through Acme's model, the bandwidth growth would be significant but more linear — you wouldn't be paying for every middleware execution individually. My guess, without modeling it properly, is you'd have seen a 50-60% lower spike on the bill. I'll put together a proper model if you can share your typical monthly request volume.

**Cassandra Bell (5:48):** That would be useful. Raj, what are our numbers?

**Raj Patel (5:58):** Typically about 350 million requests per month. The spike month was closer to 2.4 billion.

**Jordan Reeves (6:15):** Those are meaningful numbers and they're exactly where the Vercel per-invocation model becomes expensive. Let me now come back to Raj's question about ISR — because I want to be straight with you, not just tell you it's fine.

**Raj Patel (6:35):** Please.

**Jordan Reeves (6:48):** Vercel's ISR is tightly integrated with Next.js because Vercel built Next.js. Their implementation of on-demand revalidation and the `revalidatePath` / `revalidateTag` APIs is as good as it gets. We support ISR on Acme — it works correctly for the standard patterns. Where you might see differences is in edge cases with aggressive revalidation at high frequency. For a media company publishing 400 articles a week, you're likely in the standard ISR patterns, but I'd want our SE to verify that. Can I get Marcus on a technical call?

**Raj Patel (7:30):** Yes. I specifically want to test ISR revalidation behavior under load. If that breaks, the migration doesn't happen regardless of pricing.

**Jordan Reeves (7:48):** Completely fair. That's the right gate to put up. Marcus has worked with high-traffic media publishers on Acme — I'll get him on a call and specifically scope it to your ISR and middleware use cases. He won't sugarcoat it if there are gaps.

**Cassandra Bell (8:15):** That approach is refreshing. We've had vendors promise things and then Marcus — er, our engineers — found the cracks in implementation. The honesty matters.

**Jordan Reeves (8:38):** I'd rather you discover a real issue in a trial than find it 3 months after migration. On the deployment side — 40-50 deploys per week is high. How does your editorial team trigger deploys? Is it automated on content publish, or manual?

**Raj Patel (9:02):** We have a webhook from our CMS — we use Sanity — that triggers a rebuild when editors publish. It's automated but it triggers full rebuilds more often than we'd like. We've been working on more granular invalidation but it's been complex on Vercel.

**Jordan Reeves (9:28):** Acme Connect has a native Sanity integration that can do page-level cache invalidation — so a content update triggers a rebuild only for the pages that changed, not the full site. For a media company publishing 400 articles a week, that could significantly reduce your build load. Is that a current pain point?

**Raj Patel (9:55):** We're spending more in build minutes than we expected on Vercel. Granular invalidation would help.

**Jordan Reeves (10:18):** Good to know. Let me ask about the business side — beyond the pricing problem, is there a timeline driving this? Are you going to renew Vercel or are you on monthly billing?

**Cassandra Bell (10:38):** We're on an annual contract. It renews in March. That's the window — if we're going to move, we need to decide by mid-February to have time to migrate before the renewal auto-processes.

**Jordan Reeves (11:05):** That's a hard deadline. Six weeks to make a decision and begin migration. Is that enough time?

**Cassandra Bell (11:22):** Our platform is complex but Raj's team is capable. If the technical evaluation goes well, we could move a subset of our brands first — a phased migration. Raj, do you agree with that?

**Raj Patel (11:40):** Yes. We have six brands. Two of them are smaller sites with lower traffic — we could move those first, validate the ISR behavior at our real traffic patterns, and then decide on the larger ones.

**Jordan Reeves (12:05):** That's a smart risk-managed approach. Let me ask one more thing on the decision side — beyond you and Raj, who else is in this decision? You mentioned the CFO is asking questions about the pricing.

**Cassandra Bell (12:28):** The CFO will want to know we've solved the budget predictability problem before we announce we're moving to a new platform. She doesn't get into vendor selection. Beyond that, it's really my call with Raj's technical sign-off.

**Jordan Reeves (12:55):** Good. That's a clean decision structure. My proposal: Marcus and Raj do a technical deep-dive this week, scoped to ISR and middleware, ideally with a proof of concept that lets Raj test actual behavior. In parallel, I'll build you a cost model using your request volume — typical and spike — so you have the pricing comparison in writing. You'd have both inputs by end of next week, which leaves you time to make a call and start migration before the February deadline.

**Cassandra Bell (13:25):** That timeline works. Raj, any objections?

**Raj Patel (13:32):** No — I want to see the ISR test results before anything else. If that's solid, I'm open to the migration.

**Jordan Reeves (13:50):** I'll set up the Marcus session — what day this week works for you both?

**Raj Patel (14:05):** Thursday afternoon.

**Cassandra Bell (14:12):** I might not be on that one — that can be Raj and Marcus.

**Jordan Reeves (14:25):** Works for me. Cassandra, I'll connect with you after the technical session with the cost model and Raj's findings. Friday?

**Cassandra Bell (14:38):** Friday works. Send the calendar invite.

**Jordan Reeves (14:52):** Will do. One last question — have you told Vercel you're evaluating alternatives? Sometimes contracts are renegotiable when a renewal is at risk.

**Cassandra Bell (15:10):** I mentioned it. Their response was to offer us a 10% discount on renewal. That doesn't solve the pricing structure problem — it just makes the unpredictable model slightly cheaper.

**Jordan Reeves (15:32):** Understood. The structural issue is what matters — a percentage discount on an unpredictable model is still an unpredictable model. We'll talk Friday.
