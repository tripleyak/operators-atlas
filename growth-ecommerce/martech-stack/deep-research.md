# Martech Stack — Deep Research Template

> **Inherits from:** `~/.claude/templates/deep-research-technical-reference.md` (primary) or `deep-research-competitive-landscape.md` (for vendor shortlisting)

---

## Use cases

- **Stack architecture research** — canonical patterns for DTC / B2B SaaS / marketplace stacks
- **Vendor evaluation** — specific tool comparison in a category
- **CDP vs. warehouse-as-CDP research** — when to use packaged CDP vs. Hightouch / Census pattern
- **Data-infrastructure research** — Snowflake vs. BigQuery vs. Redshift vs. Databricks vs. Clickhouse at your scale
- **Migration research** — moving from one tool to another; documented case studies
- **Integration research** — specific integration patterns (ESP + CRM, CDP + ESP, Warehouse + Attribution)

## Opinionated source priorities

**Prioritize:**

- **Vendor engineering blogs** — Segment's CDP technical writing, Fivetran's pipeline architecture posts, Snowflake's data-cloud architecture
- **Operator case studies** — engineering-team postmortems on migrations (Zapier's move off X, Shopify's internal platform, etc.)
- **Industry analysts** — Gartner Magic Quadrants for CDP / ESP / attribution / analytics (if accessible)
- **Modern data stack publications** — Benn Stancil's Substack, the dbt Labs blog, Fivetran's "Data Cloud" content
- **Conference talks** — Coalesce (dbt), Modern Data Stack Conference, Martech conferences with engineering tracks
- **Stack Overflow / technical Reddit** — real integration issues surface here before vendor marketing addresses them

**De-prioritize:**

- Vendor marketing "why you need X" content
- Consultant-published "future of martech" reports
- Generic martech newsletter roundups

## Question-set specializations

### For stack architecture:

1. Canonical stack for target company profile (scale, vertical, stage)
2. Data flow — sources → ELT → warehouse → CDP → activation
3. Identity resolution approach
4. Privacy / consent architecture
5. Attribution integration
6. AI / personalization layer placement
7. Cost structure at scale
8. Common anti-patterns to avoid

### For vendor evaluation (technical archetype):

Use `deep-research-technical-reference.md` specializations. Specific additions:

1. Data ingestion capability (sources, speed, reliability)
2. Data activation (destinations, real-time vs. batch)
3. Identity resolution (match rate, merge logic)
4. Privacy / consent propagation
5. Cost model (per-record, per-destination, seat-based)
6. Integration ecosystem depth
7. Customer support + documentation quality
8. Operator UX (is it usable by marketer or requires engineer?)

### For CDP vs. warehouse-as-CDP:

1. Scale breakpoints where each pattern wins
2. Cost comparison at 100K / 1M / 10M / 50M records
3. Integration-ecosystem comparison
4. Real-time vs. batch tradeoffs
5. Privacy / consent handling comparison
6. Team expertise requirements (data engineers needed for either?)
7. Migration risk if switching approaches later

### For data-infrastructure:

1. Performance at your scale profile (query speed, concurrency)
2. Pricing model — compute-separated vs. bundled
3. Ecosystem — tools that integrate natively
4. Data-governance features (lineage, privacy, access control)
5. Multi-region / compliance readiness
6. Operator experience — does marketing touch it, or only data team?

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — attribution-layer integration
- `{{KNOWLEDGE_BASE_ROOT}}/ai-engineering/wiki/_index.md` — AI / LLM tool integration patterns

## Example filled-in briefs

- "Research canonical martech stack for $50-$200M DTC brand — warehouse choice, CDP decision, ESP, attribution, analytics; documented-case-study brands at this scale"
- "Evaluate Segment vs. Rudderstack vs. Hightouch-as-CDP for $75M DTC brand with existing Snowflake — technical fit, cost, migration complexity"
- "Research Snowflake vs. BigQuery vs. Clickhouse for DTC at $100M revenue with high-cardinality customer event data — performance, cost, ecosystem"
- "Research CDP vs. warehouse-as-CDP transition — which scale profile justifies the switch, documented-case-study migrations"
- "Research Klaviyo → Braze migration — cost, feature parity, data preservation, migration time, published case studies"
- "Research HubSpot-one-vendor vs. Salesforce-plus-ESP stack for B2B SaaS at 200-500 employees — cost, functional gaps, integration tax"
