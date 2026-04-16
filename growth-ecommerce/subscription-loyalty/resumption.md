# Subscription / Loyalty Program — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Monthly cohort retention review"
- "Dunning optimization — recovery rate 32%, target 50%"
- "Loyalty tier threshold reset"
- "Referral fraud investigation"
- "Churn-save experiment launch"
- "VIP quarterly touch planning"

## Blocker questions

1. **Any payment processor issue / dispute in last 7 days?** Affects dunning + involuntary churn; investigate first.
2. **Any program-impacting policy change** (terms, cancellation flow, tier structure) in flight that affects analysis?
3. **Any accounting / finance flag on point liability or revenue recognition?** Loyalty points and subscription deferred revenue have accounting implications.
4. **Any active churn-save experiment?** Avoid overlapping interventions.
5. **Any seasonal cohort quirk** (Q4 cohorts with different intent) that should be excluded or flagged in analysis?

## Ranked work patterns

### Monthly cohort review cadence
Standard:
1. Pull M1 / M3 / M6 / M12 retention by acquisition month
2. Compare current cohort to prior 3 cohorts
3. Flag cohorts with degraded retention (>10% vs. baseline)
4. Root-cause: acquisition mix shift? Product change? Promotion-heavy cohort?
5. Feed learnings into next-cohort acquisition strategy

### If churn is rising
Segment diagnosis:
1. Voluntary vs. involuntary split — different interventions
2. By cadence (monthly vs. quarterly subs)
3. By acquisition channel
4. By pricing tier
5. By content / feature engagement depth

### If loyalty redemption is high but new-customer acquisition is flat
Program is a de-facto discount. Options:
1. Shift tier thresholds up (harder to earn)
2. Shift earning rate down (slower accumulation)
3. Add experiential tier components (non-discount value)
4. Re-position around acquisition (referral bonus, signup bonus)

### If referral fraud detected
Immediate:
1. Pause suspect accounts
2. Tighten payout trigger rules
3. Add device / IP / email fraud detection
4. Refund suspicious payouts

## Working protocol additions

- **Never run churn-save at full list** — test with control group
- **Never extend grace periods without testing impact** — can increase churn
- **Never forget point liability balance** — accounting flag will come eventually
- **Always track voluntary vs. involuntary separately**
- **Always measure tier-distribution shift** — if everyone reaches top tier, program is over-generous

## Verification commands

```
# Subscription health
{active subs, MoM change, churn breakdown} # expect: net retention > 100%

# Dunning recovery
{recovery rate last 30 days}              # expect: 40-60%

# Loyalty engagement
{tier distribution + redemption rate}     # expect: healthy pyramid, redemption 40-60%

# Point liability
{expected future redemption value}        # expect: matches accounting estimate

# Cohort retention freshness
{M1 / M3 / M6 data complete for latest cohort} # expect: yes
```

## Common drift patterns

- **Cancellation friction creep** — teams keep adding friction; eventually customers complain + churn publicly. Friction-free is actually better for LTV.
- **Point inflation** — bonus points, double-point days, promotions = devaluation of program
- **Tier reset debates** — reset annually vs. never; both have downsides; pick and commit
- **VIP dilution** — too many customers reach VIP; becomes less special
- **Dunning aggression** — over-communicating about failed payments hurts relationship; find balance
