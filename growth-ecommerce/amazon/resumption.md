# Amazon Program — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Weekly search-term harvest + negative mining"
- "Listing optimization pass on hero SKU"
- "Budget pacing adjustment across campaign structure"
- "Account health investigation — ODR spike"
- "Q4 readiness check — inventory, deals, PPC ramp"
- "Competitor conquest campaign launch"

## Blocker questions

1. **What's the current IPI + ODR?** If IPI <400 or ODR >1% → fix account health before anything else.
2. **Any active policy warnings / violations?** If yes → remediation takes priority.
3. **Inventory status on hero SKU?** If <30 days supply → pause PPC scale; replenish first.
4. **Any category-level event in next 30 days?** (Prime Day, Black Friday, seasonal peak) — if yes, lock structure and prep.
5. **Any review spike — positive or negative?** Negative review burst = listing issue or product issue; positive burst = investigate authenticity.
6. **Any recent Amazon platform changes?** (ad format rollouts, policy changes, algorithm shifts) — check Seller Central news.

## Ranked work patterns

### If account health is at risk
Drop everything. Account health work:
1. Identify violation / ODR source (orders, returns, complaints, policy hits)
2. Remediate root cause (listing accuracy, fulfillment issue, product quality, policy compliance)
3. Appeal if necessary with documented plan
4. Do not launch new campaigns until health is green

### If inventory is low
Do not scale PPC. Reduce bids on losing keywords; maintain winning-keyword position; accelerate replenishment.

### If TACoS is drifting upward
Diagnostic sequence:
1. Search-term bleed — are Exact campaigns cannibalizing Auto? Add negatives.
2. Match-type mix — too much on Broad without Phrase/Exact winners? Cascade.
3. Product page CVR — has rating / reviews / price / availability changed?
4. Competitor action — new entrant bidding heavily? Brand Analytics will show.
5. Seasonality — is this a natural off-peak pattern?

### If listing CVR is declining
Audit: rating trend · review recency · Buy Box status · pricing vs. competitors · A+ Content freshness · main image compliance · backend keyword changes.

### Weekly search-term harvest
Standard cadence:
1. Pull 14-day Search Term Report
2. Promote profitable keywords to tight Exact campaigns
3. Add unprofitable keywords to negatives
4. Document changes in `Documentation.md`

## Working protocol additions

- **Never pay for reviews.**
- **Never restructure PPC during learning period** — algorithm punishes frequent change
- **Never scale PPC when IPI <400** — storage constraints will bite
- **Always check Brand Analytics weekly** — competitor bidding patterns + search volume + conversion share
- **Always document bid changes** — roll-forward accountability
- **Always respect the 60-day lead time** for Q4 / Prime Day / holiday moments

## Verification commands

```
# Account health
{Seller Central Account Health page} # expect: ODR <1%, violations = 0

# Inventory status
{IPI + days-of-supply report}        # expect: IPI >400, hero SKU >30d supply

# TACoS trend
{weekly TACoS report}                 # expect: flat or decreasing

# Listing quality
{hero SKU listing audit}              # expect: A+ Content, 2000px image, 249-byte backend

# Budget pacing
{daily campaign spend}                # expect: within budget, no mid-day exhaustion
```

## Common drift patterns

- **Chasing ACoS, ignoring TACoS** — ACoS can drop while TACoS rises (e.g., organic decline masked). Monitor both.
- **Over-restructuring PPC** — every major change reset learning. Commit to a structure and iterate within it.
- **Inventory complacency** — always looks fine until it's not. Automate alerts.
- **Review quality ignored** — a 4.2 rating may hide recent 2-stars dragging the trend. Check recent 30-day avg.
- **Vendor / platform support tempting shortcuts** — reject all review / rank / removal shortcut offers. They're all suspension risks.
