# Wholesale / Retail Program — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Buyer pitch prep for Target category review"
- "Pilot sell-through review at Whole Foods"
- "Chargeback audit — 18% of wholesale revenue (target 8%)"
- "MAP violation response"
- "Trade-spend ROI review"
- "Planogram sync with retail partner"

## Blocker questions

1. **Any retailer calendar window closing in next 30 days?** If yes, that's priority.
2. **Any active MAP violation?** Resolve fast — partner relationships depend on enforcement
3. **Any compliance flag** (barcode, case-pack, labeling) causing chargebacks?
4. **Any EDI / ordering issue?** Broken EDI = delayed orders, chargebacks, buyer frustration
5. **Any inventory conflict with DTC priorities?** Surface before shipping
6. **Any POS data refresh issue?** Without sell-through data, sales decisions are blind

## Ranked work patterns

### If buyer pitch is imminent
Full prep:
1. Sell-through data for any existing retail presence (benchmark)
2. Category trend data (for their context)
3. Pitch deck: problem → product → proof → ask
4. Samples coordinated
5. Pricing / MAP clarity
6. Co-op / demo budget available
7. Follow-up plan

### If pilot is underperforming
Diagnose before reorder:
1. Placement — is product where the planogram says?
2. Pricing — price matches agreement? Display anchors?
3. Velocity benchmark — typical for category?
4. Seasonality — is this expected or abnormal?
5. Training — store associates trained? (Often forgotten)
6. Trade support — is co-op / demo actually running?

### If chargebacks are high
Categorize + remediate:
1. Compliance (barcode, label, case-pack) → packaging / labeling fix
2. Shipping (short-ship, damage) → 3PL / freight audit
3. Returns / defects → product QA
4. Performance (OTIF — on-time in-full failures) → supply chain
5. Retailer-side (scanning error, policy) → dispute with documentation

### Monthly retail review
Standard:
1. Sell-through by retailer / store / SKU
2. Chargebacks + resolution status
3. Trade spend vs. ROI
4. Buyer relationship status (next meeting, expansion conversations)
5. Inventory pipeline
6. DTC cannibalization check

## Working protocol additions

- **Never ship without EDI confirmation** — missed POs = chargebacks
- **Never skip retail compliance check** on new SKUs / packaging changes
- **Never ignore MAP violations** — enforcement protects partner relationships
- **Never over-promise delivery** — OTIF failures are expensive
- **Always get POS data cadence locked** — weekly / biweekly / monthly
- **Always maintain buyer relationship** — monthly touch minimum on active accounts

## Verification commands

```
# Retailer POs vs. fulfillment
{EDI shipment status}                   # expect: OTIF >95%

# Chargeback trend
{monthly chargeback by category}        # expect: <8% of wholesale revenue

# Sell-through
{POS data by retailer / SKU / week}     # expect: velocity meeting benchmark

# MAP compliance
{MAP monitoring tool output}            # expect: violations <14 days old

# Trade-spend utilization
{co-op + demo + slotting spend}         # expect: within budget, ROI tracked
```

## Common drift patterns

- **DTC team making retail pricing decisions** — kills partner relationships
- **Trade-spend creep** — co-op keeps growing; margin erodes; net economics flip negative
- **Calendar drift** — missing retailer category reviews costs a year
- **Inventory prioritization chaos** — DTC stocks out OR retail stocks out; neither acceptable
- **Buyer relationship atrophy** — buyer moves / quits; new buyer doesn't know you; velocity drops
