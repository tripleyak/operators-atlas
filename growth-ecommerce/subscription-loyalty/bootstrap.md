# Subscription / Loyalty Program — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** launching or overhauling a subscription program (subscribe-and-save, committed, box) or loyalty program (points, tiers, referral, VIP).

---

## Who this is for

Growth / retention / ecommerce leaders at DTC / CPG / consumer brands launching subscription or loyalty for the first time, or overhauling an underperforming program. Subscription programs: 12-16 weeks to launch + ongoing iteration. Loyalty programs: 8-12 weeks to launch + 6+ months to mature.

## Opinionated defaults

### Subscription model choice

- **Subscribe-and-Save (discount-for-repeat):** default for CPG replenishables (coffee, skincare, pet food)
- **Committed subscription (locked duration):** only with compelling value (e.g., curation, exclusivity)
- **Flex (skip/swap/pause freely):** highest LTV model but requires pricing power; churn hides if not measured
- **Subscription box (curated):** highest acquisition cost, hardest to scale; only for brands with strong creative

### Subscription measurement

- **Monthly active subscribers as primary metric**
- **Voluntary churn (cancel) vs. involuntary (payment fail) separated** — different interventions
- **Net retention:** (active subs month-end) / (active subs month-start); report monthly
- **Cohort retention curves** — monthly cohorts; retention measured at M1 / M3 / M6 / M12

### Dunning / payment recovery

