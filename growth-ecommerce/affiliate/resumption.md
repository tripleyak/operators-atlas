# Affiliate Program — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Monthly top-affiliate review"
- "Fraud investigation"
- "Commission-ladder adjustment"
- "New content-affiliate outreach batch"
- "De-duplication policy review"
- "Network migration (CJ → Impact)"

## Blocker questions

1. **Any active fraud investigation?** Resolve before scaling any affiliate activity.
2. **Any network / tool platform issue** (CJ, Impact, Rakuten outage, Refersion bug)?
3. **Any commission calculation error** — retroactive fixes required?
4. **Any MAP violation by affiliate?** Enforcement protects partner ecosystem.
5. **Any legal / T&C update needed?** — platform rules change occasionally

## Ranked work patterns

### If fraud detected
Standard procedure:
1. Quarantine affiliate commissions
2. Investigate — orders, IP, device, referral patterns
3. Decision: void + chargeback + terminate, or warning + probation
4. Document + update fraud rules
5. Audit similar affiliates for pattern match

### Monthly top-affiliate review
Standard:
1. Top-20 by revenue — trend, tier movement
2. Personal outreach — relationship maintenance
3. Co-creation opportunities (exclusive products, content collaborations)
4. Commission-tier recalibration
5. Underperforming formerly-top affiliates — diagnose

### Commission-ladder adjustment
Process:
1. Revenue + margin analysis by commission tier
2. Competitor commission benchmarks
3. Affiliate feedback on current structure
4. Tier-movement impact modeling
5. Transparent announcement to affiliates

### Network migration
Risk: revenue disruption during transition. Process:
1. Affiliate export from current network
2. Parallel-run both networks
3. Affiliate migration (manual outreach to top-20)
4. Cutover + sunset old network
5. Retention measurement at 30/60/90 days

### If coupon affiliate last-clicking too much
De-duplication policy tightening:
1. First-look-wins attribution (creator or paid ad wins over later coupon click)
2. Disqualify coupon traffic from non-coupon journeys
3. Reduce coupon commission
4. Blacklist most aggressive coupon sites

## Working protocol additions

- **Never pay fraud** — void, chargeback, terminate
- **Never let affiliates bid brand terms**
- **Never skip top-affiliate relationship management** — they're the 80/20
- **Always review fraud rules quarterly** — new tactics emerge
- **Always document de-duplication policy** in T&C

## Verification commands

```
# Program revenue
{affiliate revenue + % of total revenue}  # expect: tracked, stable or growing

# Top-20 affiliate concentration
{top-20 share of affiliate revenue}        # expect: 60-80%

# Fraud detection
{flagged orders + resolution}              # expect: detection active, resolution current

# Commission accuracy
{audit sample of recent commissions}       # expect: matches policy

# MAP violations
{affiliate pricing audit}                   # expect: no violations or remediated quickly
```

## Common drift patterns

- **Coupon creep** — unchecked, coupon affiliates start last-click-grabbing everything
- **Top-affiliate complacency** — assume they'll stay, don't manage relationship; they leave
- **Fraud slow response** — delays in fraud action signal tolerance to bad actors
- **Commission inflation** — negotiated exceptions become policy over time
- **Migration disruption** — switching networks loses 20-40% of affiliates if not managed
