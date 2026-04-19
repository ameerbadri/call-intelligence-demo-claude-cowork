# Product Context — Acme

**This file is the primary customization point.** When adapting this repo for your
own company, replace everything below with your company's products, personas,
competitors, and team roster.

---

## Company Overview

**Acme** is a cloud platform for web development teams. It provides hosting,
CI/CD, serverless compute, and edge infrastructure optimized for frontend and
full-stack applications. Acme's core thesis: the best developer experience
wins. Teams that deploy faster, preview freely, and run logic at the edge
ship better products and move faster than teams locked into traditional cloud
infrastructure.

**GTM motion:** Product-led growth at the individual developer level, transitioning
to enterprise sales for teams requiring SSO, SLAs, audit logs, and custom contracts.

**Primary buyers:**
- Engineering Manager / Director of Engineering (budget authority + daily user)
- VP Engineering / CTO (enterprise deals, strategic partnerships)
- Frontend Lead / Staff Engineer (technical champion, often the initiator)
- Platform Engineering Lead (evaluating infrastructure fit)

---

## Product Catalog

### Core Platform

**Acme Sites (Hosting + CDN)**
- Global CDN with 100+ edge nodes
- Git-connected deployments (GitHub, GitLab, Bitbucket)
- Instant cache invalidation on deploy
- Atomic deploys — every deploy is immutable, rollback is instant
- Custom domains, HTTPS, redirects, headers out of the box
- Value: Eliminates DevOps overhead for deploying and serving web apps

**Deploy Previews**
- Automatic preview URL for every pull request and branch
- Shareable link for design/QA review before merge
- Collaborative comments on previews
- Value: Shortens review cycles, kills "works on my machine" problems

**Acme Functions (Serverless)**
- AWS Lambda-backed serverless functions, zero configuration
- Co-located with frontend code in the same repository
- Supports Node.js, Go, Rust
- Scheduled functions (cron), background functions (async)
- Value: Teams ship backend logic without managing servers or separate deployments

**Acme Edge Functions**
- Runs at the CDN edge, not in a central region
- Deno-based runtime (TypeScript/JavaScript)
- Sub-millisecond cold starts, globally distributed
- Use cases: A/B testing, auth, personalization, geo-routing, middleware
- Value: Low-latency compute without the complexity of regional infrastructure

**Acme Connect (Data Layer)**
- Aggregates content from multiple headless CMS, commerce, and data sources
- Unified GraphQL API over all connected sources
- Cache-aware: data invalidation tied to content changes
- Value: Solves the "too many APIs" problem in composable/headless architectures

**Acme Analytics**
- Server-side analytics (no client JS, not blocked by ad blockers)
- Real user data, not sampled
- Value: Accurate traffic data, especially for engineering + SEO teams

### Enterprise Capabilities

- **SSO / SAML** — Okta, Google Workspace, Azure AD integration
- **Audit Logs** — Full activity logging for compliance teams
- **Role-Based Access Control** — Fine-grained permissions by team
- **SLA** — 99.99% uptime SLA for enterprise tier
- **Custom Billing** — Annual contracts, invoicing, PO support
- **Private npm Registry** — Dependency management at scale
- **IP Restrictions / VPN** — Network-level access control

---

## Value Propositions by Persona

### Engineering Manager / Director of Engineering

- **Faster release cycles:** Deploy previews eliminate the back-and-forth between
  dev, QA, and design. PRs have live URLs before they're merged.
- **Less infra toil:** No more Nginx configs, S3 bucket policies, or CloudFront
  distributions to manage for frontend apps.
- **Rollback confidence:** Atomic deploys mean a bad deploy is one click from
  reversal. No scary Friday deploys.
- **Team velocity metric:** Most teams report 30-50% reduction in time from
  code-complete to production-ready.

### VP Engineering / CTO

- **Developer experience as a retention lever:** Engineers who use good tools
  stay longer and recruit better. Acme is consistently cited in "developer
  experience" survey as a preferred tool.
- **Platform consolidation:** Replace S3 + CloudFront + Lambda@Edge +
  CodePipeline with one integrated platform with a single pane of glass.
- **Edge strategy:** Run business logic at the edge without a separate edge
  compute team. Edge Functions are the same codebase as the rest of the app.
- **Vendor risk:** Open-source Acme toolchain (acme-cli, Build plugins)
  avoids lock-in at the tooling layer.

### Frontend Lead / Staff Engineer

- **Best-in-class DX:** CLI, Git integration, instant previews, local
  dev server that mirrors production — the toolchain engineers actually like.
- **Framework-native:** First-class support for Next.js, Astro, Remix, Gatsby,
  SvelteKit, Nuxt. Not an afterthought.
- **Edge Functions as middleware:** Replace a whole class of infrastructure
  problems (geo-routing, auth, personalization) with a few lines of TypeScript.
- **Open ecosystem:** Works with any headless CMS, any ecommerce backend, any API.

---

## Competitors

