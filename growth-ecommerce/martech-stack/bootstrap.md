# Martech Stack — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** auditing, rationalizing, or rebuilding the martech / ecommerce-tech stack — tool consolidation, data-infrastructure overhaul, CDP implementation, or stack modernization.

---

## Who this is for

CMOs, VPs of growth, marketing ops, data/analytics leaders at $10M-$500M businesses drowning in tool sprawl, integration tax, and fragmented customer data. Programs span 12-24 weeks for focused overhaul; 6+ months for full-stack rebuilds.

## Opinionated defaults

### Philosophy

- **Consolidate, don't expand.** Most stacks have 50-80% redundant tools. Rationalize before adding.
- **Best-of-breed is not free.** Every additional tool adds integration tax, security surface, invoicing overhead, vendor-management time.
- **Warehouse-as-source-of-truth.** All customer data lands in the warehouse (Snowflake / BigQuery / Redshift / Databricks); tools read from the warehouse, not from each other.
- **Activation on top of warehouse.** Hightouch / Census / Rudderstack do reverse-ETL into marketing tools.
- **Identity resolution is the ground layer.** Without it, every downstream personalization / attribution / activation is shaky.

### Canonical stack layers (for most DTC / ecommerce / B2B SaaS)

1. **Data warehouse** — Snowflake / BigQuery / Redshift / Databricks / Clickhouse
2. **ELT pipeline** — Fivetran / Stitch / Airbyte / Hightouch (for reverse-ETL)
3. **CDP or CDP-equivalent** — Segment / Rudderstack / mParticle / Hightouch-as-CDP / Census
4. **Identity resolution** — in-CDP or dedicated (LiveRamp, Merkle)
5. **Analytics** — GA4 + product analytics (Amplitude / Mixpanel / Heap) + BI (Looker / Mode / Hex / Tableau)
6. **Attribution** — standalone layer (Northbeam / Triple Whale / Rockerbox / Measured / Haus / in-house MMM)
7. **Email / SMS / push (ESP)** — Klaviyo (DTC), Braze (enterprise multi-channel), Iterable (mid-market), HubSpot (B2B), Customer.io
8. **CRM** — Salesforce / HubSpot / Pipedrive (B2B); or overlap with ESP (B2C often doesn't need standalone CRM)
9. **Website / CMS** — Shopify / Headless (Next.js + PIM), WordPress (B2B), custom
10. **Personalization** — Dynamic Yield / Monetate / Bloomreach (if at scale); or home-built on warehouse
11. **Support** — Gorgias / Zendesk / Intercom / Help Scout
12. **Feedback / reviews** — Yotpo / Okendo / Stamped / Trustpilot / in-native-platform
13. **Loyalty** — LoyaltyLion / Yotpo Loyalty / Smile (if program needed)
14. **Subscription** — Recharge / Stay AI / Smartrr / Ordergroove (if applicable)
15. **Testing** — VWO / Convert / Optimizely / Statsig / LaunchDarkly
16. **Creator / influencer** — Grin / Aspire / Creatable (if program needed)

### Consolidation priorities

- **Remove:** tools with <3 active users; tools with duplicate capability; tools with sub-30-day time-to-value that never materialized
- **Consolidate:** multiple analytics tools doing overlapping work; ESP + CRM when one can do both (B2C); CDP + ESP when warehouse can serve
- **Upgrade:** ESP on same-vendor family (Klaviyo free → paid); warehouse from shared to dedicated when scale requires

### Data hygiene

- **PII handling:** documented, compliant with GDPR / CCPA / state laws
- **Consent management:** OneTrust / Transcend / Didomi; consent propagates to CDP → ESP → activation
- **Identity resolution:** email + phone + device IDs + customer ID; merged in warehouse
- **Data governance:** data dictionary, data lineage, data quality monitoring

### Vendor management

- **Annual audit:** tools in use vs. paid for (typical waste: 20-40% of tool spend)
- **Renewal calendar:** 90 days before each renewal, evaluate alternatives + negotiate
- **Kill switch:** every tool has a documented migration path; no indispensable vendors

## Step 0 — Interview question additions

1. **Current tool inventory** — list every martech / data / ops tool + monthly cost + # of users
2. **Warehouse status** — in place? What platform? Who owns?
3. **CDP status** — tool, vendor, coverage, identity-resolution depth
4. **ESP + CRM** — tools, overlap, redundancy
5. **Analytics stack** — which tools, what's duplicative?
6. **Attribution** — standalone or embedded? Quality?
7. **Pain points** — where do people complain? What breaks? What takes too long?
8. **Integration tax** — which integrations are fragile / manual / expensive?
9. **Data team + ownership** — who manages the warehouse + pipelines?
10. **Compliance posture** — GDPR / CCPA / HIPAA / PCI — any gaps?
11. **Annual tool budget** — total spend + growth trajectory
12. **Recent tool failures** — vendors dropped? Migrations? Lessons?

## Step 2 — Milestone template (16-week program)

```markdown
### M1 — Stack Audit (week 1-3)
- Deliverable: complete tool inventory; usage analysis; redundancy map; pain-point interviews
- Validation: every tool accounted for, categorized, scored
- Target: end of week 3

### M2 — Target State Architecture (week 3-5)
- Deliverable: target stack design; data-flow architecture; consolidation recommendations; kill list
- Validation: stakeholder sign-off; vendor-sequence decided
- Target: end of week 5

### M3 — Foundation Rebuild (warehouse + CDP + identity) (week 5-10)
- Deliverable: warehouse operational; CDP live; identity resolution working
- Validation: first data flows working end-to-end; identity merge rate measured
- Target: end of week 10

### M4 — Tool Consolidation (week 8-14)
- Deliverable: redundant tools sunset; consolidated vendors live; integrations rebuilt on warehouse
- Validation: every sunset tool migration complete; no data gaps
- Target: end of week 14

### M5 — Activation Layer (week 12-16)
- Deliverable: ESP + personalization + attribution + testing on new stack
- Validation: end-to-end user journey flows through new stack
- Target: end of week 16

### M6 — Governance + Documentation (ongoing)
- Deliverable: data dictionary, runbooks, vendor management, renewal calendar
- Validation: team can operate without external help
- Target: week 16+
```

## Step 3 — Critical mental model

> **The martech stack is not a collection of tools; it's a single system.**
>
> Individual tool purchases feel small. "Let's add a tool to solve X." But every addition multiplies: new integration, new user list, new identity model, new data-flow, new renewal, new security review, new training.
>
> The compound tax is invisible until you audit it. Typical finding: 40-70% of tool spend is waste (duplicate capability, unused licenses, broken integrations, "we still pay for this?"). Typical second finding: 30-50% of team time is spent on tool-gymnastics rather than customer work.
>
> Healthy stacks are designed as systems: warehouse-centered, with tools as peripherals that read/write from the warehouse, not from each other. Unhealthy stacks grow through point-purchases; each one fixes one problem and creates three.

## Step 4 — Domain validators

- **Tool inventory:** complete, accurate, cost-documented
- **Usage analysis:** every tool has documented active-user count + value assessment
- **Data flow:** diagram shows how data moves; every tool has documented inputs/outputs
- **Integration health:** no manual data movement; no brittle custom integrations
- **Governance:** data dictionary, data-lineage, data-quality monitoring in place

## Step 8 — Working protocol additions

- **Never add a tool without killing one** — hold the stack count flat or shrinking
- **Never let a tool live beyond its 90-day time-to-value** without explicit renewal decision
- **Never integrate tool-to-tool directly** — always through warehouse or CDP
- **Never onboard without kill-switch plan**
- **Always review annual renewals 90 days out** — don't auto-renew
- **Always document integration ownership** — who fixes when it breaks
- **Always monitor data-quality** — bad data propagates silently

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — attribution-layer design patterns
- `{{KNOWLEDGE_BASE_ROOT}}/ai-engineering/wiki/_index.md` — for AI / LLM additions to the stack

## Common example fills

- **"Audit + consolidate $500K/year martech spend at $50M DTC brand — 47 tools → target 25 tools, warehouse-centric"**
- **"Rebuild data infrastructure — from platform-locked (Klaviyo-owned data) to warehouse-first with Segment + Snowflake"**
- **"Implement CDP for the first time at $80M DTC brand currently running on ESP-only data"**
- **"Sunset legacy tools post-acquisition — merge two stacks into unified system"**
- **"B2B SaaS martech rebuild — HubSpot over-stretched; decide Salesforce + dedicated-ESP vs. HubSpot Pro + CDP"**

## Hand-off

After bootstrap, use `~/.claude/templates/growth-ecommerce/martech-stack/resumption.md`.
