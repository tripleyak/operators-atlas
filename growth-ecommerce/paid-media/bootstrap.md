# Paid Media Program — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** starting a multi-session paid-media program — Meta, Google, TikTok, programmatic, or cross-channel scale-up / restructure / optimization.
>
> **Run the master bootstrap first, then apply these domain specializations.**

---

## Who this is for

Growth marketers, performance-media managers, paid-acquisition leads at DTC brands, B2B SaaS PLG teams, subscription businesses, or agencies running paid media for clients. The program typically spans 8-16 weeks for a structured scale-up, or 12+ weeks for a full account restructure.

## Opinionated defaults (non-negotiable starting points — override only with reason)

### Measurement

- **Blended MER is primary; platform ROAS is diagnostic.** Budget decisions are made on blended, not siloed.
- **MTA + MMM shown side-by-side always.** Never make a channel allocation decision on one view alone.
- **Attribution window:** 7-day click / 1-day view for paid social; 30-day click for search (adjust per platform default only with reason).
- **Daily MER reporting; weekly channel-level; monthly MMM refresh.**

### Testing discipline

- **Learning phase respect:** ≥50 conversions in 7 days before algorithm-optimization claims are trusted.
- **No stop-start within learning phase.** If a campaign is underperforming in learning, let it finish or kill it entirely — do not toggle.
- **Creative test matrix:** 4x4 minimum (4 audiences × 4 creatives) per test wave.
- **Creative refresh cadence:** 30-day budget allocation for new creative per major channel.
- **Kill losers:** anything <0.5× target MER for 14 days straight → pause.

### Scaling

- **Scale ladder:** ≤20% budget increase per 72 hours per campaign to preserve algorithm stability.
- **CAC payback:** <90 days for existing-channel new customers, <180 days for new-channel launches.
- **Channel expansion gate:** new channel only after primary channel hits target CAC payback with ≥60 days of data.

### Account hygiene

- **Pixel installed, firing, and de-duplicated** (server-side where possible — CAPI for Meta, GA4 Measurement Protocol / Enhanced Conversions for Google).
- **Naming taxonomy:** `{brand}_{channel}_{objective}_{audience}_{creative-theme}_{date}` or equivalent; enforced across all campaigns.
- **Budget pacing check daily;** within ±10% of weekly target.
- **Frequency caps** at campaign level for retargeting (3-5 per 7 days typical).

## Step 0 — Interview question additions (ask in addition to master Step 0)

1. **Current blended MER / ROAS / CAC** — most recent complete month. If unknown, this is the first unknown to eliminate.
2. **Target MER / CAC / payback period** — what economic output does the program need to hit?
3. **Channel mix** — current spend distribution; any channels under-spent / over-spent vs. opportunity?
4. **Agency / in-house / hybrid** — who executes, who decides, who has platform access?
5. **Attribution model in use today** — last-click, LTV-adjusted, MTA vendor, MMM, "vibes"? What's the gap?
6. **Creative supply** — how many new creatives ship per week? Who produces? Any creative-testing framework in use?
7. **MMM status** — have a model? When last updated? Who owns?
8. **Incrementality history** — ever run a geo or holdout test? Results?
9. **Seasonality / cyclical factors** — is this a gift/holiday-sensitive business? Q4/Prime Day?
10. **Platform account health** — any account bans, policy strikes, content-review issues?

## Step 2 — Milestone template (pre-fill Plan.md with this)

Standard 12-week paid-media program. Compress or extend per scope.