### Vercel ← Primary

**Their positioning:** "The platform for frontend teams." Almost identical surface
area. Strong Next.js alignment (they created Next.js).

**Their genuine strengths:**
- Next.js is developed by Vercel — first-class support, newest features earliest
- Strong brand recognition in React/Next.js community
- Fluid DX for Next.js teams specifically
- ISR (Incremental Static Regeneration) deeply integrated

**Where we win:**
- Framework-agnostic: Acme works equally well for non-Next.js stacks
- More open ecosystem: Acme doesn't own a framework, reducing lock-in concern
- Better CMS/headless support via Acme Connect
- Stronger enterprise motion: more mature RBAC, audit logs, enterprise support
- Functions: Acme's serverless functions are simpler to co-locate and reason about
- Price predictability: Vercel's pricing model (per-request for some features) can
  surprise teams at scale

**Objection we hear:** "Our team is all-in on Next.js, Vercel feels like the natural choice."
**Response:** Framework expertise matters; platform lock-in matters more at scale. Acme
fully supports Next.js (including SSR, ISR, Edge Middleware) and your stack will evolve —
you want a platform that evolves with it, not one tied to a single framework vendor.

---

### AWS Amplify ← Incumbent Displacement

**Their positioning:** AWS-native frontend hosting for teams already in the AWS ecosystem.

**Their genuine strengths:**
- Deep AWS integration: IAM, Cognito, AppSync, DynamoDB — all native
- Cost: Very cheap for small workloads inside AWS Free Tier
- Enterprise procurement: Already on AWS contract, no new vendor to approve

**Where we win:**
- DX: Amplify is notoriously harder to configure and debug. Acme is consistently
  rated higher for developer experience
- Deploy Previews: Amplify's preview URLs are slower to generate and harder to share
- Edge: Acme Edge Functions are significantly easier to write and reason about than
  Lambda@Edge or CloudFront Functions
- Support: AWS enterprise support is generalist; Acme support is platform-specific

**Objection we hear:** "We're an AWS shop, adding another vendor is friction."
**Response:** Acme runs on AWS under the hood. It's not a competing cloud — it's the
best interface for deploying your frontend on top of your existing AWS investment.
Your backend, auth, and data stays in AWS. Acme just removes the DevOps complexity
from the frontend layer.

---

### Cloudflare Pages ← Price Competitor

**Their positioning:** "Deploy faster, for less." Cloudflare's global network + free tier
is aggressive.

**Their genuine strengths:**
- Price: Generous free tier, bandwidth included
- Performance: Cloudflare's edge network is among the best globally
- Workers integration: If teams use Cloudflare Workers, Pages is natural

**Where we win:**
- Feature completeness: Acme Functions, Connect, Deploy Previews are more mature
- DX: Cloudflare Pages DX is more bare-metal; Acme has more batteries included
- Enterprise: Cloudflare's enterprise sales motion is primarily network/security, not frontend
- Ecosystem: Acme has more integrations with CMSes, ecommerce platforms, auth providers

**Objection we hear:** "Cloudflare is free for us right now."
**Response:** Free is great for side projects. At team scale — with multiple contributors,
preview environments, enterprise auth, and uptime SLAs — the economics shift. What's the
cost of a 30-minute deploy outage, a merge that doesn't preview correctly, or a compliance
audit gap?

---

### Render / Railway ← Simpler Alternative

**Their positioning:** Simple full-stack deployments. Targeted at developers who want
something between Heroku and AWS.

**Where we win:** Acme is purpose-built for frontend and composable architectures.
Render/Railway are more backend-first. For teams with complex frontend requirements
(multi-region edge, headless CMS, heavy JS frameworks), Acme is the right tool.

---

## Team Roster (Demo)

Adjust this to match your actual team. The pipeline uses these names to distinguish
seller speakers from prospect speakers in transcripts.

| Name | Role | Abbreviation |
|------|------|-------------|
| Sarah Chen | Account Executive | AE |
| Marcus Webb | Solutions Engineer | SE |
| Jordan Reeves | Account Executive | AE |
| Priya Nair | Solutions Engineer | SE |
| Alex Torres | Customer Success Manager | CSM |

---

## Typical Deal Profile

| Segment | ARR Range | Seats | Sales Cycle | Primary Buyer |
|---------|-----------|-------|-------------|---------------|
| Self-serve / Startup | <$5K | 1-5 | None (PLG) | Individual dev |
| Growth | $5K-$50K | 5-25 | 30-60 days | Eng Manager |
| Enterprise | $50K-$500K+ | 25-500+ | 60-120 days | VP Eng / CTO |

**Common triggers for enterprise evaluation:**
- Hitting limits of self-serve plan (build minutes, bandwidth, team members)
- SOC 2 / compliance requirement surfaces
- SSO requirement from IT/security
- Platform consolidation initiative
- New VP Eng / CTO reviewing the stack
- Competitive loss to Vercel triggering a re-evaluation
