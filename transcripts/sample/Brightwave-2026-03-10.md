# Brightwave — Discovery Call
**Date:** 2026-03-10
**Participants:** Sarah Chen (Acme AE), Jordan Kim (Engineering Manager, Brightwave), Priya Patel (Senior Frontend Engineer, Brightwave)
**Duration:** 38 minutes

*Note: This is a synthetic transcript created for demonstration purposes.*

---

## Full Transcript

**Sarah Chen (0:32):** Thanks for making time today, Jordan. I saw you signed up through our website and had a few questions before I dive in — would it be okay if I spent the first 10 minutes understanding where you are before we get into anything about Acme specifically?

**Jordan Kim (0:48):** Yeah, that works. I appreciate you not jumping straight into a pitch.

**Sarah Chen (1:05):** Perfect. So — at a high level, what brought you to look at Acme now? What's happening at Brightwave that made this a priority?

**Jordan Kim (1:22):** Honestly, we've been on Heroku for about four years. It's been fine. But we're growing faster than we expected — we went from 20 engineers to 65 over the past 18 months — and the deployment process hasn't kept up. We're shipping slower now than we were with half the team.

**Sarah Chen (1:48):** That's the opposite of what you'd expect with more engineers. What does slow look like for you — are we talking about deploy time, review cycles, something else?

**Jordan Kim (2:05):** Both, honestly. Our main deploy takes anywhere from 25 to 45 minutes depending on what changed. And we don't have good preview environments — so when a designer or a PM wants to review something, they're either waiting for a staging push or they're just reviewing it in a video call. It's manual and it's slow.

**Priya Patel (2:31):** The preview problem is actually worse than Jordan is describing. We've got 8 frontend engineers, and whenever multiple people are working on different features, staging becomes a conflict zone. Someone pushes to staging and breaks someone else's review. We've basically stopped using staging for reviews because of it.

**Sarah Chen (2:58):** Got it. So you've got two separate problems — long build and deploy times, and a staging environment that's become a bottleneck because it's shared. Is that fair?

**Jordan Kim (3:12):** Yeah, exactly.

**Sarah Chen (3:20):** How long has the staging problem been bad? Is this a recent thing or has it been building?

**Priya Patel (3:35):** Six months maybe? When we were smaller it wasn't a problem. Now it's constant. We've had actual arguments in Slack about who gets staging on a given day. It's embarrassing.

**Sarah Chen (4:00):** Have you tried anything to fix it — separate staging branches, more environments, anything like that?

**Jordan Kim (4:15):** We've talked about spinning up additional staging environments on Heroku, but the cost and setup time makes it not worth it. We'd need DevOps time we don't have. We're a product-focused company — we don't have a platform team.

**Sarah Chen (4:40):** That's an important detail. So no dedicated platform or DevOps engineering — your frontend engineers are managing their own deployment needs.

**Jordan Kim (4:55):** Right. Priya and one other engineer are basically doing double duty — half their time is product work, half is keeping the deployment stuff running. That's not what I hired them to do.

**Sarah Chen (5:20):** What's the cost of that — if you had to put a number on the engineering time going into deployment maintenance, what would it be?

**Jordan Kim (5:42):** Priya, you probably know this better than I do.

**Priya Patel (5:50):** Honestly, between the two of us, it's probably 25-30% of our time. And that's just maintenance — not improvements, not new tooling. Just keeping it from breaking.

**Sarah Chen (6:15):** So roughly half an engineer full-time going to deployment maintenance. At your headcount that's a significant cost. Has that number been growing as you've scaled?

**Jordan Kim (6:32):** Yes. When we were 20 engineers, it was maybe 10%. Now it's 25-30%. If we double the team again, I don't even want to think about it.

**Sarah Chen (7:00):** Let me ask about the business side — what's the downstream effect of slower releases? Does engineering speed affect anything the business cares about?

**Jordan Kim (7:22):** Yes. We've missed two product commitments in the last quarter — things we told customers we'd have ready that slipped because the feature took longer to get through the deployment process than expected. Our CPO is aware of it. It's becoming a recurring conversation.

**Sarah Chen (7:52):** Have those slippages had customer impact — renewals, expansion, anything like that?

**Jordan Kim (8:05):** One situation where a customer pushed back on their renewal timing because a feature they were counting on wasn't ready. We ended up holding the price flat for an extra quarter. So yes, there's been commercial impact, though we've avoided losing anyone over it so far.

**Sarah Chen (8:35):** That's really helpful context. Let me shift to the other side — what does your current stack look like? What framework are you building on?

**Jordan Kim (8:50):** We're primarily Next.js. We moved to it about two years ago. React before that.

**Priya Patel (9:02):** Next.js 14 with the App Router. We use TypeScript across the board.

**Sarah Chen (9:18):** And where does the frontend deploy to today — just Heroku, or do you have anything else?

**Priya Patel (9:32):** Just Heroku for the main app. We have a small marketing site on a separate stack — that's on Webflow, managed by the marketing team. But the product itself is all Heroku.

**Sarah Chen (9:55):** And on the backend — is Heroku hosting backend services too, or are we specifically talking about the frontend?

**Jordan Kim (10:10):** Backend is on AWS. We have a Python FastAPI stack on ECS. The Heroku piece is specifically the Next.js frontend.

**Sarah Chen (10:28):** Got it. So the pain is specific to the frontend deployment pipeline — not a broader infrastructure overhaul.

**Jordan Kim (10:40):** Correct. We're not looking to move everything. Just the frontend.

