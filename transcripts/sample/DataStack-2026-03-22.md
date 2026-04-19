# DataStack — Late-Stage Stuck Deal
**Date:** 2026-03-22
**Participants:** Jordan Reeves (Acme AE), Priya Nair (Acme SE), Owen Fletcher (Engineering Manager, DataStack)
**Duration:** 28 minutes

*Note: This is a synthetic transcript created for demonstration purposes.*

---

## Full Transcript

**Jordan Reeves (0:28):** Owen, good to hear from you. It's been a few weeks — I was starting to wonder if we'd lost you. How are things?

**Owen Fletcher (0:42):** Ha, yeah, sorry about that. It's been a rough few weeks internally. Things have been a bit chaotic.

**Jordan Reeves (1:00):** No worries at all. I'm glad we found time today. Where are things with the Acme evaluation — last we spoke, you were expecting to have a decision by the end of February. Can you catch me up?

**Owen Fletcher (1:22):** Yeah, so, the decision got delayed. Our CTO — Marcus, not your Marcus — he got pulled into an acquisition integration project in early February and basically deprioritized all the tooling evaluations. It's been in limbo since.

**Jordan Reeves (1:48):** Got it. Is the acquisition integration still consuming his attention, or has things settled down?

**Owen Fletcher (2:05):** It's mostly settled, but the dust hasn't fully cleared. There's been some reorg talk — nothing official — but it's made people cautious about committing to new spend.

**Jordan Reeves (2:28):** That's a common dynamic after acquisitions. Can I ask — where does the Acme decision fit in the context of the reorg uncertainty? Is it on hold pending clarity, or is it still something you're trying to push through?

**Owen Fletcher (2:50):** Honestly, I'm still trying to push it through. The pain hasn't gone away — our deploy process is still slow and our team is still frustrated. But my ability to get Marcus's attention on tooling decisions has dropped significantly.

**Jordan Reeves (3:20):** I appreciate you being straight with me. Let me ask a direct question: is Marcus still the economic buyer for this, or has the reorg changed who needs to approve it?

**Owen Fletcher (3:42):** That's... actually a good question. He's still technically my CTO, but there's a possibility that the combined engineering team will have a different structure. If that happens, I honestly don't know who approves tooling decisions at that level.

**Jordan Reeves (4:10):** So you might be in a situation where you're trying to get approval from someone who isn't yet sure if they'll be in that role. Is that a fair characterization?

**Owen Fletcher (4:28):** Yes. Which is why I've been hesitant to push. Pushing for a decision from the wrong person at the wrong time is a bad look politically.

**Jordan Reeves (4:55):** I understand. Have you had any direct conversations with Marcus about the Acme evaluation since February?

**Owen Fletcher (5:12):** Briefly. He remembers it, he said "let's pick this up when things calm down." But he didn't give me a timeline.

**Jordan Reeves (5:35):** And the technical work you did — the proof of concept, the security review — is that still valid? Or has anything changed on the requirements side?

**Owen Fletcher (5:52):** The POC is still valid. Our requirements haven't changed. If anything, the problem has gotten worse — we hired three more frontend engineers and the deployment bottleneck is more painful than it was three months ago.

**Jordan Reeves (6:18):** Has anything changed on the competitive side? Are you still evaluating alternatives, or is Acme still the primary option you're working toward?

**Owen Fletcher (6:38):** We're not actively evaluating anyone else. The team liked Acme from the POC. Vercel came up early but we ruled it out — pricing concerns and the lock-in risk.

**Jordan Reeves (7:02):** That's good to know. Let me ask about the size of this deal — have the requirements changed? When we talked in January, you were looking at the Business plan for 12 engineers. Is that still the scope?

**Owen Fletcher (7:25):** Actually it's grown. We're now at 18 frontend engineers and the scope has expanded — we want to migrate both the main product and our docs site. The business case has gotten stronger, not weaker.

**Jordan Reeves (7:52):** So the deal is bigger and the problem is more acute, but the organizational dynamics are holding it up. That's a solvable problem, but we need to find the right lever. Can I think through this with you for a minute?

**Owen Fletcher (8:10):** Go ahead.

**Jordan Reeves (8:28):** There are a few paths. One: you wait for the reorg dust to settle — safer politically but could be months, and in the meantime your team keeps dealing with the pain. Two: you try to get a decision under your own budget authority — do you have discretionary budget at a level that would cover a starter Acme plan for a subset of the team? A pilot that doesn't need CTO sign-off?

**Owen Fletcher (9:00):** Hmm. I have up to $5,000 a month in discretionary tools budget. What would a scaled-down Acme deployment for, say, six engineers look like?

