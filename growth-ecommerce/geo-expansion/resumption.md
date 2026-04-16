# Geographic Expansion Program — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Launch-week readiness check for UK"
- "Customs seizure investigation — last batch held at EU border"
- "Local payment-method integration (iDEAL, Klarna)"
- "CAC drift diagnosis — EU paid performance collapsed"
- "Third-party logistics (3PL) selection for APAC entry"
- "Regulatory update impact — new UK packaging rules"

## Blocker questions

1. **Any compliance flag active?** Product compliance failure = customs seizure, not a delay. Stop-ship until resolved.
2. **Any tax registration or filing issue?** VAT / GST penalties compound; resolve immediately.
3. **Any FX volatility affecting margin?** Track, adjust pricing if sustained.
4. **Any local regulatory change in last 30 days?** Product compliance, data privacy, labeling rules do shift.
5. **Any customer-service language / timezone gap causing complaints?** Local coverage needs investigation.
6. **Local payment-method outage?** iDEAL / Klarna / Pix / AliPay occasionally have regional issues — conversion drops silently.

## Ranked work patterns

### If customs issue / regulatory block
Drop everything:
1. Identify specific compliance gap (label, certification, ingredient, claim, documentation)
2. Remediate — new labels, updated certification, corrected documentation
3. Arrange alternate shipment (re-export, destroy, rework)
4. Document learning; add to compliance checklist

### If soft launch performing
Decision gates:
1. 30-day review: CAC, CVR, payment-method mix, customer reviews
2. 60-day review: retention signal, refund rate, returns handling
3. 90-day review: scale / hold / exit decision with data

### If scale phase underperforming
Diagnose:
1. Channel mix — is it the right channels for this market?
2. Creative localization — does creative feel local or imported?
3. Pricing — at local market premium, is willingness-to-pay present?
4. Competitive action — has a local incumbent responded?
5. Payment-method coverage — missing a critical local method?
6. Customer support — language, timezone, return address adequate?

### Market review cadence
Monthly:
1. Performance vs. home market + vs. plan
2. Channel mix + CAC trends
3. Compliance + regulatory watch
4. Customer service signal
5. Competitive landscape updates
6. FX impact on margin

## Working protocol additions

- **Never ship products out of compliance window** — customs seizure
- **Never miss a VAT filing deadline** — penalties compound
- **Never assume home-market creative works locally** — localize then test
- **Never ignore returns address** — returns going back to US are expensive + slow
- **Always monitor FX impact** — 5-15% swings common
- **Always maintain local regulatory watch** — rules do change

## Verification commands

```
# Compliance status
{product compliance by market}          # expect: all markets current

# Tax filings
{VAT / GST / consumption-tax status}    # expect: no overdue filings

# Local-payment coverage
{payment-method fire rate by country}   # expect: all expected methods live

# Market performance
{market-by-market CAC, CVR, return rate} # expect: tracked + trending

# FX exposure
{revenue + margin by currency}           # expect: hedge or document exposure
```

## Common drift patterns

- **Home-market team making local decisions** — cultural + regulatory blind spots
- **VAT filing forgotten** — small oversight, large penalty
- **Localization theater** — translated site but local operator isn't running creative
- **Exchange-rate ignorance** — margin erodes silently; discover at quarter-end
- **Returns logistics skipped** — hot market but return experience is terrible
- **Local competitor response** — incumbents defend; don't underestimate
