# Attribution / MMM — Deep Research Template

> **Inherits from:** `~/.claude/templates/deep-research-competitive-landscape.md` or `deep-research-technical-reference.md` (for vendor/methodology evaluations)

---

## Use cases

- **MMM vendor evaluation** — Haus / Measured / Prescient / Recast / MMM.co / Rockerbox MMM / Northbeam MMM / build-in-house
- **MTA vendor evaluation** — Northbeam / Triple Whale / Rockerbox / Proper Attribution / Ruler Analytics
- **Methodology research** — Bayesian MMM vs. frequentist; geo-holdout design; unified measurement approaches
- **iOS / cookie deprecation impact research** — SKAN4, ATT, third-party cookie loss, CAPI adoption
- **Competitor measurement strategy** — how do category leaders measure?
- **Incrementality testing design** — geo holdouts, light-hold, ghost bidding methodology

## Opinionated source priorities

**Prioritize:**

- **Academic research** — Google's Robyn paper, Meta's paper on MMM, Stanford + Columbia papers on causal inference in marketing
- **Rockerbox blog** — methodology-heavy, open about tradeoffs
- **Haus blog** — incrementality-focused
- **Measured blog** — MMM-first philosophy
- **Recast blog** — Bayesian MMM
- **Open-source code** — Meta's Robyn (R package) is the reference implementation; LightweightMMM from Google; PyMC-Marketing
- **Conference talks** — Measured Summit, Haus Effect, Google Marketing Live

**De-prioritize:**

- Vendor-sponsored "why we're better" white papers (treat as positioning)
- Last-click MTA vendor marketing (outdated framing)
- Generic attribution blogs

## Question-set specializations

### For MMM vendor evaluation:

1. Modeling methodology — Bayesian / frequentist? Open about their math?
2. Data ingestion — which platforms auto, which manual, which require warehouse?
3. Refresh cadence — daily, weekly, quarterly?
4. Incrementality integration — do they run tests or only model?
5. Confidence intervals — reported? How wide for typical client?
6. Customer validation — public case studies with named brands?
7. Stakeholder UX — is the output readable by a non-DS VP?
8. Pricing — annual tier + data-source add-on + custom-modeling cost?
9. Time-to-value — realistic weeks from kickoff to usable model?
10. Exit cost — can you export model priors / feature engineering / contributions?

### For methodology research:

1. Adstock function choice — geometric, delayed, Weibull?
2. Saturation function — Hill, logistic, power?
3. Priors for channel effects — how do vendors / in-house teams set them?
4. Seasonality handling — Fourier terms, dummy variables, spline?
5. External factor integration — weather, competitor activity, macro trends?
6. Brand vs. performance split — how to handle brand campaigns in MMM?
7. Cross-channel interaction — how (or do) vendors handle channel-to-channel effects?

### For iOS / cookie research:

1. Meta CAPI adoption benchmarks — what % of events server-side?
2. SKAN4 impact by vertical — where has iOS attribution collapsed most?
3. Conversion API effectiveness — measured match rate, conversion restoration
4. Third-party cookie deprecation timeline — latest schedule, mitigation patterns
5. First-party data maturity benchmarks — CDP adoption by category

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — **primary KB, 20 articles** — Hill curves, mROAS, PPC engine methodology, response-curve fitting

Cite specific KB articles in the Methodology section of the deliverable.

## Example filled-in briefs

- "Evaluate Haus vs. Measured vs. Recast for $80M DTC brand ready to replace in-house MMM; need: 90-day time-to-value, quarterly refresh, ≤$150K/year, confidence intervals reported"
- "Research current best-practice for Bayesian MMM vs. frequentist MMM — performance, speed, stakeholder understandability, regret rates on decisions"
- "Research measured impact of iOS 14.5 + SKAN4 on ecommerce MMM contributions to Meta — pre/post contribution shifts at peer brands"
- "Evaluate Northbeam vs. Triple Whale MTA for a $15M DTC brand — feature parity, data accuracy, migration cost"
- "Research incrementality test design — geo-holdout vs. light-hold vs. ghost bidding — for a brand that can't run geo-holdouts (no regional variance) — what are the best alternatives?"
