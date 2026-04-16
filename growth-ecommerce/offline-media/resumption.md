# Offline / Traditional Media — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Direct mail trigger-based segment launch"
- "CTV creative iteration — first-wave fatigue"
- "Incrementality test readout"
- "Podcast roster expansion"
- "OOH market selection"
- "Brand-tracker review + insights"

## Blocker questions

1. **Is incrementality test concluded before scaling decisions?**
2. **Any creative approval / legal / regulatory issue pending?**
3. **Any media-buy placement issue?** (ad vs. content mismatch, brand-safety, geo-coverage gap)
4. **Any attribution-window / MMM refresh pending?**
5. **Any seasonal / category event coming that affects channel performance?**

## Ranked work patterns

### If incrementality test is running
Do not scale. Do not kill. Wait for test period to complete. Use time for creative iteration, next-test-design.

### If creative is fatigued
1. Test new creative in holdout first
2. Compare to original in A/B if platform supports
3. Roll winner; keep loser as baseline
4. Set creative refresh calendar (CTV: 30-60 days; direct mail: 90 days; podcast: varies)

### If brand tracker trending up
Channel working. Iterate not restructure:
1. Creative refreshes
2. Scale to adjacent markets / dayparts / shows
3. Deepen creative testing
4. Compound learnings into next quarter's plan

### If brand tracker flat despite spend
Either: (a) not enough time elapsed, (b) under-scale in this channel, (c) creative isn't resonating, (d) measurement issue. Diagnose before declaring channel failure.

### Monthly channel review
Standard:
1. Spend + pacing vs. budget
2. Incrementality test status + results
3. Brand tracker trends
4. Creative performance + fatigue signals
5. Geo / daypart / show-level performance
6. Attribution + MMM contribution

## Working protocol additions

- **Never cut offline channel before incrementality validates or invalidates**
- **Never evaluate offline on last-click alone**
- **Never skip creative refresh** — fatigue is brutal
- **Always coordinate with digital team** — offline amplifies digital
- **Always monitor brand-tracker** monthly at minimum

## Verification commands

```
# Incrementality test status
{holdout test tracker}                   # expect: test period in progress or concluded

# Brand tracker
{monthly unaided / aided awareness}       # expect: stable or trending up during offline activity

# Creative freshness
{asset age vs. benchmark refresh}         # expect: within refresh window

# Channel-level MMM contribution
{MMM refresh output}                      # expect: offline contribution visible + positive

# Budget pacing
{monthly spend vs. plan}                  # expect: within ±10%
```

## Common drift patterns

- **Cutting offline too early** — 6-12 months to compound, most brands exit at 3
- **Platform-ROAS optimization** — CTV platforms over-report ROAS; use MMM + incrementality
- **Creative overuse** — same CTV creative for 6 months fatigues; brand tracker drops
- **Measurement theater** — "offline contributed $2M this quarter" without incrementality proof
- **Geo / daypart blind spots** — paying for coverage without measurement
