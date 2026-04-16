# Growth & Ecommerce Template Library

Specialized templates for 23 high-ROI growth-marketing and ecommerce-operator workstreams. Every template is an *opinionated diff* on top of the general-purpose masters in `~/.claude/templates/` — they inherit the discipline and add domain expertise.

**Tier 1 (core 8 domains):** paid media, lifecycle, CRO, attribution/MMM, Amazon, retention/LTV, SEO/content, launch/GTM.

**Tier 2 (next 6 domains):** influencer/creator, subscription/loyalty, brand-positioning, wholesale/retail, geo-expansion, martech-stack.

**Tier 3 (additional 9 domains):** B2B lead generation, event marketing, community/ambassador, offline media, PR/earned media, sustainability/ESG, affiliate, UGC/reviews, pricing/promotion.

## Quick-start

1. Identify your workstream from the decision tree
2. Read the domain-specific README (in each subfolder)
3. Run the general-purpose master template first (`~/.claude/templates/session-kickoff-bootstrap.md` / `session-kickoff-prompt.md` / `deep-research-*.md`)
4. Apply the domain specialization overrides

## Placeholder conventions

Templates reference `{{KNOWLEDGE_BASE_ROOT}}` and `{{WORK_VAULT_ROOT}}` as placeholders for personal infrastructure. Substitute with your own paths (Obsidian vault, Notion workspace, local wiki, Confluence space) or delete references if you don't maintain a KB. The templates still work without a KB — they just skip the KB-integration step.

## Decision tree — pick your domain

```
What workstream is this project?

— TIER 1 —
Paid media / performance marketing              → paid-media/
Email / SMS / push / lifecycle orchestration    → lifecycle/
Landing pages / on-site CRO / A/B testing       → cro/
Attribution / MMM / measurement rebuild         → attribution-mmm/
Amazon listings / PPC / marketplace             → amazon/
Retention / LTV / cohort optimization           → retention-ltv/
SEO / content program / organic growth          → seo-content/
New product launch / GTM                        → launch-gtm/

— TIER 2 —
Influencer / creator / ambassador program       → influencer-creator/
Subscription program or loyalty program         → subscription-loyalty/
Rebrand / positioning refresh / new brand       → brand-positioning/
Wholesale / retail channel expansion            → wholesale-retail/
International / geographic expansion            → geo-expansion/
Martech stack audit / consolidation / rebuild   → martech-stack/

— TIER 3 —
B2B lead generation (ABM, SDR, inbound)         → b2b-leadgen/
Events — trade shows, webinars, conferences     → event-marketing/
Community / ambassador network program          → community-ambassador/
Offline media — DM, OOH, CTV, TV, podcast       → offline-media/
PR / earned media / thought leadership          → pr-earned-media/
Sustainability / ESG / B-Corp / climate         → sustainability-esg/
Affiliate marketing (network or in-house)       → affiliate/
UGC / reviews / social proof program            → ugc-reviews/
Pricing strategy / promotional architecture     → pricing-promotion/
```

## The 23 domains × 3 templates each (69 templates total)

### Tier 1

