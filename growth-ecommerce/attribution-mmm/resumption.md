# Attribution / MMM Program — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Q2 MMM refresh build + validation"
- "Incrementality test design for Meta vs. organic social"
- "Reconciliation investigation — MMM vs. bank delta grew to 18%"
- "Stakeholder training on MMM output interpretation"
- "Add TikTok + CTV to existing MMM data pipeline"

## Blocker questions

1. **Is the data pipeline healthy?** If weekly revenue reconciliation is >5% off vs. bank → pause modeling work, fix pipeline first.
2. **Is there an active incrementality test running?** If yes → do not re-run MMM on data that includes test period until test concludes.
3. **Any recent channel-attribution-setting changes?** (Meta attribution window, iOS privacy update, SKAN4 rollout, cookie deprecation impact) — if yes, rebuild with awareness of the structural break.
4. **Has any stakeholder been making decisions on stale model output?** If model >90 days old, stop stakeholders first, then refresh.
5. **Any seasonality / external factor not in the model?** New product launch, major PR, regulatory change, competitor action — these need to be added as features or the model misattributes.

## Ranked work patterns

### If model refresh is due (>90 days old)
Priority #1. Drop everything. Refresh procedure:
1. Pull latest data, reconcile to bank
2. Re-engineer features (add new channels, holidays, launches)
3. Refit model with saved priors
4. Cross-validate out-of-time
5. Compare contributions vs. prior model — flag anything >15% delta
6. Update dashboards + notify stakeholders

### If MMM vs. bank reconciliation breaks
Data pipeline issue. Investigate:
1. Revenue definition changed? (Net vs. gross, returns, currency)
2. Channel definition changed? (Platform name change, campaign restructure)
3. Platform data export broken? (API deprecation, credential expiry)
4. Attribution window changed on source system?

### If incrementality test misaligns with MMM
This is the program working correctly. Update the model with test data as ground truth where possible. If delta is consistent and >25%, consider: (a) model needs refresh with incrementality as a prior, (b) incrementality test design was flawed, or (c) structural break occurred.

### If stakeholder drift (decisions on MTA again)
Re-train. Root cause is always: MMM outputs aren't understood, or dashboard shows MTA more prominently. Fix presentation + run another stakeholder session.

## Working protocol additions

- **Never report a model output without confidence intervals.**
- **Never refresh with cherry-picked features** — document every variable change
- **Never hide an incrementality result that disagrees with MMM** — that's the point of validation
- **Always cross-validate out-of-time** on every refresh
- **Always reconcile weekly to bank**
- **Always preserve prior model outputs** — roll-forward storage enables drift analysis

## Verification commands

```
# Data reconciliation
{warehouse-to-bank weekly query}    # expect: ±2% delta

# Model freshness
{MMM last-run timestamp}            # expect: <90 days

# Incrementality calendar
{test tracker query}                 # expect: no conflicting active tests

# Dashboard integrity
{MMM dashboard refresh}              # expect: last 24h

# Channel coverage
{channel-to-spend query}             # expect: no channel >5% spend untracked
```

## Common drift patterns

- **Stakeholders asking for MTA views** — normal; they need re-training, not more dashboards
- **MMM contributions shifting substantially refresh-over-refresh** — either seasonality or structural change; investigate, don't just accept
- **Platform reps pushing platform-ROAS narratives** — always contrary to MMM; defend the methodology
- **Agency / vendor skepticism** — valid; engage them, show the cross-validation, build confidence
- **Data team deprioritizing MMM refresh** — the #1 long-term risk; model drift makes the program worse than nothing
