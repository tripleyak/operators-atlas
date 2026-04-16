# Retention / LTV Program — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Cohort refresh for Q2 acquisition month"
- "Win-back test launch on 60-day inactive"
- "Subscription churn investigation — Month-3 drop"
- "LTV:CAC segmentation by channel"
- "Intervention readout + next-wave planning"

## Blocker questions

1. **Is the cohort data pipeline healthy?** If weekly cohort refresh is broken → diagnostic work first.
2. **Any active intervention test?** Avoid contaminating by adding new programs to the same segment.
3. **Any recent product change** (new SKU, pricing, bundling)? Can create a structural break in retention curves.
4. **Any channel mix change** (new paid channel, organic spike)? Changes acquisition cohort quality.
5. **Any recent customer-support / returns trend?** Often the upstream signal of churn we're about to see.

## Ranked work patterns

### If cohort data is stale
Refresh first. Nothing depends on stale retention data in a useful way.

### If test just concluded
Readout procedure:
1. Significance calculation with proper method
2. Segment post-hoc analysis — does the win hold across segments?
3. Revenue per user comparison — is this a real lift or engagement theater?
4. Retention impact measurement — does the test cohort retain differently 30 / 60 / 90 days out?
5. Rollout or kill decision with `Documentation.md` entry

### If LTV is declining
Segment-level investigation:
1. Is it cohort quality (acquisition-driven) or cohort behavior (retention-driven)?
2. Which channels' cohorts declined? (new-channel dilution? paid-channel degradation?)
3. Any product change coinciding with cohort break?
4. Any category-level secular trend? (category decline vs. brand issue)

Cohort-quality decline = fix acquisition mix. Cohort-behavior decline = fix product/experience/retention.

### If churn is up
Segment first, intervene second. Blended churn changes can hide +10% / -20% cross-segment.

## Working protocol additions

- **Never declare win from engagement metric alone** — show revenue
- **Never mix control group into downstream work**
- **Never compare non-matched cohorts** — always control for time/channel/product
- **Always show confidence intervals on LTV**
- **Always segment before acting**

## Verification commands

```
# Cohort freshness
{cohort refresh timestamp}          # expect: <7 days old

# Revenue reconciliation
{cohort sum vs. finance revenue}    # expect: ±2%

# Active test status
{test tracker}                       # expect: adequate sample, clean variant split

# LTV trend
{1yr LTV by cohort month}           # expect: stable or documented drift
```

## Common drift patterns

- **Retention-program bloat** — every intervention becomes "always on"; the intervention that was a winner on a control becomes a baseline everyone gets, with no holdout. Rotate holdouts.
- **Vanity engagement metrics** — "email-open rate is up 40%" masks flat revenue. Always check revenue.
- **Cherry-picking cohorts** — comparing cohorts with different acquisition mix. Match cohorts first.
- **Retention theater** — discount-driven repeat rate that actually destroys LTV. Gross vs. net retention matters.
