# Amazon — Deep Research Template

> **Inherits from:** `~/.claude/templates/deep-research-competitive-landscape.md` or `deep-research-technical-reference.md`

---

## Use cases

- **Amazon-native tool evaluation** — Helium10 vs. JungleScout vs. SmartScout vs. DataDive vs. Perpetua vs. Pacvue
- **Category competitive research** — top-N competitors on your target keywords, their listings, their PPC patterns
- **New category / new-SKU launch research** — demand validation, competitive intensity, review landscape
- **Amazon algorithm / feature change research** — COSMO, SQP, A10, new ad formats, Buy Box logic
- **Q4 / Prime Day strategy research** — category-level benchmarks, historical deal effectiveness
- **Vendor vs. Seller Central analysis** — pros / cons / migration implications

## Opinionated source priorities

**Prioritize:**

- **Amazon official sources** — Seller Central forums, Amazon Advertising official docs, Amazon Brand Registry blog
- **Amazon-native tool blogs** — Helium10, JungleScout, SmartScout, DataDive, Perpetua, Pacvue (bias toward their own tools; still useful for category data)
- **Amazon-specialist podcasts** — Seller Sessions, Amazon FBA Podcast, The Firing Squad, My Amazon Guy
- **SEC filings / earnings** — Amazon.com quarterly earnings (Ads is a growing segment, increasingly disclosed)
- **Academic research on marketplace dynamics**
- **Operator communities** — r/FulfillmentByAmazon, r/AmazonSeller, Amazon-specific Slack / Discord groups

**De-prioritize:**

- Generic "how to sell on Amazon" listicles
- Course-seller content (motivated sales bias)
- AI-generated Amazon blog content (rampant)
- Pay-for-review review-aggregator sites

## Question-set specializations

### For Amazon-native tool evaluation:

1. Feature comparison — keyword research, PPC management, listing optimization, review monitoring, competitor intelligence, SP-API integration
2. Data source — which tools have SP-API read access, which scrape, which mix
3. Accuracy benchmarks — how often does BSR / search volume / competitor data differ from ground truth?
4. Pricing — tier, per-account vs. per-marketplace, enterprise tier
5. PPC bid automation — rules-based, ML-based, open box?
6. Integration depth — does it work with your warehouse / analytics / finance stack?
7. Scale ceiling — does it work for single-brand, multi-brand, aggregator?
8. Customer quality — what operator profile uses it, with what success?

### For category competitive research:

1. Top-10 SKUs by BSR in category — who are they, when launched, review count, rating?
2. Average price, price dispersion, AOV in category
3. Review velocity benchmarks — top-5 vs. median vs. new entrant
4. PPC intensity — estimate via Helium10 / JungleScout / SmartScout cost estimates
5. A+ Content adoption in category
6. Video content — % of SKUs with video
7. Brand Registry adoption — which competitors have brand tools, which don't
8. Amazon private label / Basics presence in the category
9. Seasonality pattern — monthly demand curve
10. Recent new entrants — who launched in last 12 months, how are they performing

### For algorithm / feature change:

Use `deep-research-technical-reference.md`. Specifically:

1. What changed at the mechanism level (indexing, ranking signals, ad serving)?
2. Who's published measured impact (not speculation)?
3. What's the operator-facing remediation playbook?
4. Official Amazon documentation (Seller Central help articles update continuously; timestamp matters)
5. Rollout timeline — is this category-wide or phased?

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/amazon-ads/wiki/_index.md` — **32 articles; primary reference for PPC architecture questions**
- `{{KNOWLEDGE_BASE_ROOT}}/amazon-product-launches/wiki/_index.md` — **9 articles; primary reference for launch playbooks**
- `{{KNOWLEDGE_BASE_ROOT}}/amazon-developer-tools/wiki/_index.md` — **15 articles; SP-API, MCP, catalog CLI**

Cite specific KB articles in the Methodology section.

## Example filled-in briefs

- "Research the top 10 Amazon private-label brands in women's active / athleisure category as of {{date}} — launch timeline, review velocity, PPC intensity, category share"
- "Evaluate Helium10 vs. Perpetua vs. in-house PPC automation for a $10M/yr Amazon brand — feature parity, cost, operator time savings"
- "Research Amazon COSMO algorithm rollout impact on ecommerce SKU ranking — pre/post analysis at peer brands, what signals are more / less important"
- "Research Amazon Vendor-to-Seller Central transition playbook — published case studies, migration timelines, revenue impact patterns"
- "Research Q4 2025 Amazon Prime Day + Black Friday performance benchmarks by category — deal-type ROI, inventory planning signals, PPC CPM patterns"
- "Research the emerging Amazon Posts + Brand Story feature adoption — which brands, which verticals, measured lift / vanity metric?"
