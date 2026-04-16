# Paid Media — Deep Research Template

> **Inherits from:** `~/.claude/templates/deep-research-competitive-landscape.md` (primary) or `deep-research-technical-reference.md` (for platform-feature evaluations)
>
> **Use when:** researching paid-media competitive landscape, platform feature changes, creative strategy benchmarks, channel feasibility, or attribution/measurement methodology.

---

## Use cases

- **Competitive paid-media teardown** — how is a specific competitor running paid? (ad library analysis, creative strategy, offer architecture)
- **Platform feature evaluation** — iOS 14.5 / SKAN4 / Meta Advantage+ / Google PMax / TikTok Spark Ads impact on a specific account profile
- **Channel feasibility** — should we launch TikTok / CTV / Reddit / Pinterest? Research before a budget commitment
- **Creative strategy benchmarks** — what's working for category leaders in creative format / hook patterns / UGC-vs-produced?
- **Attribution-vendor evaluation** — Northbeam vs. Rockerbox vs. Triple Whale vs. build-in-house
- **Agency shortlist** — evaluating agencies before an RFP

## Opinionated source priorities

**Prioritize:**

- **Meta Ad Library + Google Ads Transparency + TikTok Ad Library + LinkedIn Ad Library** — all free; these are primary-source competitive ad data
- **Platform product blogs** — Meta for Business, Google Ads, TikTok for Business, LinkedIn Marketing Solutions — for feature changes and policy updates
- **Case studies from the platforms themselves** — often over-indexed on the platform's own narrative, but useful for scale benchmarks
- **Earnings call mentions** — Meta, Google, Snap, Pinterest, TikTok-parent (ByteDance private, but Alphabet calls mention YouTube/Google Ads metrics)
- **Ecommerce-specific analysts** — Triple Whale blog, Northbeam blog, Rockerbox blog, Measured blog, Haus blog — for attribution-specific methodology
- **Operator podcasts** — 2X eCommerce, Operators Podcast, Honest Ecommerce, DTC POD, Shopify Masters, Lenny's (PLG SaaS)
- **Industry reports** — AppLovin / Adjust / Appsflyer (app ads); eMarketer / Insider Intelligence (B2C); SaaStr (B2B SaaS)

**De-prioritize:**

- Twitter/X takes without operator credentials
- Platform-rep advice (always optimize for platform ROAS, never blended)
- Generic "top 10 Facebook ad tricks" listicles
- AI-generated LinkedIn thought-leadership

## Question-set specializations by use case

### For competitive teardown:

1. What creative formats is the competitor running? (feed, story, reel, carousel, UGC, produced)
2. What offer architecture do they use? (price anchor, discount ladder, bundle, subscription)
3. What landing page pattern? (direct-to-PDP, category, quiz/funnel, long-form advertorial)
4. What audience signals can we infer from creative + ad library activity? (lookalike sources, interest stacks, retargeting aggressiveness)
5. What pixel / attribution setup is visible? (server-side, CAPI, 3rd-party)
6. What's their scale / budget band inferable from ad-library impression tiers?
7. What creative production cadence — how many new ads per week?
8. Where are they under-invested that we could exploit?

### For platform-feature evaluation:

Use the `deep-research-technical-reference.md` archetype. Focus specifically on:

1. What does the feature actually do at the auction / delivery level?
2. What's the claimed uplift vs. independent measurement?
3. What's the data / setup prerequisite?
4. Who's tested it with published results?
5. What are the failure modes / rollback criteria?
6. What's the migration cost from the prior feature?

### For channel feasibility:

1. Category / audience overlap — are your buyers on this channel? Proof?
2. Creative fit — does your current creative library work, or is a full production swing required?
3. Measurement / attribution — does the channel have first-party measurement at useful granularity?
4. Scale ceiling — at full scale, how much of your CAC-target spend can this channel absorb?
5. Brand-safety constraints — any category / regulatory issues?
6. Case studies from peer brands — who's launched and at what CAC?

### For attribution-vendor evaluation:

Use the `deep-research-technical-reference.md` archetype for vendor comparison. Specifically:

1. MTA, MMM, or both?
2. Data sources — which platforms + warehouse integrations?
3. Modeling approach — rules-based, probabilistic, black-box ML?
4. Refresh cadence — daily, weekly, quarterly?
5. Reconciliation — do they cross-validate against bank revenue?
6. Pricing — implementation + monthly + data-sources add-on?
7. Implementation time — realistic weeks-to-value?
8. Customer overlap — peers of your stage using it?

## KB integration

Before running a paid-media research brief:

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — if the question touches MMM, incrementality, mROAS, or Hill curves, the answer may already be in 20 compiled articles
- `{{KNOWLEDGE_BASE_ROOT}}/amazon-ads/wiki/_index.md` — if Amazon PPC is in scope

Cite KB hits in the Methodology section of the deliverable.

## Example filled-in briefs

- "Research the Meta + Google paid landscape for premium outdoor-gear brands $10M-$50M as of {{date}} — competitor set: REI, Backcountry, Huckberry, Filson, Mountain Hardwear, Outerknown"
- "Research SKAN4 impact on iOS-first DTC brands and the current best-practice measurement stack as of {{date}}"
- "Research TikTok Shop + TikTok Ads combined strategy for beauty brands $5M-$30M as of {{date}}"
- "Research current MMM vendor landscape ($40-$150K annual tier) for ecommerce brands $30-$100M as of {{date}} — candidates: Haus, Measured, Prescient, Recast, MMM.co, in-house build"
- "Research incrementality-testing methodology for geo-holdout-restricted brands (no geo-SKU variance) as of {{date}}"
