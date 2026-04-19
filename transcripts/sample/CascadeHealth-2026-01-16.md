# Cascade Health — Technical Scoping (Security-Focused)
**Date:** 2026-01-16
**Participants:** Marcus Webb (Acme SE), Jordan Reeves (Acme AE), Priya Das (Senior Platform Engineer, Cascade Health), Leo Huang (Security Engineer, Cascade Health)
**Duration:** 55 minutes

*Note: This is a synthetic transcript created for demonstration purposes.*

---

## Full Transcript

**Jordan Reeves (0:28):** Priya, Leo — thanks for joining. Marcus is our SE and he's been briefed on your context. Before we get into the technical detail, can you give Marcus a quick summary of where you are?

**Priya Das (0:48):** Sure. We're a health information technology company — we build software for hospital systems. We currently deploy our patient-facing portal on AWS Amplify. We've been running into problems on two fronts: build times are terrible and getting worse as our codebase grows, and we're going through a HIPAA compliance review this quarter that's putting scrutiny on all our vendor relationships. Our CISO flagged Amplify's documentation gaps.

**Marcus Webb (1:22):** That's exactly the right framing. Let me ask a few questions before showing anything. First — is the patient portal a public-facing site, a authenticated application, or both?

**Priya Das (1:40):** Both. The public side is marketing content — clinic locator, service descriptions, appointment scheduling forms. The authenticated side is the actual patient portal — access to records, appointment management, message your doctor.

**Marcus Webb (2:05):** Important distinction. The authenticated application — is PHI actually rendered in the frontend, or does the frontend just authenticate and then call backend APIs that return PHI?

**Priya Das (2:22):** The frontend is a Next.js app that calls our backend APIs. PHI lives in the backend — the frontend renders it but doesn't store it. We're careful about that.

**Marcus Webb (2:45):** That's the right architecture. So Acme would be hosting the Next.js shell and static assets — the PHI flows through your backend APIs, not through our infrastructure.

**Leo Huang (3:02):** That's the architecture, yes. But our CISO still wants to understand Acme's security posture for hosting the frontend, because even if PHI isn't stored there, it's the entry point that patients use.

**Marcus Webb (3:20):** Completely reasonable. Leo, what does your CISO need specifically? I want to make sure I'm addressing the actual requirements rather than what I assume they are.

**Leo Huang (3:38):** A few things. One — SOC 2 Type II report. Two — BAA: does Acme offer a Business Associate Agreement? Three — our pen test questionnaire, which I'll need to send you. Four — data residency: where are our builds processed and where are assets stored? We have some state-level requirements around data not leaving certain jurisdictions.

**Marcus Webb (4:15):** Let me go through each. SOC 2 Type II — yes, we have it. Jordan can get that to you today under NDA. BAA — this is an important one. Acme does offer a BAA at the enterprise tier, specifically acknowledging our role as a Business Associate for the limited scope of data that passes through our infrastructure. For your use case — PHI rendered by the frontend, not stored — the BAA primarily covers the build pipeline and any edge processing. I'll have Jordan send the BAA template today.

**Leo Huang (5:02):** That's better than Amplify. We asked AWS for BAA language specific to Amplify and got their generic AWS BAA, which took weeks to review and didn't address our specifics.

**Marcus Webb (5:28):** Understood. Data residency — this is more nuanced. Our CDN edge nodes are globally distributed. Build processing happens in our infrastructure — US and EU regions available. If you need builds to run specifically in a region, we support that in enterprise contracts. For asset serving, the CDN serves from the closest edge node to the user by default, which may include international nodes. If you need geo-restrictions on asset delivery, we can configure that. What's the specific jurisdiction requirement?

**Leo Huang (6:10):** Our primary concern is build logs and artifacts not leaving the US. Patient data isn't in the build process, but we've had legal counsel advise that any data processing for a healthcare customer should be US-only as a conservative interpretation.

**Marcus Webb (6:38):** US-only builds — we can configure that at the enterprise tier. The build worker runs in US-region infrastructure. Logs and artifacts are stored in US-region S3. I'll have this documented specifically for your legal review. The CDN serving is still globally distributed by default — do you need asset delivery to be US-restricted as well?

**Leo Huang (7:05):** Our patients are US-based, so practically speaking most traffic is US. We don't need to restrict asset delivery globally — we just need the data processing to be US-based.

**Marcus Webb (7:22):** Then we're aligned. Build processing US-only, CDN serving global with US-predominant traffic. That's a clean configuration. Let me turn to the actual build performance problem — Priya, tell me about your current setup.

**Priya Das (7:45):** We're on Next.js 14 with the App Router. Our codebase has grown significantly — we have about 240 routes. Amplify builds currently take 28-35 minutes. We deploy about 8-10 times a week for the main portal, plus more frequently for the marketing content side.

**Marcus Webb (8:15):** 240 routes at 28-35 minutes — that's consistent with Amplify's full-rebuild behavior. Are you using any ISR or just SSR and static?

**Priya Das (8:35):** Mixed. Marketing content is mostly static with ISR for CMS updates. The authenticated portal is server-rendered — most pages need to be dynamic because they're patient-specific.

