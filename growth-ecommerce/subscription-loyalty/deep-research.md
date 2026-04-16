# Subscription / Loyalty — Deep Research Template

> **Inherits from:** `~/.claude/templates/deep-research-competitive-landscape.md` or `deep-research-technical-reference.md`

---

## Use cases

- **Subscription platform evaluation** — Recharge / Bold / Shopify Subscriptions / Smartrr / Ordergroove / Stay AI / custom
- **Loyalty platform evaluation** — LoyaltyLion / Yotpo Loyalty / Smile / Stamped / Rise.ai / Friendbuy (referral-focused)
- **Category subscription benchmarks** — churn, retention, LTV, take rate in your vertical
- **Loyalty program ROI research** — measured incremental revenue at peer brands
- **Referral program benchmarks** — referral share of new customers by category
- **Competitor subscription teardown** — specific competitor's subscription offer, economics, friction

## Opinionated source priorities

**Prioritize:**

- **SEC filings for public subscription companies** — detailed cohort data in S-1s, 10-Ks (Warby Parker, Allbirds, Figs, Blue Apron, HelloFresh, Disney+, Netflix for methodology)
- **Zuora Subscription Economy Index** — aggregate subscription benchmarks
- **Recharge data reports** — published category benchmarks for Shopify-ecosystem subscriptions
- **Loyalty research firms** — Clarus Commerce, LoyaltyLion reports
- **Operator podcasts on specific programs** — operators who've launched / scaled / killed programs publish postmortems
- **Stripe guidance on dunning** — Stripe Smart Retries documentation + published recovery rates

**De-prioritize:**

- Vendor-published ROI claims without brand attribution
- Generic "why subscriptions work" content
- Course-seller loyalty-program content

## Question-set specializations

### For subscription platform evaluation:

1. Subscription models supported — S&S, committed, flex, box, hybrid?
2. Dunning sophistication — Smart Retries, payment-method-update UX, communication flows
3. Portal UX — customer self-serve for skip/swap/pause
4. Integration depth — Shopify, ERP, warehouse, customer data
5. Analytics + cohort reporting — native or bolt-on?
6. Pricing — % of subscription revenue + monthly minimums
7. Migration cost — moving from another platform
8. Scale ceiling — works at 10K subs or 500K?

### For loyalty platform evaluation:

1. Program types — points, tiers, referral, VIP, experiential combined?
2. Measured ROI at published case-study brands (critically read)
3. Integration depth — Shopify, Klaviyo, review platform, subscription platform
4. Ownership of member data — portable if you switch?
5. Pricing — per-member, per-transaction, flat tier
6. Launch time-to-value — realistic weeks
7. Exit cost — migration / retirement path

### For category benchmarks:

1. Subscription take rate — % of customers who subscribe in your category
2. Cohort retention curves — M1, M3, M6, M12 benchmarks
3. Voluntary vs. involuntary churn ratio
4. Skip / pause rate — % of subscribers using these features
5. Pricing structures — standard discount depth in category
6. Loyalty program adoption — % of category leaders running programs; what types

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — LTV modeling + retention-curve analysis applies directly
- `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/wiki/_index.md` — VIP + tier design patterns

## Example filled-in briefs

- "Evaluate Recharge vs. Stay AI vs. Smartrr vs. Ordergroove for $40M DTC brand launching subscription — feature parity, pricing, dunning quality, migration complexity"
- "Research subscription benchmarks for premium CPG beauty ($30-$80 AOV) — take rate, M3 retention, M12 retention, typical discount depth"
- "Research measured ROI of loyalty programs at DTC scale ($20M-$100M revenue) — which programs generate incremental revenue vs. function as discount theater"
- "Research referral program benchmarks across DTC categories — referral share of new customers, dual-sided incentive structures, fraud rates"
- "Teardown competitor subscription offering — $50M DTC coffee brand's S&S program — economics, friction, cancellation flow, skip/pause adoption"
- "Research dunning recovery benchmarks by industry — what's a 'good' recovery rate for ecom subscriptions vs. SaaS?"
