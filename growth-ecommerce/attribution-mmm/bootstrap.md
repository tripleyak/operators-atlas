# Attribution / MMM Program — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** starting a multi-session attribution or measurement program — MTA → MMM migration, MMM build from scratch, incrementality program, or measurement methodology overhaul.

---

## Who this is for

Analytics / data-science / growth-leadership at DTC, ecommerce, subscription, or B2B companies with >$5M annual paid spend where channel-allocation decisions matter. Also applies to agencies selling MMM-as-a-service. Programs span 10-16 weeks for a first MMM build, or 16-24 weeks for a full MTA retirement with parallel MMM buildup.

## Opinionated defaults

### Measurement philosophy

- **MMM answers "how should I allocate budget?"** — channel-level incrementality, diminishing returns, saturation curves
- **MTA answers "which touchpoint gets credit?"** — diagnostic, not decision-making
- **Never use MTA for budget allocation decisions.** Use it for creative optimization and tactical diagnostics.
- **Always cross-validate:** platform-reported ROAS vs. MMM-modeled vs. bank revenue. ±15% reconciliation target.

### MMM build discipline

- **Hill saturation curves for channel response** (or equivalent — adstock + saturation)
- **Minimum data: 2 years weekly data if available; 18 months acceptable; 12 months marginal**
- **Refresh cadence: quarterly minimum; monthly for high-velocity businesses**
- **Priors: use platform spend + attribution as priors, not ground truth**
- **Cross-validation: 80/20 train/test; RMSE + MAPE reported; hold-out period tested**

### Incrementality

- **Parallel incrementality tests validate MMM quarterly** — geo holdouts, ghost bidding, or light-hold
- **Never skip the incrementality check** — MMM drifts without it
- **Brand campaigns: separate measurement** — MMM alone under-credits brand; overlay with brand-lift studies

### Migration from MTA

- **MTA and MMM run parallel 90+ days minimum before MTA retirement**
- **Dashboards carry both views** during migration (teams panic without familiar MTA numbers)
- **Budget decisions migrate to MMM first; reporting migrates last**
- **Document the new decision rules** — people need to learn how to read MMM output

### Governance

- **Model documentation required** — priors, data sources, seasonality handling, known limitations
- **Confidence intervals reported on all outputs** — point estimates alone hide model uncertainty
- **Stakeholder training** — CMO / VP Growth / CFO need to read MMM output before decisions rest on it

## Step 0 — Interview question additions

1. **Current attribution model** — platform last-click, last-touch MTA, MMM, or mixed?
2. **Data infrastructure** — warehouse? (Snowflake / BigQuery / Redshift / Databricks) — source-of-truth for spend + revenue?
3. **Data completeness** — how many weeks of history do we have across all channels?
4. **Channel set** — which channels get measured, which are black boxes?
5. **Offline / retail mix** — how much of revenue is non-digital? (affects attribution complexity)
6. **Incrementality history** — ever run holdouts? Results?
7. **Stakeholder mapping** — who makes budget decisions? What do they trust?
8. **Compliance / privacy** — iOS impact, cookie deprecation, first-party data maturity
9. **Current dashboards** — Northbeam / Triple Whale / Prescient / Haus / Recast / custom?
10. **Seasonality structure** — Q4-heavy? Summer / back-to-school? Day-of-week patterns?

## Step 2 — Milestone template (16-week program)

```markdown
### M1 — Data Infrastructure Audit (week 1-2)
- Deliverable: data source inventory; warehouse access confirmed; historical-data quality report
- Validation: can pull last 24 months of spend + revenue by channel in one query
- Target: end of week 2

### M2 — Data Pipeline + Feature Engineering (week 2-4)
- Deliverable: cleaned spend + revenue + seasonality + external-factor features; canonical dataset
- Validation: data reconciles to bank within ±2%; no missing weeks
- Target: end of week 4

### M3 — First MMM Build + Validation (week 4-8)
- Deliverable: first model run; hill curves fit; contributions report; cross-validation metrics
- Validation: 80/20 cross-val RMSE acceptable; predictions within ±20% of actual
- Target: end of week 8

### M4 — Parallel Run with MTA + Reconciliation (week 8-12)
- Deliverable: dashboards showing MMM + MTA side-by-side; reconciliation dashboard vs. bank
- Validation: stakeholders receive both views weekly; no budget decisions made yet
- Target: end of week 12

### M5 — Decision Framework + Training (week 12-14)
- Deliverable: decision rules documented; stakeholder training delivered; first MMM-based budget allocation
- Validation: stakeholders demonstrate reading MMM outputs correctly
- Target: end of week 14

### M6 — Incrementality Test + Quarterly Refresh Cadence (week 14-16)
- Deliverable: first incrementality test completed; quarterly refresh rhythm locked
- Validation: incrementality aligned with MMM within ±25%; refresh runs autonomously
- Target: end of week 16
```

## Step 3 — Critical mental model

> **Attribution is a model, not a truth. All attribution is wrong; some is useful.**
>
> MMM is a statistical approximation of incrementality at the channel level — it gets directionally right the answer to "should I shift $1 from A to B?" — even though it cannot tell you "this specific conversion came from this specific touchpoint."
>
> MTA is a credit-assignment model — it partitions revenue across touchpoints using heuristics (last-touch, linear, time-decay, algorithmic). It tells you nothing about incrementality. A channel can look great in MTA (high last-click conversions) and be entirely cannibalistic in incrementality (those people would have bought anyway).
>
> **Don't confuse them.** Budget allocation = MMM (+ incrementality validation). Creative and tactical optimization = MTA. Executive reporting = both, with MMM labeled as primary.

## Step 4 — Domain validators

- **Data reconciliation:** weekly revenue (warehouse) vs. bank — within ±2%
- **MMM cross-validation:** out-of-time RMSE + MAPE reported quarterly
- **Incrementality alignment:** MMM-predicted vs. holdout-measured incrementality within ±25%
- **Channel coverage:** no >5% of paid spend untracked
- **Refresh freshness:** MMM rebuild ≤90 days old at any time
- **Dashboard freshness:** daily refresh on MTA views; weekly on MMM

## Step 8 — Working protocol additions

- **Never make a budget allocation decision on MTA alone.**
- **Never retire MTA without 90+ days of parallel run.**
- **Never ignore incrementality — an MMM without it drifts.**
- **Never report MMM point estimates without confidence intervals.**
- **Always reconcile to bank revenue weekly.**
- **Always document model changes** in `Documentation.md` — priors, data additions, variable removals
- **Always cross-validate out-of-time** — never only in-sample

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — **primary KB for this program (20 articles)** — Hill curves, mROAS, PPC engine methodology
- Read `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` before M3 (first model build); cite specific articles in `Documentation.md`

## Common example fills

- **"Build first-ever MMM for $40M DTC brand; retire Northbeam MTA over 6 months"**
- **"Migrate from Triple Whale MTA to custom MMM + incrementality program for $100M subscription brand"**
- **"Add brand-lift measurement to MMM for B2B SaaS with 6-month sales cycle"**
- **"Rebuild broken in-house MMM (confidence intervals too wide for decisions) with outside consultant + data-science team"**
- **"Cross-validate MMM against geo-holdout incrementality tests — produce variance report for board"**

## Hand-off

After bootstrap, use `~/.claude/templates/growth-ecommerce/attribution-mmm/resumption.md`.