**Sarah Chen (11:00):** Makes sense. Can I ask — what does the current deployment flow look like from commit to production? Walk me through the steps.

**Priya Patel (11:18):** Sure. Developer pushes to a feature branch. We have a GitHub Actions pipeline — it runs our test suite, which takes about 8 minutes. Then it builds the Next.js app, which is where most of the time goes — that's been getting slower as the codebase grows, we're at about 18-22 minutes. Then it deploys to Heroku, which is another 5-8 minutes. Total from push to production is usually 30-40 minutes on a good day.

**Sarah Chen (11:55):** And if something goes wrong — a bad deploy — what's the rollback process?

**Priya Patel (12:10):** We redeploy the previous commit. Which means going through that same pipeline again. So a rollback is another 30-40 minutes.

**Sarah Chen (12:30):** I want to come back to the business timeline question — do you have a sense of when you want this resolved? Is there a specific date or event driving the urgency?

**Jordan Kim (12:50):** We're doing a significant product launch in Q2 — end of May. Our engineering capacity is going to be stretched thin getting features ready, and we can't afford the deployment overhead on top of that. If we're going to make a change to our deployment stack, it needs to happen before May, otherwise we'll be changing tooling during a launch, which is the worst possible time.

**Sarah Chen (13:20):** That's a concrete timeline — basically 6-8 weeks from now to get something in place and stable before the Q2 crunch. Is that the right read?

**Jordan Kim (13:38):** Yes. We need it live and stable before mid-April, realistically, so we have time for people to get comfortable with it before May gets busy.

**Sarah Chen (14:05):** Got it. That's actually helpful because it's a real constraint. Let me ask about the decision side — beyond you and Priya, who else would be involved in choosing a new deployment platform?

**Jordan Kim (14:28):** It'll mostly be me. My manager is our VP of Engineering, Rebecca Lam. She's supportive of modernizing the stack but she's not going to get into the details of the tooling evaluation. She'll want to know cost impact and that I'm confident in the choice.

**Sarah Chen (14:55):** And budget-wise — do you have a sense of what you're spending on Heroku now, and whether there's flexibility for a change?

**Jordan Kim (15:18):** We're paying about $800 a month on Heroku right now. I have discretionary budget for tools up to about $2,000 a month before I'd need to escalate to Rebecca. So cost isn't a primary concern as long as it's in that range.

**Sarah Chen (15:45):** That's useful. And are you evaluating anyone else, or is Acme currently the first conversation you're having?

**Jordan Kim (16:00):** We've looked at Vercel. Honestly, Priya is a bigger fan of Vercel than I am — partly because we're on Next.js and Vercel is very Next.js native. But I have some concerns about pricing at scale and vendor lock-in.

**Priya Patel (16:22):** I wouldn't say I'm a Vercel fan, exactly — I just think their DX for Next.js is really polished. But I've heard the pricing can get unpredictable.

**Sarah Chen (16:45):** Have you done a trial with Vercel or just looked at their site?

**Jordan Kim (16:58):** Just their site and some blog posts. No trial yet.

**Sarah Chen (17:15):** Fair enough. I'll be straightforward — Vercel's Next.js DX is genuinely strong, especially if you're using newer Next.js features. Where we tend to win is teams that are thinking beyond today's stack — framework-agnostic platform, more predictable pricing at team scale, and stronger headless CMS and data layer support if you ever want to go composable. But I'd rather show you than tell you — does it make sense to get you both into a trial so you can form your own view?

**Jordan Kim (17:55):** Yeah, that would be useful. How long does a trial typically take to set up?

**Sarah Chen (18:12):** You can have a real project deployed in under 30 minutes. Priya, could you spare time this week to get a branch of your Next.js app deployed to Acme? Even just the marketing pages or a feature branch — the point is to see the deploy preview experience and compare build times.

**Priya Patel (18:38):** That's pretty low friction. Yeah, I could probably do that Thursday or Friday.

**Sarah Chen (19:00):** Let me also set up a technical session with our Solutions Engineer — his name is Marcus, he works with a lot of Next.js teams and can walk through the App Router specifics and anything around build optimization. Would that be valuable?

**Jordan Kim (19:22):** Yes. Build time is a big deal for us — if Acme can improve on our current 18-22 minute builds, that changes the math significantly.

**Sarah Chen (19:45):** Marcus has done a lot of work on Next.js build caching and incremental builds. I'll get him in for that conversation. Can we lock in time next week — Tuesday or Wednesday?

**Jordan Kim (20:00):** Tuesday works. Let's say 10am Pacific.

**Sarah Chen (20:15):** Perfect. I'll send a calendar invite. To confirm the plan: Priya deploys a branch this week to get the preview experience, Marcus and I do a technical session next Tuesday to go deeper on build performance and architecture — and that gives you enough information to make a recommendation to Rebecca before the end of March. Does that sound right?

**Jordan Kim (20:42):** Yes, that sounds like a good plan.

**Sarah Chen (21:00):** One last thing — is there anything you haven't mentioned that I should know about? Security requirements, compliance, anything that would be a dealbreaker?

**Jordan Kim (21:18):** We don't have heavy compliance requirements right now. SOC 2 would be good to have documented for when we have enterprise customers asking, but it's not blocking anything today.

**Sarah Chen (21:38):** Acme is SOC 2 Type II certified — Marcus can walk through our security posture in the technical call if that's useful. Great, I think we have everything we need for now. I'll get that invite out for Tuesday and look forward to seeing what you think of the trial.

**Jordan Kim (21:58):** Great. Thanks, Sarah.

**Priya Patel (22:05):** Yeah, looking forward to it.
