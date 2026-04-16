# Lifecycle (Email/SMS/Push) Program — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** starting a multi-session lifecycle-marketing program — email, SMS, push — for welcome, cart, post-purchase, retention, and win-back flows.

---

## Who this is for

Lifecycle / CRM / retention marketers at DTC brands, subscription businesses, B2B SaaS PLG teams, or agencies managing lifecycle for clients. Programs typically span 6-12 weeks for a structured rebuild or 8-16 weeks for a full CRM overhaul.

## Opinionated defaults

### Flow structure

- **Welcome flow: 6 emails over 14 days** — (1) brand story T+0, (2) social proof T+1, (3) offer T+3, (4) education T+5, (5) hero product T+7, (6) final nudge T+14
- **Abandoned cart: 3 emails** at T+1h / T+1d / T+3d. Optional SMS at T+30min.
- **Post-purchase: T+7 / T+30 / T+90** — (T+7) thank-you + review request + first-time-buyer offer; (T+30) replenishment / cross-sell; (T+90) reactivation signal
- **Win-back: T+60 / T+120 inactive** — with "we miss you" at T+60 and offer-led at T+120
- **Browse abandonment:** opt-in at T+2h after 3+ PDP views without purchase

### Segmentation

- **RFM (Recency / Frequency / Monetary)** as default — 3×3×3 grid = 27 segments
- **Always segment by acquisition channel** when MER is primary — lifecycle behavior differs wildly by acquisition source
- **Never one-size-fits-all campaigns** past 5K list size

### Measurement

- **Revenue/message is primary KPI.** Open rate is vanity; click-through is diagnostic; revenue is the only number that matters.
- **Attribution:** last-touch with 7-day click / 24-hour view window (adjust with reason)
- **Suppression rate <20% email, <2% SMS** of total list
- **Deliverability:** inbox placement tests monthly; Gmail/Yahoo postmaster weekly

### Discipline

- **A/B test subject lines on every campaign** over 1000 sends (50/50 split)
- **Frequency caps:** max 5 emails/week per subscriber (aggregate across flows + campaigns); max 4 SMS/month
- **Compliance:** CAN-SPAM + GDPR + CCPA + TCPA + CASL — double opt-in for EU, express written consent for SMS in US
- **Content production cadence:** 2 campaigns/week minimum to stay front-of-mind; never >1/day
- **Review cycle:** every email/SMS reviewed by a second set of eyes before send

## Step 0 — Interview question additions

1. **Current flows in place** — which exist, which are dormant, which are broken?
2. **ESP / CRM stack** — Klaviyo / Braze / Iterable / Attentive / Postscript / Omnisend / HubSpot — and versions / tiers
3. **Integration depth** — Shopify (or ecomm platform) connected? Reviews? Returns? Support tickets?
4. **List size + growth rate** — email and SMS independently; by source
5. **Deliverability baseline** — inbox placement, complaint rate, unsubscribe rate, spam rate
6. **Current revenue mix** — % of total revenue attributable to owned channels
7. **Flow maturity** — welcome exists? Cart? Post-purchase? Win-back? Which are broken vs. working vs. missing?
8. **Segmentation approach** — RFM? Category? Channel? Lifecycle-stage? Or blast to all?
9. **Creative production capacity** — in-house designer? Stock template packs? Agency?
10. **Compliance stance** — double opt-in? Express consent for SMS? Any past complaints / legal issues?
11. **Subscription component** — replenishment cadence? Churn protection flows?

## Step 2 — Milestone template (12-week program)

