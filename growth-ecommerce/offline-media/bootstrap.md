# Offline / Traditional Media Program — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** launching or overhauling offline media — direct mail, OOH (out-of-home / billboards), TV (linear + CTV), radio, print, audio (podcast, streaming).

---

## Who this is for

Growth leaders, brand managers, performance-marketing leads at DTC / consumer brands ready to add offline channels to a predominantly-digital stack. Typically considered at $30M+ annual revenue when digital saturation or CAC inflation makes offline economics attractive.

## Opinionated defaults

### Channel fit

- **Direct mail:** strong for DTC with clear targeting data; 1-3% response rates typical; retargeting lift 10-30%
- **OOH / billboards:** awareness + brand-building at scale; measure on brand lift, not direct response
- **CTV (Connected TV):** growing; measurable via platform (Roku, Amazon Fire TV, YouTube) — ROAS trackable
- **Linear TV:** still works for mass brands with $2M+ annual spend minimum; above-the-fold national + regional
- **Radio / streaming audio:** operator-targeted podcasts > broad radio; host-read > produced spots
- **Print:** category-dependent; magazines work for premium brands + industry journals for B2B
- **Podcast advertising:** host-read performs 5-10× produced; operator-aligned shows preferred

### Direct mail benchmarks

- **Response rate: 1-3% cold; 3-8% retargeting existing visitors**
- **Revenue per piece: $0.50-$5 across categories (category-specific)**
- **Mailing frequency: every 6-8 weeks for retargeting; less frequent for cold**
- **Personalization impact: +20-40% on response rate when done well**
- **Trigger-based DM (abandoned cart, post-purchase)** outperforms batch by 3-5×

### OOH / billboards

- **Measure on brand lift** (aided + unaided awareness), not direct response
- **Geo-targeted CTV + digital retargeting** amplifies OOH by tying online behavior to offline exposure
- **Category-specific placement** (tech near tech corridors, consumer near retail corridors)
- **Creative simplicity:** 6 words max for driving-by readability
- **Programmatic OOH (Vistar, Place Exchange)** enables digital-style buying + measurement

### CTV benchmarks

- **ROAS benchmarks:** comparable to Meta / YouTube for DTC at scale
- **Platform-specific:** Roku / Amazon Fire TV / YouTube CTV / Hulu / streaming bundles
- **Measurement:** platform attribution + incrementality testing (most platforms support)
- **Creative: 15s / 30s / 60s;** 15s for reach, 30s for story, 60s for complex products

### Linear TV

- **Minimum viable scale: $2-$5M/year** to be meaningful
- **Dayparts:** prime-time CPMs high; late-night + sports for efficient reach
- **DR-style (direct-response) vs. brand TV:** different creative, different buying model, different measurement
- **Measurement:** brand-tracking + MMM essential; MTA can't measure TV

### Podcast advertising

- **Host-read: 5-10× produced spot performance**
- **Operator-aligned shows:** shows whose hosts + audiences match your ICP
- **Category-specific shows:** Lenny's Podcast (PLG B2B SaaS), Operators (DTC), 2X eCommerce — predictable audiences
- **Measurement:** promo codes + UTMs + brand-lift studies; attribution is weak without intentional capture
- **Spend: $25-$80 CPM typical; premium shows $100-$200+ CPM**

### Don'ts

- **Don't run offline without incrementality plan** — MTA undermeasures offline materially
- **Don't expect last-click attribution** to work — offline is brand + assist, not direct-response
- **Don't scale too fast** — creative fatigue and audience saturation are brutal in offline
- **Don't skip geo-coverage planning** — regional inefficiency is common
- **Don't launch direct mail without suppression logic** — mailing customers who just ordered is waste

## Step 0 — Interview question additions

