# Pricing / Promotion Program — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** pricing strategy overhaul, promotion architecture redesign, discount rationalization, pricing-tier structure, or promotional calendar buildout.

---

## Who this is for

CMOs, VPs of growth, CFOs, ecommerce leaders at DTC / subscription / B2B SaaS / consumer brands. Programs span 8-16 weeks for pricing redesign or promotional architecture; longer for category-level repricing.

## Opinionated defaults

### Pricing philosophy

- **Pricing is positioning.** A price is a message: premium price signals quality, discount price signals value, mid-price signals balance. Drift between pricing + positioning creates confusion.
- **Aggressive discounting is repositioning.** A "premium" brand that discounts 30%+ regularly has repositioned itself as promotional, regardless of marketing language.
- **Price elasticity is brand-specific; measure, don't assume.** General rules of thumb are directional; your category + brand + customer has unique curves.
- **Bundle pricing: good for AOV, watch margin.** Unbundling hides price increases; bundling creates perceived value — both have tradeoffs.

### Promotion cadence

- **Monthly calendar, not ad-hoc.** Every promotion planned 30+ days in advance with clear purpose.
- **Max 1 promotion active at a time** (except calendar moments: Black Friday, Memorial Day, etc.)
- **No stacking unless explicitly designed** — stacking destroys margin + trains customers to wait
- **Promotion cycle:** launch promo → 7-14 day window → post-mortem → next planning

### Promotion types

- **Site-wide discount:** rare; blunt instrument
- **Category / collection:** targeted, preserves brand-level pricing
- **Tiered (spend $X get Y%):** AOV-driver, margin-preserving
- **BOGO / bundle:** inventory-clearing, AOV-building
- **Gift-with-purchase (GWP):** margin-preserving perceived-value
- **Subscribe-and-save:** retention-focused, predictable margin hit
- **Flash sale:** time-limited urgency, don't overuse
- **Loyalty-exclusive:** rewards existing customers, non-cannibalizing

### Margin discipline

- **Set a minimum gross margin % for promotions.** No promotion below X% GM.
- **Track promotional GM separately from list-price GM** — they're different economics
- **Promotional revenue share target: 15-30%** of total; below = under-promotion, above = over-dependent
- **Full-price CVR vs. promotional CVR:** track separately; if full-price CVR is collapsing, you're conditioning customers to wait

### Pricing strategy patterns

- **Price increases:** do quietly, communicate selectively; test impact carefully
- **Price decreases:** communicate loudly, make obvious — but be certain the economics work
- **Tier structure:** good / better / best — entry tier for acquisition, mid-tier for volume, top tier for margin
- **Freemium → paid:** conversion benchmark 2-5% free-to-paid typical
- **Value-based pricing > cost-plus** — anchor to what customer saves / gains, not what product costs

### Discount depth norms (starting points; category-dependent)

- **First-time buyer: 10-20%** (more devalues brand)
- **Subscribe-and-save: 10-15%**
- **Bundle: 15-25% on bundle vs. individual purchase**
- **Loyalty tier exclusive: 10-25%**
- **Flash sale: 20-40%** (limited duration + quantity)
- **Black Friday / Cyber Monday: 20-40%** (higher = margin destruction)
- **Clearance: 40-70%** (true inventory offload, rare)

### Pricing-test methodology

- **A/B test pricing with sample-size discipline** — same product at 2+ prices to measure elasticity
- **Geographic / audience-targeted pricing tests** — if infrastructure supports
- **Pre/post measurement:** measure lift + margin vs. historical
- **Holdout groups for subscription price changes** — grandfather vs. migrate

### MAP policy (for multi-channel brands)

- **MAP (Minimum Advertised Price) policy required** if you have retail + DTC + marketplace
- **Enforce aggressively** — MAP violations destroy partner relationships
- **Policy documented + distributed** to affiliates + retailers + marketplace sellers

## Step 0 — Interview question additions

