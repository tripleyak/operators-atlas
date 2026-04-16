# Pricing / Promotion — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Q3 promotional calendar planning"
- "Price-elasticity A/B test readout"
- "MAP violation response"
- "Competitor price-move response"
- "Subscription pricing migration"
- "Promotional post-mortem"

## Blocker questions

1. **Any pending / recent price change** requiring measurement window?
2. **Any active promotion in flight** that affects next decision?
3. **Any MAP violation** — enforcement response needed
4. **Any competitor pricing move** that requires response?
5. **Any inventory state** that drives or constrains promotional calendar?

## Ranked work patterns

### If full-price CVR collapsing
Signal that customers are trained to wait. Diagnosis:
1. Review promotional cadence frequency
2. Review promotional depth trend
3. Review recency of last promotion (customers may be anticipating)
4. Compare current state to historical healthy baseline

Remediation: reduce promotional frequency or depth; run full-price-only window; communicate pricing clearly.

### If promotion just concluded
Post-mortem (within 14 days):
1. Revenue vs. forecast
2. Margin vs. plan
3. Customer acquisition vs. retention mix
4. Post-promo revenue drop (how quickly back to baseline?)
5. Inventory impact
6. Documentation of learnings

### If competitor moved
Decision framework:
1. Is the competitor's move sustainable or promotional?
2. Is there margin headroom to match?
3. Is the price-conscious segment your target?
4. What's the positioning cost of matching?
5. Decision: match, hold, or communicate differentiation

Don't reflexively match; evaluate consequences.

### Quarterly pricing review
Standard:
1. Promotional revenue share by quarter + trend
2. Margin discipline — promotional GM vs. target
3. Full-price CVR trend
4. Tier-level revenue + margin
5. Competitor pricing state
6. Willingness-to-pay research refresh

## Working protocol additions

- **Never reactive price-match** without analysis
- **Never allow stacking** by default
- **Never discount below GM minimum**
- **Always post-mortem promotions**
- **Always track full-price CVR** as canary

## Verification commands

```
# Promotional calendar health
{current quarter calendar + pacing}     # expect: no overlaps, clear purpose

# Revenue mix
{promotional vs. full-price revenue}     # expect: 15-30% promo share

# Gross margin
{GM by promotion type}                   # expect: above minimum threshold

# Full-price CVR trend
{weekly full-price CVR}                  # expect: stable, not declining

# MAP compliance
{MAP monitoring dashboard}               # expect: no active violations
```

## Common drift patterns

- **Promotional creep** — "just this once" becomes monthly; revenue share balloons
- **Depth inflation** — customers expect deeper discounts each year
- **Stacking accommodation** — teams approve exceptions; becomes expected
- **Competitor-reflex matching** — reacting without analysis
- **Margin discipline erosion** — "revenue goal first" overrides GM floor
