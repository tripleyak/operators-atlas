# CRO Program — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Test readout + next-wave planning"
- "Hypothesis generation from latest research"
- "Launch top-3 tests from backlog"
- "Analyze underperforming test with segmentation"
- "Performance audit (Core Web Vitals regression)"

## Blocker questions

1. **Are current tests past their sample-size threshold?** If not → do not make declare-a-winner decisions. Wait or kill.
2. **Has any page with an active test had other changes (copy, design, data)?** If yes → test is contaminated. Decide to keep or invalidate.
3. **Is testing-platform analytics integration healthy?** (Variant exposure logging to GA4/Amplitude) — if not, segmentation analysis will be impossible
4. **Any recent marketing campaign / PR / external event that skewed traffic?** If yes, test conclusions may not generalize
5. **Has speed / Core Web Vitals regressed on tested pages?** If yes, treat as confound

## Ranked work patterns

### If a test just concluded
1. Calculate significance with proper method (Bayesian or frequentist, but the one you pre-registered)
2. Check segment stability (mobile, desktop, source, new/repeat)
3. If winner: implement on 100%, hold-back 10% global control
4. Post-mortem written to `Documentation.md`
5. Generate 2-3 next hypotheses from the learning

### If backlog needs refresh
1. Review heatmap + recording insights
2. Customer support tickets — what keeps coming up?
3. Funnel drop-off data — where does conversion leak?
4. Competitive analysis — what's different at winners?
5. ICE score the new hypotheses

### If test velocity is low
Root cause: developer bottleneck or hypothesis bottleneck or both. Diagnose: too few hypotheses or too few able-to-ship?

### If Core Web Vitals regressed
Pause new tests. Fix CWV first — every second of page-speed regression reduces test power and damages conversion independent of any test.

## Working protocol additions

- **Never make a call on an underpowered test.** Kill or extend.
- **Never layer tests without thinking about interaction effects.** If two tests touch adjacent UI, they may confound.
- **Never ignore a lost test — document the learning.**
- **Never re-run an identical lost test** — change the hypothesis or move on.
- **Always check variant logging** to analytics before concluding a test.
- **Always write the post-mortem within 7 days.**

## Verification commands

```
# Active test status
{testing platform API or UI}            # expect: expected % traffic, flicker-free

# Analytics variant-exposure logging
{GA4/Amplitude query for variant prop}  # expect: 50/50 split (or configured)

# Core Web Vitals baseline
{PageSpeed Insights or Lighthouse CI}   # expect: no regression week-over-week

# Conversion-rate baseline
{GA4 weekly CVR report}                 # expect: no unexplained movement
```

## Common drift patterns

- **"Winning" tests that don't hold up in implementation** — often from unchecked segmentation, peek-and-extend, or insufficient duration. Audit before trusting.
- **Developer pushing changes "off the books" during a test** — breaks test integrity. Enforce the "no changes during active test" rule.
- **Stakeholders demanding to call tests early** — hold the line on pre-registered duration.