1. **Which channels in scope** — direct mail, OOH, CTV, linear TV, radio, print, podcast?
2. **Current digital saturation signal** — CAC inflation, CPM trends, platform performance?
3. **Incrementality testing capability** — geo-holdout, matched-market, MMM?
4. **Creative production capacity** — in-house, agency, hybrid?
5. **Measurement infrastructure** — MMM, brand-tracker, incrementality?
6. **Budget envelope** — per-channel + annual
7. **Target markets** — national, regional, metro-level?
8. **Existing agency relationships** — media buying, creative?
9. **Past offline history** — tried, results, lessons learned?
10. **Category context** — regulatory constraints (pharma, financial, political)?

## Step 2 — Milestone template (20-week program)

```markdown
### M1 — Channel Strategy + Measurement (week 1-3)
- Deliverable: channel mix decision; budget allocation; measurement plan (incrementality + MMM + brand tracker)
- Validation: strategy aligned with goals; measurement baseline captured
- Target: end of week 3

### M2 — Creative Development (week 3-8)
- Deliverable: creative assets per channel + creative testing framework
- Validation: creative tested with lift studies (if scale permits) or qualitative review
- Target: end of week 8

### M3 — Launch + Geo-Holdout Setup (week 8-10)
- Deliverable: channels live; geo-holdout test designed; baseline data captured
- Validation: campaigns running; holdout period defined
- Target: end of week 10

### M4 — Scale Phase (week 10-18)
- Deliverable: budget scaling on validated performers; creative iteration; coverage expansion
- Validation: incrementality positive; brand-tracker trending up; CAC improving or stable
- Target: end of week 18

### M5 — Retrospective + Decision (week 18-20)
- Deliverable: channel-by-channel performance review; scale / hold / cut decisions
- Validation: data-driven conclusions; next-phase plan
- Target: end of week 20
```

## Step 3 — Critical mental model

> **Offline is a brand + assist channel; digital MTA will under-measure it.**
>
> Offline channels produce two things: (1) brand lift that compounds over time, (2) assist value that amplifies digital performance. Neither shows up cleanly in last-click MTA. Brands that measure offline on platform-reported metrics consistently under-invest and exit too early.
>
> The two things offline requires to work:
>
> 1. **Incrementality testing** (geo-holdout, matched-market, or MMM) — the only way to know if offline is contributing
> 2. **Patience** — brand lift takes 6-12 months to compound; direct response takes 3-6 months to stabilize
>
> If you can't commit to both, don't launch offline. You'll kill it before it works.

## Step 4 — Domain validators

- **Incrementality plan documented** — not optional
- **Brand-tracker baseline** before launch
- **Creative approval by brand + legal** — category risks (health claims, financial claims)
- **Geo-coverage verified** — not paying for markets without inventory
- **Frequency caps and suppression** in place for direct mail / CTV

## Step 8 — Working protocol additions

- **Never launch offline without incrementality plan**
- **Never measure offline on last-click alone**
- **Never scale offline before incrementality validates it**
- **Never skip brand-tracker baseline**
- **Always budget for creative iteration** — fatigue is real
- **Always coordinate offline with digital** — offline amplifies digital, not replaces it
- **Always run regional holdout** if geo-based channel

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — **20 articles on attribution + channel response; critical for offline measurement**
- `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/wiki/_index.md` — creative strategy frameworks

## Common example fills

- **"Launch direct mail program for $80M DTC brand — trigger-based + cold mailing; $100K/mo test"**
- **"Add CTV to digital-only media mix — $2M/year starting budget; Roku + Amazon Fire TV + YouTube CTV"**
- **"Linear TV launch for $50M CPG brand — national cable + regional broadcast; $5M/year"**
- **"Podcast advertising program for B2B SaaS — 10-15 operator-aligned shows; host-read focus; $500K/year"**
- **"OOH test in 3 markets — digital-amplified billboards + brand-lift study"**

## Hand-off

After bootstrap, use `~/.claude/templates/growth-ecommerce/offline-media/resumption.md`.
