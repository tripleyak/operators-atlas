# Retention / LTV Program — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** starting a multi-session retention or LTV program — cohort optimization, churn intervention, win-back, subscription retention, or LTV:CAC improvement work.

---

## Who this is for

Retention managers, data analysts, growth leaders at DTC, subscription, B2B SaaS, or marketplace businesses. Programs span 8-16 weeks for a focused retention rebuild or 12+ weeks for a full LTV modeling + intervention system.

## Opinionated defaults

### LTV measurement

- **Windowed LTV: 1yr / 2yr / 3yr.** Never "lifetime" — unknowable at decision-time and mathematically unbounded with tail noise.
- **Cohort analysis by acquisition month.** Everyone in the same cohort entered at the same point in seasonality, same promotions, same market.
- **Retention curves: weekly for first 13 weeks, monthly thereafter.** Captures the critical early drop-off.
- **Segment LTV by channel + category + AOV.** Averages hide huge variance.

### LTV:CAC targets

- **Target: LTV:CAC ≥ 3:1 by month 12.** Lower ratios mean either payback is slow or unit economics are thin.
- **Payback period: <12 months** for subscription; <18 months for one-time purchase with repeat; <6 months for SaaS with expansion.
- **New-customer CAC and LTV reported together, not separately** — they're the same decision.

### Churn / disengagement

- **Churn signal: 60-day inactive (rolling)** for one-time purchase; 1 failed payment for subscription.
- **Early-warning: 30-day reduced engagement** triggers monitoring, not intervention yet.
- **Win-back: start at 60-day mark**, escalate at 120-day and 180-day marks.

### Intervention discipline

- **A/B test every intervention before rollout** — "common sense" retention tactics often backfire.
- **Measure on revenue, not engagement.** A metric like "email opens +50%" is meaningless if LTV is flat.
- **Control for self-selection.** "We emailed the engaged users and they bought more" is not an intervention result.

### Segmentation

- **RFM (Recency / Frequency / Monetary) + category + channel** as default.
- **Never treat all customers the same past 5K active users** — behavior differs enormously.
- **Identify predictors, not just descriptors.** "People who bought X and Y are likely to buy Z" > "people buy stuff."

## Step 0 — Interview question additions

1. **Current LTV definition:** what window? what segmentation?
2. **LTV:CAC today** — by channel, by category, blended
3. **Churn definition** — subscription (explicit cancel, failed payment, paused) or behavioral (N-day inactive)?
4. **Cohort data availability** — can we pull by acquisition month × weekly retention × revenue?
5. **Current retention programs** — loyalty, win-back, replenishment, subscription, ambassador?
6. **Subscription component** — if yes, what cadence, churn rate, recovery rate?
7. **Customer-support data** — are tickets tagged with reason codes? Available to this program?
8. **Returns / refund data** — is this a big component of churn?
9. **NPS / CSAT** — any measurement, recent results?
10. **Technical stack** — warehouse, CDP, loyalty platform, subscription platform

## Step 2 — Milestone template (12-week program)

```markdown
### M1 — Cohort Data Build + Baseline Analysis (week 1-2)
- Deliverable: cohort retention curves; LTV by window + segment; baseline churn rate
- Validation: data matches bank / subscription system; cohorts complete
- Target: end of week 2

### M2 — Segmentation Model Build (week 2-3)
- Deliverable: RFM + category + channel segments; segment-level LTV + retention + churn
- Validation: every customer tagged; segment counts + economics reported
- Target: end of week 3

### M3 — Retention Driver Analysis (week 3-4)
- Deliverable: top-5 drivers of retention (and churn); evidence + statistics
- Validation: findings cross-validated with customer-support reasons, surveys, behavioral data
- Target: end of week 4

### M4 — Intervention Program Design (week 4-5)
- Deliverable: 3-5 intervention concepts with hypothesis + KPI + design
- Validation: each intervention has control group design; stats power calculated
- Target: end of week 5

### M5 — A/B Test Launch (week 5-10)
- Deliverable: top-3 interventions running with proper controls
- Validation: sample size adequate; variant allocation even; KPI logged
- Target: end of week 10

### M6 — Systematic LTV Lift Program (week 10-12)
- Deliverable: winners rolled out; ongoing measurement + iteration cadence
- Validation: documented LTV lift vs. control; program running without external help
- Target: end of week 12
```

## Step 3 — Critical mental model

> **Retention is earned, not won.**
>
> The best retention program is a product that solves a recurring problem. Everything else — email, SMS, loyalty programs, win-back offers — is marketing on top of that core truth. If the product only works once, retention marketing will extend purchase windows modestly but cannot create repeat demand where none exists.
>
> This reframes what retention work actually is:
> 1. **Identify which customers find repeat value** (segmentation + LTV modeling)
> 2. **Help them buy again without friction** (replenishment, subscription, easy-reorder)
> 3. **Don't over-market to customers who don't find repeat value** (suppression, win-back timing)
>
> A 15% repeat rate with a profitable cohort beats a 35% artificial repeat rate bought with heavy discounts.

## Step 4 — Domain validators

- **Cohort data integrity:** cohort revenue sums match finance revenue within ±2%
- **Segmentation coverage:** 100% of customers tagged; no orphan segment
- **Test integrity:** variant assignment verified; exposure logged; sample size adequate
- **KPI tracking:** revenue, retention %, repeat rate tracked alongside engagement metrics
- **Control group preserved:** never mix treatment and control in downstream analyses

## Step 8 — Working protocol additions

- **Never declare a retention win from engagement metrics alone** — show revenue impact or it didn't happen
- **Never design a retention program without segment analysis** — you'll push value-destroying interventions to valuable segments
- **Never extrapolate short-window LTV to "lifetime"** — use 1yr / 2yr / 3yr windows
- **Never run a retention intervention without a control group** — self-selection bias will fake a result
- **Always report LTV:CAC together** with the channel mix that drove each
- **Always segment churn investigation** — blended churn hides the segments with the problems
- **Always document intervention hypothesis** before launch

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — relevant for channel-LTV analysis and retention-curve modeling (Hill curves apply conceptually to retention)
- `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/wiki/_index.md` — scoring and segmentation frameworks

## Common example fills

- **"Improve LTV:CAC from 2.1:1 to 3:1 for DTC beauty brand over 12 weeks via targeted retention interventions"**
- **"Subscription retention program for CPG skincare — reduce Month-3 churn from 18% to 10%"**
- **"Diagnose LTV decline — 1yr LTV dropped from $280 to $210 over last 4 quarters; investigate + remediate"**
- **"Win-back program launch — target 15% reactivation rate on 60-day-inactive segment"**
- **"Segment-level LTV modeling for marketplace; identify top 20% LTV cohorts for retention focus"**

## Hand-off

After bootstrap, use `~/.claude/templates/growth-ecommerce/retention-ltv/resumption.md`.