**Jordan Reeves (9:22):** Our Business plan for six developers with the feature set you need — Deploy Previews, Functions, single site deployment — would be around $300-400 a month. That's well within your budget.

**Owen Fletcher (9:45):** So I could start there without needing Marcus's approval.

**Jordan Reeves (10:02):** Exactly. And there's a strategic benefit beyond just getting started — you'd go into the CTO conversation with live data: "We've been running on Acme for 90 days, deploy time is down from 40 minutes to 8, here's the team feedback." That's a very different conversation than "here's what the vendor promised us."

**Owen Fletcher (10:38):** I like that framing. Honestly, Marcus is more likely to approve an expansion of something that's already working than sign off on a new vendor relationship right now.

**Jordan Reeves (11:00):** That's been the pattern we've seen. It also means you're not waiting for organizational clarity to solve your team's problem. Your engineers don't have to keep dealing with the slow deploys while the politics sort themselves out.

**Owen Fletcher (11:28):** Okay. What would that actually look like — can we start on a pilot this week?

**Jordan Reeves (11:45):** Yes. You can sign up for Business plan today and have your first site deployed this week — Priya can support the technical setup. Then we'd treat this as the foundation, with a formal expansion proposal to Marcus once you have the data.

**Priya Nair (12:05):** Owen, I can schedule a setup session with you and one or two of your engineers this week — Thursday or Friday. We'd get the first project live, configure the deploy settings, and do a build time benchmark against your current setup. That gives you real numbers within a week.

**Owen Fletcher (12:35):** That works. Let's do Friday morning — 9am Pacific.

**Jordan Reeves (13:00):** Let me also ask — is there a specific event in the next 30-60 days that might create a natural forcing function for the broader decision? A product launch, a board meeting, anything that would make "we need the deployment infrastructure resolved" more urgent for Marcus?

**Owen Fletcher (13:28):** Actually, yes. We have a board meeting in late April — the 28th. Marcus will be presenting on engineering velocity and technical debt. If I have 60 days of Acme data by then, that could be a natural moment to propose the full rollout as a line item.

**Jordan Reeves (13:58):** That's exactly the kind of forcing function that works. Here's what I'd suggest: we launch the pilot this week, build a 45-day results summary by mid-May that ties deploy velocity to engineering productivity, and position it as "here's what full adoption would unlock" going into the board prep. Does that align with how Marcus thinks about these decisions?

**Owen Fletcher (14:35):** Marcus is very data-driven. He'll want to see actual numbers, not projections. If we have 60 days of real data showing the improvement, that's his language.

**Jordan Reeves (15:00):** Then let's make sure the pilot is instrumented right from the start. Priya, can we set up deploy time tracking from day one so we have a clean before-and-after comparison?

**Priya Nair (15:18):** Absolutely. I'll configure Acme Analytics and set up a simple tracking dashboard — deploy time, build success rate, team adoption rate. We can pull a summary report at 30 and 60 days.

**Jordan Reeves (15:45):** Owen, one last question — on the expansion conversation with Marcus, is there anything that would make him less receptive to this? A concern about Acme specifically that we haven't addressed, or a preference for staying on AWS-managed services?

**Owen Fletcher (16:15):** He did ask once about AWS integration — whether Acme has proper VPC or IAM integration. We're using a few AWS services on the backend and he's security-conscious about data flow.

**Priya Nair (16:40):** Good to know. Acme doesn't run inside your VPC — we're a managed platform. But data leaving to your backend services goes over HTTPS, and you can restrict which origins your Edge Functions and site can communicate with. If there are specific AWS services your frontend needs to talk to, I can map out that architecture so Marcus has a clear picture. That might also be worth including in the data we present to him.

**Owen Fletcher (17:15):** Yes, that would help. His concern isn't a blocker, but having a clear answer preemptively is better than him asking in the board meeting.

**Jordan Reeves (17:40):** I'll make sure that's in the documentation we prepare for the expansion proposal. Okay — I think we have a clear plan. Pilot starts Friday with Priya. We build the data over 60 days. I'll prepare an expansion proposal timed to the board meeting prep. Does that feel right?

**Owen Fletcher (18:05):** Yeah. I feel better about this than I did before the call. I'd been avoiding it because I didn't see a path, but this is actually a path.

**Jordan Reeves (18:28):** Good. Let's make it happen. I'll send a calendar hold for Friday and connect you with Priya directly. And let's check in at the 30-day mark — say, April 25th — to see how the pilot data looks.

**Owen Fletcher (18:50):** Sounds good. Talk Friday.