| Domain | Scope | Primary KB |
|---|---|---|
| **paid-media/** | Meta, Google, TikTok, programmatic paid | `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/`, `{{KNOWLEDGE_BASE_ROOT}}/amazon-ads/` |
| **lifecycle/** | Email, SMS, push — welcome, cart, post-purchase, win-back | (retail-sales-enablement) |
| **cro/** | Landing page, checkout, on-site optimization | `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/` |
| **attribution-mmm/** | MTA → MMM, incrementality, measurement | `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/` |
| **amazon/** | Listings, PPC, account health, Seller Central | `{{KNOWLEDGE_BASE_ROOT}}/amazon-ads/`, `{{KNOWLEDGE_BASE_ROOT}}/amazon-product-launches/`, `{{KNOWLEDGE_BASE_ROOT}}/amazon-developer-tools/` |
| **retention-ltv/** | Cohort analysis, LTV, churn intervention | (mmm + product-research KBs) |
| **seo-content/** | Keyword clusters, content velocity, E-E-A-T | `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/` |
| **launch-gtm/** | New product launches, retail + DTC parallel | `{{KNOWLEDGE_BASE_ROOT}}/amazon-product-launches/`, `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/` |

### Tier 2

| Domain | Scope | Primary KB |
|---|---|---|
| **influencer-creator/** | Seeding, paid, whitelisting, ambassador | `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/`, `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/` |
| **subscription-loyalty/** | Subs, loyalty programs, referral, VIP | `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/`, `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/` |
| **brand-positioning/** | Rebrand, positioning, architecture | `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/`, `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/` |
| **wholesale-retail/** | Specialty, mass, club retail expansion | `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/` |
| **geo-expansion/** | UK/EU/CA/AU/APAC international | `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/`, `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/` |
| **martech-stack/** | Tool audit, consolidation, warehouse + CDP | `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/`, `{{KNOWLEDGE_BASE_ROOT}}/ai-engineering/` |

### Tier 3

| Domain | Scope | Primary KB |
|---|---|---|
| **b2b-leadgen/** | ABM, outbound SDR, inbound demand, webinars | `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/`, `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/` |
| **event-marketing/** | Trade shows, conferences, webinars, field events | `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/`, `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/` |
| **community-ambassador/** | Discord/Circle/Slack, ambassador tiers | `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/`, `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/` |
| **offline-media/** | Direct mail, OOH, CTV, TV, radio, podcast | `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/`, `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/` |
| **pr-earned-media/** | Media relations, thought leadership, crisis | `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/`, `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/` |
| **sustainability-esg/** | B-Corp, climate reporting, supply chain | `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/`, `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/` |
| **affiliate/** | CJ/Impact/Rakuten/in-house, creator commerce | `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/`, `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/` |
| **ugc-reviews/** | Review solicitation, UGC rights, response | `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/`, `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/` |
| **pricing-promotion/** | Pricing strategy, promotional architecture | `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/`, `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/` |

Each domain folder contains three files:

- `bootstrap.md` — session 1 of a multi-session engagement
- `resumption.md` — sessions 2+
- `deep-research.md` — research brief template

## Opinionated defaults — what's baked in

Every domain template includes non-negotiable-by-default rules drawn from industry best-practice. Override with explicit reason in `Documentation.md` — they're starting points, not gospel.

**Tier 1 highlights:**
- **Paid media:** No stop-start within learning phase · MER primary, ROAS diagnostic · ≤20% scale/72h
- **Lifecycle:** Welcome = 6 emails / 14 days · Cart = T+1h/T+1d/T+3d · Revenue/message primary
- **CRO:** 2wk OR 10K visitors OR 200 conv · 5% MDE minimum · 10% global control holdout
- **Attribution:** MTA + MMM parallel 90+ days · Quarterly MMM rebuild · Hill curves
- **Amazon:** 10+ reviews + 4.0 rating + 30+ days inventory before PPC scale · TACoS 10-15%
- **Retention:** Windowed LTV · LTV:CAC ≥ 3:1 by M12 · Segment first
- **SEO:** 2-4 articles/week · E-E-A-T signals · 6mo minor / 18mo major refresh
- **Launch:** 90-day window · Day-30 gate · 60+ days inventory

**Tier 2 highlights:**
- **Influencer:** Seed before paid · Whitelist for amplification · FTC #ad · UTMs per creator
- **Subscription:** Dunning day-1/3/7/14 · Voluntary/involuntary split · Recovery 40-60%
- **Brand:** Memory structure > design novelty · 5-7 year rebrand horizon · Internal first rollout
- **Wholesale:** MAP before entry · 5-15% chargeback budget · Category review calendar critical
- **Geo:** Local payment methods = 30-50% conversion · Localization ≠ translation
- **Martech:** Consolidate don't expand · Warehouse-as-source-of-truth · Kill before add

**Tier 3 highlights:**
- **B2B leadgen:** ICP first volume second · Pipeline coverage 3-5× target · Cadence completion 80%+
- **Event marketing:** 30/20/50 split pre/during/post · Events are accelerators not generators
- **Community:** Community ≠ marketing · 5-15% posting rate healthy · Real communities have disagreement
- **Offline media:** Brand + assist channel · Incrementality testing required · 6-12mo compound
- **PR:** Credibility bank that compounds · Story not pitch · No AVE
- **Sustainability:** Claim 20% less, do 20% more · Third-party > self-declaration · Scope 3 not optional
- **Affiliate:** Partnership not channel · Top 20 affiliates = 80% revenue · No payment for fraud
- **UGC/Reviews:** Never pay for reviews · Velocity > count · Response within 48h on 1-3 star
- **Pricing:** Pricing is positioning · Every promo trains waiting · 15-30% promo revenue share target

## KB integration

Templates link to relevant KB wikis from `{{KNOWLEDGE_BASE_ROOT}}/HOME.md`. When a template cites a KB article, intent is:

1. Template encodes the high-level opinionated default
2. KB article has detailed reasoning + reference
3. Agent reads both during execution

Missing KB references flag in `Documentation.md` for later compilation.

## File organization

```
~/.claude/templates/growth-ecommerce/
├── README.md                          # ← you are here
├── paid-media/             Tier 1
├── lifecycle/              Tier 1
├── cro/                    Tier 1
├── attribution-mmm/        Tier 1
├── amazon/                 Tier 1
├── retention-ltv/          Tier 1
├── seo-content/            Tier 1
├── launch-gtm/             Tier 1
├── influencer-creator/     Tier 2
├── subscription-loyalty/   Tier 2
├── brand-positioning/      Tier 2
├── wholesale-retail/       Tier 2
├── geo-expansion/          Tier 2
├── martech-stack/          Tier 2
├── b2b-leadgen/            Tier 3
├── event-marketing/        Tier 3
├── community-ambassador/   Tier 3
├── offline-media/          Tier 3
├── pr-earned-media/        Tier 3
├── sustainability-esg/     Tier 3
├── affiliate/              Tier 3
├── ugc-reviews/            Tier 3
└── pricing-promotion/      Tier 3
```

## Coverage summary

**Total at this point in `~/.claude/templates/`:**

- 6 general-purpose masters (bootstrap + resumption + 4 deep-research)
- 23 specialized domain folders × 3 templates = 69 specialized templates
- 1 top-level README, 1 growth-ecommerce README

**76 markdown files + 76 docx files = 152 total template files.**

Full coverage of ecommerce + growth-marketing operational workstreams at the level of opinionated defaults + KB integration + inheritance from general-purpose masters. Usable by any operator, growth marketer, or agency in any B2B / B2C / DTC / subscription / marketplace context.