**Marcus Webb (8:58):** For the SSR pages, those don't benefit from ISR caching by definition — they're dynamic per user. That's fine. The optimization opportunity is on the build side for your static pages and the ISR invalidation for your marketing content. Let me show you the dependency caching behavior...

[Marcus shares screen and walks through the Acme build configuration]

**Marcus Webb (9:35):** This is what a typical acme.toml looks like for a Next.js app with your pattern. The key section here — `[build.processing]` — is where we configure incremental builds. The build cache here means that unchanged routes don't rebuild. For your 240-route app, if you're deploying a change that touches 30 routes, only those 30 routes rebuild. The remaining 210 stay cached.

**Priya Das (10:15):** What's the practical build time improvement we'd expect?

**Marcus Webb (10:32):** For a change-set that touches 10-15% of routes — which sounds like a typical deploy for you — you'd go from 28-35 minutes to roughly 5-8 minutes. For a large release touching most of the codebase, you'd be closer to 15-18 minutes.

**Priya Das (10:58):** Even 15-18 minutes on a big release is better than our current baseline. Can that be validated in a trial?

**Marcus Webb (11:18):** Yes. The best test is deploying your actual app — not a representative app — because the caching behavior depends on your specific dependency graph. I can set up a trial and run your first deploy so we get real numbers, not estimates. How's Friday?

**Priya Das (11:42):** Friday works.

**Leo Huang (12:00):** Before we go deeper on build performance — can I ask about your penetration testing posture? We run our own pen tests annually and we'll need to know if there are restrictions on testing Acme-hosted applications.

**Marcus Webb (12:20):** Our pen test policy for enterprise customers: you can test your own site/application without restriction. You cannot test our shared infrastructure (our CDN nodes, build system, etc.) — that's separately audited by our third-party security firm. So for your purposes, you can run a full pen test against your patient portal on Acme as if it were your own infrastructure. Any findings that appear to be in our shared layer, we'd want to know about under responsible disclosure.

**Leo Huang (12:58):** That's a cleaner policy than what Amplify gave us. Their answer was essentially "open a support ticket and we'll tell you case-by-case."

**Marcus Webb (13:18):** That's not a policy, that's an obstacle. Our pen test policy is in writing in our security documentation — Jordan will send it with the other security materials.

**Jordan Reeves (13:38):** Leo, do you want me to send all the security materials today — SOC 2 under NDA, BAA template, pen test policy, and the pre-filled security questionnaire? That gives you and your CISO everything to review in parallel while Marcus and Priya do the technical trial.

**Leo Huang (13:58):** Yes. Send those today.

**Marcus Webb (14:15):** Priya, one more thing I want to cover — your marketing content CMS. What are you using?

**Priya Das (14:32):** Contentful for the marketing side. The patient portal content is pulled from our own backend — patient-specific data through our APIs.

**Marcus Webb (14:50):** Acme Connect has a native Contentful integration. When an editor publishes in Contentful, it triggers page-level cache invalidation and rebuilds only the affected marketing pages. Right now, how does a marketing content update get to production?

**Priya Das (15:12):** Manual process — a content editor notifies our frontend team, we trigger a build, and it deploys in 30+ minutes. It's a bottleneck.

**Marcus Webb (15:35):** With Acme Connect, that whole loop becomes: editor publishes in Contentful → Acme detects the webhook → rebuilds only the affected pages → pages are live in 3-5 minutes, automatically. No human in the loop, no 30-minute wait.

**Priya Das (16:00):** That would solve a complaint we get from the marketing team every week. Can we include that in the trial scope?

**Marcus Webb (16:18):** Absolutely. I'll set up Connect as part of the trial configuration on Friday. You'll see the full automated flow.

**Jordan Reeves (16:40):** Let me make sure we have clear next steps. Marcus and Priya — Friday trial session, scoped to build performance, ISR behavior, and Connect integration. Leo — I'm sending the full security package today. What's the decision timeline? Is there a contract or evaluation gate we should know about?

**Priya Das (17:05):** We want to make a decision by end of January. We're trying to get off Amplify before our next HIPAA review cycle in Q2, and migration takes time.

**Jordan Reeves (17:28):** End of January is tight. If the Friday trial goes well and the security review is clean, can we be in contract discussions by January 22nd?

**Priya Das (17:48):** That's aggressive but doable if Marcus's trial delivers what he's describing.

**Leo Huang (18:05):** The CISO review is usually 2 weeks. If I send the materials today, I can have her review complete by January 30th. That's the critical path.

**Jordan Reeves (18:28):** Then the security review is the long pole. Leo — if anything in the documentation raises a question that's dealbreaking, I want to know by January 20th so we have time to address it rather than having it block us at the end. Can we set a midpoint check-in?

**Leo Huang (18:52):** January 20th check-in. I'll flag any concerns by then.

**Jordan Reeves (19:12):** Perfect. I'll send a calendar hold. Talk Friday, Priya.

**Priya Das (19:25):** Looking forward to it.