```markdown
### M1 — Audit + Deliverability Baseline (week 1)
- Deliverable: flow inventory, segment audit, deliverability health report, revenue/channel baseline
- Validation: Gmail/Yahoo postmaster accessible; IP + domain reputation documented
- Target: end of week 1

### M2 — RFM Segmentation Build (week 2)
- Deliverable: 27-segment RFM model live in ESP; tagging verified
- Validation: every subscriber has valid R/F/M tag; counts by segment reported
- Target: end of week 2

### M3 — Core Flow Rebuild: Welcome + Cart + Post-Purchase (week 3-4)
- Deliverable: three flagship flows live, content approved, triggers tested
- Validation: test sends from agent address flow correctly through all branches
- Target: end of week 4

### M4 — Campaign Calendar + Templating (week 4-6)
- Deliverable: 12-week content calendar; 5+ reusable templates; review workflow
- Validation: 2 campaigns/week cadence hit for 2 weeks straight
- Target: end of week 6

### M5 — Advanced Flows: Win-back + Browse + Replenishment (week 6-8)
- Deliverable: win-back, browse-abandon, replenishment flows live
- Validation: test sends complete; opt-in logic verified
- Target: end of week 8

### M6 — Performance Review + Iteration Cadence (week 8-12)
- Deliverable: performance dashboard; weekly review rhythm; quarterly re-optimization plan
- Validation: revenue/message trending flat or up 4 weeks; dashboard auto-refreshes
- Target: end of week 12
```

## Step 3 — Critical mental model (for Implement.md)

> **Lifecycle marketing is not email marketing. It's the orchestrated conversation with a customer across their journey.**
>
> Channel (email vs. SMS vs. push) is secondary; the customer state machine is primary. Every subscriber is in exactly one lifecycle state at a time (new, considering, recent-buyer, repeat, at-risk, churned) — and the flow they receive should match that state, not the segmentation marketing team prefers.
>
> Over-messaging destroys LTV; right-sized messaging compounds it. A 10% lift in revenue/message with a 5% reduction in send volume is a huge win; it says the program is more valuable per touch. The opposite (more sends, flat revenue/message) is a failing program hiding behind gross numbers.

## Step 4 — Domain-specific validators

- **Deliverability:** Gmail/Yahoo postmaster — spam rate <0.3%, reputation "High"
- **Inbox placement:** monthly 250ok / Litmus test — >95% primary inbox
- **Flow health:** every flow test-sent through every branch weekly
- **Compliance:** double-opt-in for EU list; express written for SMS US list
- **Revenue/message:** auto-reported in dashboard; weekly 4-week rolling average
- **Suppression rate:** <20% email, <2% SMS of active list

## Step 8 — Domain-specific working protocol additions

- **Never blast to full list after 5K subscribers** — always segment
- **Never send SMS without express written consent** — TCPA risk = $500-$1500/violation
- **Never remove a suppression — use list hygiene to re-engage, not re-add**
- **Never launch a flow without test-sending every branch** — broken flows damage trust
- **Always review send cadence vs. frequency cap** before a campaign — check active flows + planned campaigns
- **Always A/B test subject line** on campaigns >1000 sends
- **Always segment post-purchase flows by first-time vs. repeat** — their offers and intent are different
- **Always clean list quarterly** — sunset subscribers inactive >180 days; sending to dead addresses destroys deliverability

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/wiki/_index.md` — related retention and customer-experience content
- Reference Klaviyo / Attentive / Braze docs directly for ESP-specific features; templates aim to be ESP-agnostic

## Common example fills

- **"Rebuild DTC welcome + cart + post-purchase flows for $20M beauty brand; current revenue/message $0.18, target $0.35"**
- **"Launch SMS program from zero for subscription coffee brand; compliance-first buildout"**
- **"Consolidate two ESPs after acquisition — migrate from Braze to Klaviyo with <1% list loss"**
- **"Fix deliverability collapse — inbox placement dropped from 95% to 60% over 8 weeks; diagnose + remediate"**
- **"Launch replenishment flow for CPG skincare brand; target 15% repeat-rate lift in 90 days"**

## Hand-off

After bootstrap, use `~/.claude/templates/growth-ecommerce/lifecycle/resumption.md` for sessions 2+.
