# Offline / Traditional Media — Deep Research Template

> **Inherits from:** `~/.claude/templates/deep-research-competitive-landscape.md` or `deep-research-technical-reference.md`

---

## Use cases

- **Channel feasibility research** — should we launch TV / CTV / OOH / podcast / direct mail?
- **Vendor / agency evaluation** — media-buying agencies, DM vendors, CTV platforms, podcast networks
- **Incrementality methodology** — geo holdout, matched-market, MMM specifics for offline
- **Category benchmarks** — CPM, response rates, ROAS benchmarks by channel + category
- **Creative strategy research** — what formats, lengths, host-read vs. produced for podcasts
- **Competitor offline strategy teardown** — who's on TV, CTV, podcasts; how much and where

## Opinionated source priorities

**Prioritize:**

- **iHeartMedia / Triton / Edison Research** — audio + podcast benchmarks
- **Magna Global / Group M / Publicis Groupe** — media-spend benchmarks + industry forecasts
- **Nielsen Scarborough** — demographic + consumption data
- **OOH specialists** — OAAA (Outdoor Advertising Association of America), Vistar Media
- **DMA (Data & Marketing Association)** — direct mail benchmarks
- **CTV publisher reports** — Roku, Amazon Advertising, Samsung Ads, Hulu / Disney+ advertising
- **Haus, Measured, Recast** — attribution + incrementality methodology for offline

**De-prioritize:**

- Broadcast network sales decks
- Agency-published "why TV works" marketing
- Generic OOH listicles

## Question-set specializations

### For channel feasibility:

1. Category benchmarks — has your category's peer brands used this channel at scale? Results?
2. CPM + ROAS benchmarks at your scale band
3. Attribution weakness — can you measure? Geo-holdout feasible?
4. Creative production cost — in-house vs. agency
5. Minimum viable scale in this channel
6. Incrementality test published at peer brands
7. Time-to-measurable-result

### For vendor evaluation:

1. Platform / agency track record at your scale
2. Pricing model + transparency (especially TV: programmatic vs. direct, markup + fees)
3. Measurement + attribution capability
4. Geo + demographic targeting depth
5. Creative support (in-house vs. require your own)
6. Customer references + published results
7. Exit / switching cost

### For incrementality methodology:

1. Geo-holdout design for your brand (regional variance? test-market design?)
2. Matched-market methodology + when it works
3. MMM integration — can the channel-specific data feed your MMM?
4. Platform-provided measurement — which platforms have meaningful test tools?
5. Brand-lift study design — Nielsen / Kantar / in-house

### For competitor teardown:

1. TV / CTV spend visibility (iSpot.tv, SMI data, analyst reports)
2. OOH placement tracking (Vistar, Outfront, Clear Channel data)
3. Podcast advertising visibility (Podscribe, Magellan, manual tracking)
4. Direct mail tracking (Harvested from mailer-swap groups, operator reports)

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — **20 articles, critical for offline attribution + incrementality**
- `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/wiki/_index.md` — creative strategy frameworks

## Example filled-in briefs

- "Research CTV landscape for $50M DTC brand — Roku vs. Amazon Fire TV vs. YouTube CTV vs. Hulu; CPM, targeting, measurement, typical ROAS"
- "Evaluate direct mail vendors for retargeting program — Lob / PostPilot / PFL / USPS Every Door Direct Mail — integration, pricing, targeting"
- "Research podcast advertising landscape for B2B SaaS — top 50 operator-aligned shows; CPMs; host-read benchmarks"
- "Research incrementality methodology for brands without geo-variance (national DTC with same SKU everywhere) — test alternatives, matched-market, ghost bidding"
- "Teardown of competitor offline strategy — $100M DTC brand's TV + podcast + OOH spend; markets, creative, measurement"
- "Research OOH measurement + attribution 2026 — programmatic OOH platforms (Vistar, Place Exchange), brand-lift studies, digital-amplification impact"