```markdown
### M1 — Baseline + Instrumentation Audit (week 1)
- Deliverable: Baseline MER/CAC by channel; pixel/attribution audit report
- Validation: Blended-MER dashboard refreshes daily; pixel CAPI/server-side firing verified
- Target: end of week 1

### M2 — Account Restructure + Taxonomy (week 2-3)
- Deliverable: Campaigns renamed; taxonomy enforced; budget pacing automated
- Validation: All active campaigns follow `{brand}_{channel}_{objective}_{audience}_{creative}_{date}` pattern; daily-pacing alert live
- Target: end of week 3

### M3 — Creative Testing Framework Launch (week 3-4)
- Deliverable: 4x4 matrix live; test documentation template; creative brief library
- Validation: 16+ ad variants live in test; readouts scheduled
- Target: end of week 4

### M4 — Audience Expansion Tests (week 4-6)
- Deliverable: New-audience tests launched; lookalike / interest / broad strategy
- Validation: 3+ audience tests each at ≥$X daily; MER by audience reported
- Target: end of week 6

### M5 — Scale Ladder to Target MER (week 6-12)
- Deliverable: Winning creatives + audiences scaled per 20%/72h ladder
- Validation: Blended MER trending to target; no more than 10% campaigns flagged as under-performing
- Target: end of week 12

### M6 — Handoff / Runbook (week 12+)
- Deliverable: Runbook for ongoing ops; weekly review cadence locked
- Validation: Team can run the program without external help
- Target: end of week 13
```

## Step 3 — Critical mental model (pre-fill Implement.md with this)

> **Platform ROAS ≠ incremental ROAS. Blended MER is the business reality.**
>
> Every paid-media channel over-reports its own contribution — platform attribution windows, click-biased models, and auto-bidding algorithms all inflate platform-reported ROAS.
>
> The business only has one pool of revenue and one pool of spend. Blended MER (total revenue / total paid spend) is the only number that reconciles to the bank. Channel-level ROAS is useful for diagnosing *why* blended MER moved, but it is never the decision number.
>
> When a channel's platform ROAS rises while blended MER falls, the channel is cannibalizing, not incrementing. Kill the cannibalization even if the platform dashboard says "scale up."

## Step 4 — Domain-specific validators

Run these checks at every milestone:

- **Pixel health:** `{pixel helper or CAPI debug tool}` — verify fire + deduplication
- **Conversion match rate:** Platform events vs. GA4 vs. Northbeam vs. bank revenue — within ±15%
- **MER dashboard refresh:** `{dashboard URL}` — daily refresh timestamp <24h old
- **Budget pacing:** weekly spend within ±10% of target
- **Taxonomy compliance:** `{taxonomy-audit query}` — 100% of active campaigns match pattern
- **Account health:** platform restrictions / policy strikes = 0

## Step 8 — Domain-specific working protocol additions

Add to Implement.md "Non-negotiable rules":

- **Never toggle a campaign during learning phase** — let it finish (≥50 conv/7d) or kill entirely
- **Never scale >20% in 72h** — preserves algorithm stability
- **Never cut a test <2 weeks old** — insufficient signal
- **Never change attribution settings mid-test** — invalidates the test
- **Always show MTA + MMM side-by-side** in any channel-allocation decision
- **Always archive paused campaigns** within 14 days — keeps account hygiene clean
- **Always document a hypothesis before a test;** no fishing expeditions

## KB integration

Read before starting work on this program:

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — 20 articles on MMM, Hill curves, mROAS (foundational for the decision framework)
- `{{KNOWLEDGE_BASE_ROOT}}/amazon-ads/wiki/_index.md` — 32 articles on Amazon PPC (if Amazon is in the mix; PPC architecture patterns transfer conceptually)
- `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/wiki/_index.md` — competitor creative / positioning benchmarks

If any referenced wiki is missing: flag in `Documentation.md` as a known gap; continue with external sources.

## Common example fills

- **"Scale Meta + Google from $80K/mo to $250K/mo while holding blended MER ≥ 2.8"**
- **"Restructure underperforming Meta account — blended MER 1.4 → target 2.5 — full teardown + rebuild"**
- **"Launch TikTok as a new channel at $20K/mo test, kill/double-down decision at Day 60"**
- **"Migrate from agency-run to in-house paid media over 16 weeks"**
- **"Diagnose blended MER collapse from 3.1 to 2.0 over last 90 days; prescribe remediation"**

## Hand-off to resumption

After bootstrap completes, use `~/.claude/templates/growth-ecommerce/paid-media/resumption.md` for sessions 2+.