- **Failed-payment retry schedule:** Day 1 / Day 3 / Day 7 / Day 14 (Stripe's Smart Retries or equivalent)
- **Recovery target: 40-60% of involuntary churn**
- **Communication: email + SMS at each retry;** gentle tone, not collections
- **Payment method update flow:** one-click easy; the #1 recovery lever

### Loyalty program design

- **Points-to-value ratio: typical 1¢ per point** (10,000 points = $100); higher dilutes perceived value
- **Earning rate: 1-2% of spend typical;** higher for VIP tier
- **Tier design:** 3-4 tiers; thresholds calibrated so most engaged customers reach tier 2
- **Never launch loyalty without exit plan** — retiring a loyalty program is operationally expensive and reputation-damaging
- **Measure ROI against incremental revenue, not gross revenue** — loyalty must create new spend, not discount existing

### Referral programs

- **Dual-sided incentive:** referrer gets X, referee gets Y — both should be meaningful
- **Payout trigger:** first purchase by referee, not signup (prevents fraud)
- **Fraud detection:** same IP, same device, same email pattern = review
- **Measurement:** new-customer referral CAC vs. paid channel CAC; loyalty ROI includes referral performance
- **Promote referral at peak-delight moments:** post-purchase, after review, after positive support interaction

### VIP / top-tier discipline

- **Quarterly touch minimum** for top-tier VIPs
- **Early access, exclusive product, private events** — experience beats discount
- **VIP tier should be <5% of customer base** — dilution hurts positioning

## Step 0 — Interview question additions

### For subscription:

1. **Product fit for subscription** — replenishable? Curated? Exclusive? Service-like?
2. **Current non-subscription baseline** — repeat rate, average order gap
3. **Infrastructure** — Recharge / Bold / Shopify subs / Stripe / custom?
4. **Billing cadence options** — monthly / 2-month / quarterly / custom?
5. **Discount offered for subscription** — 10% / 15% / 20% typical; what's the plan?
6. **Skip/swap/pause policy** — strict or flexible?
7. **Cancellation flow** — friction-full (phone only) or friction-free (self-serve)?

### For loyalty:

8. **Current loyalty state** — program running, past program, or greenfield?
9. **Brand positioning fit** — premium brands need experiential tiers, mass brands need points
10. **Integration depth** — Shopify + Klaviyo + review platform + subscription platform?
11. **Tool evaluation** — LoyaltyLion / Yotpo / Smile / Stamped / custom?
12. **Referral component** — included in loyalty or separate?

## Step 2 — Milestone template (subscription 16 weeks)

```markdown
### M1 — Economics + Infrastructure Audit (week 1-2)
- Deliverable: LTV model for subs vs. non-subs; churn benchmark; tool selection
- Validation: economics model quantified; infrastructure path decided
- Target: end of week 2

### M2 — Subscription Design (week 2-4)
- Deliverable: cadence options; discount structure; skip/swap policy; pricing model
- Validation: stakeholder sign-off; legal / T&C approved
- Target: end of week 4

### M3 — Technical Build + Integration (week 4-8)
- Deliverable: subscription live on platform; billing, dunning, skip/pause/swap flows working
- Validation: test subs through every path; end-to-end tested
- Target: end of week 8

### M4 — Soft Launch + First Cohort (week 8-10)
- Deliverable: existing customer offer; first 100-500 subs acquired
- Validation: M1 retention tracked; cancellation reasons tagged
- Target: end of week 10

### M5 — Acquisition Expansion (week 10-14)
- Deliverable: subscription offer on acquisition paths (new customer + existing email)
- Validation: sub share of new customers trending to target
- Target: end of week 14

### M6 — Optimization + Reporting Cadence (week 14-16)
- Deliverable: cohort dashboard; monthly review rhythm; dunning optimization
- Validation: program self-operates; reporting auto-refreshes
- Target: end of week 16
```

## Step 3 — Critical mental model

> **Subscriptions and loyalty are economic contracts, not marketing tactics.**
>
> A subscription offers a better price in exchange for a commitment — the customer trades optionality for savings, and the brand trades margin for LTV certainty. A loyalty program offers future value in exchange for present behavior — the customer trades some purchase flexibility for accumulated reward value.
>
> Programs fail when this contract is one-sided:
> - Subscription with aggressive discount + generous cancellation = brand loses margin and customer has no real commitment
> - Loyalty with cheap rewards + high earning rate = points become liability without behavior change
>
> Healthy programs measure both sides: customer satisfaction AND unit economics. A subscription that's loved but unprofitable is a marketing expense, not a business model. A loyalty program with huge redemption rate but flat new-customer acquisition is wasted spend.

## Step 4 — Domain validators

### Subscription:

- **Cohort retention reports monthly** — M1, M3, M6, M12
- **Voluntary vs. involuntary churn split** — tracked weekly
- **LTV:CAC for subscribers vs. non-subscribers** — quarterly comparison
- **Skip/swap/pause usage** — not dumping customers into churn
- **Dunning recovery rate** — measured against 40-60% benchmark

### Loyalty:

- **Incremental revenue attribution** — loyalty-driven vs. would-have-bought-anyway
- **Point liability balance sheet** — tracked as expected future redemption value
- **Tier distribution** — healthy pyramid, not over-concentrated
- **Redemption rate** — if >70%, loyalty is a de-facto discount program

## Step 8 — Working protocol additions

- **Never launch subscription without dunning infrastructure** — 30-50% of churn will be involuntary
- **Never hide cancellation** — friction destroys brand trust and doesn't lower real churn
- **Never launch loyalty without exit plan** — programs are hard to retire
- **Never ignore point liability** — accounting will flag eventually
- **Always measure cohort retention, not monthly churn alone** — monthly hides cohort quality
- **Always measure referral fraud** — programs with no fraud filter get gamed

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — for retention-curve analysis and LTV modeling
- `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/wiki/_index.md` — for VIP / tier program design patterns
- `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/wiki/_index.md` — for program communication frameworks

## Common example fills

- **"Launch first subscription program for CPG coffee brand — 15% discount, monthly cadence, target 20% of new customers on subs within 90 days"**
- **"Overhaul underperforming loyalty program — redemption 75% but new-customer acquisition flat; need to reposition"**
- **"Launch referral program parallel to loyalty — target referral share of new customers 8-12%"**
- **"Diagnose subscription churn — Month-3 voluntary churn 22% (target 10%); remediation plan"**
- **"Launch VIP tier for existing loyalty — target top 3% of customers; experience over discount"**

## Hand-off

After bootstrap, use `~/.claude/templates/growth-ecommerce/subscription-loyalty/resumption.md`.