1. **Current pricing structure** — tiers, price points, bundles
2. **Current promotional cadence** — how often, what depth, what format
3. **Revenue mix by price tier** — where's the concentration?
4. **Promotional revenue share** — what % of revenue from promotions?
5. **Margin discipline** — gross margin by price tier; by promotion type
6. **Last price change** — when, what, measured impact?
7. **Price elasticity data** — any measurement available?
8. **Competitor pricing intelligence** — who's priced where?
9. **Channel-specific pricing** — retail MAP, DTC, marketplace coordination?
10. **Loyalty tier pricing** — exclusive rates, member discounts?
11. **Legal / regulatory constraints** — MAP enforcement, price-fixing considerations?

## Step 2 — Milestone template (12-week program)

```markdown
### M1 — Pricing Audit + Research (week 1-3)
- Deliverable: current-state pricing map; competitor pricing analysis; customer research on willingness-to-pay
- Validation: pricing map + competitor benchmarks + customer data in hand
- Target: end of week 3

### M2 — Strategy + Architecture (week 3-5)
- Deliverable: pricing architecture (tiers, bundles, promotional structure); MAP policy; monthly promotional calendar template
- Validation: architecture aligned with positioning; legal-reviewed
- Target: end of week 5

### M3 — Promotional Calendar Q1-Q2 (week 5-8)
- Deliverable: detailed promotional calendar with purpose + expected margin + expected lift for each
- Validation: calendar approved; inventory + creative coordinated
- Target: end of week 8

### M4 — A/B Testing + Measurement (week 6-10)
- Deliverable: pricing A/B tests live; promotion measurement framework
- Validation: tests running with proper stats; measurement dashboards built
- Target: end of week 10

### M5 — Rollout + Communication (week 8-12)
- Deliverable: price changes implemented; promotional cadence active; team + customer communication
- Validation: no negative PR / major customer complaint; revenue + margin trending
- Target: end of week 12

### M6 — Ongoing Rhythm + Review (week 12+)
- Deliverable: monthly promotional review; quarterly pricing review; annual strategy refresh
- Validation: program self-operates; discipline maintained
- Target: ongoing
```

## Step 3 — Critical mental model

> **Every promotion teaches customers to wait.**
>
> The compound effect of frequent discounting is deferred purchasing — customers learn that "full price" is a temporary state between sales and optimize accordingly. This shows up as: collapsing full-price conversion rate, shortening time-to-next-sale in customer behavior, increasing discount-depth expectation.
>
> Brands with strong pricing discipline (Apple, Patagonia at their peak) almost never discount and maintain premium positioning for decades. Brands that have discounted into the ground (many specialty retail) cannot reverse without painful customer pushback.
>
> The rule: every promotion should have a clear purpose (inventory clearing, acquisition, retention, seasonal moment). No promotions for "stimulating sales this month" without plan for what it does to next month.

## Step 4 — Domain validators

- **Promotional calendar documented** 30+ days in advance
- **Promotional revenue share tracked** — within target band
- **Gross margin by promotion type** — meeting minimum threshold
- **Full-price CVR vs. promotional CVR** — tracked separately, compared
- **MAP compliance** — violations detected + remediated
- **Price-change impact measured** — pre/post or A/B

## Step 8 — Working protocol additions

- **Never run simultaneous promotions without intent** — cannibalization + margin destruction
- **Never allow stacking** unless explicitly designed
- **Never discount below minimum GM**
- **Never change pricing without measuring**
- **Always document promotion purpose** before launch
- **Always post-mortem** promotions within 14 days
- **Always track full-price CVR trend** — canary for over-promotion

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — elasticity + response modeling
- `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/wiki/_index.md` — retailer pricing + MAP patterns
- `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/wiki/_index.md` — competitor pricing research

## Common example fills

- **"Rationalize promotional calendar for $60M DTC brand — current 18 promotions/year, revenue 38% from promos; reduce to 12 with higher impact per"**
- **"Tier restructure for B2B SaaS — add enterprise tier, reprice mid-tier, keep starter flat"**
- **"Pricing increase execution — 8% across core line; communication + grandfathering + measurement"**
- **"Holiday promotion architecture — Black Friday + Cyber Monday + December calendar"**
- **"MAP policy rollout — coordinate DTC + retail + Amazon + affiliate after years of drift"**

## Hand-off

After bootstrap, use `~/.claude/templates/growth-ecommerce/pricing-promotion/resumption.md`.
