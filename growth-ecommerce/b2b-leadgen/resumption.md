# B2B Lead Generation — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Weekly pipeline review + gap diagnosis"
- "SDR cadence iteration based on response data"
- "New ICP tier launch"
- "Content asset performance review"
- "ABM target-account expansion"
- "MQL quality investigation"

## Blocker questions

1. **Any SDR team change in last 30 days?** Ramp time affects comparison.
2. **Any MQL → SQL acceptance gap with revenue team?** Misalignment kills programs.
3. **Any platform / data issue** in CRM, MAP, sales engagement? Attribution breakage.
4. **Any major content asset freshness issue?** Stale content converts poorly.
5. **Any market signal** (industry event, competitor move, regulatory change) affecting pipeline trend?

## Ranked work patterns

### If pipeline coverage dropping
Diagnostic:
1. MQL volume — is it volume issue or conversion issue?
2. MQL quality — has ICP match rate dropped?
3. SDR activity — cadences completing? Meetings booked?
4. Handoff SLA — are MQLs aging in queue?
5. Win rate — is it win-rate collapse masking volume?

Fix at root cause; don't layer volume on broken precision.

### If win rate is low but MQL volume is high
ICP precision problem. Tighten targeting. Run win-analysis on recent closes vs. loss analysis on recent losses.

### If MQL volume is low but win rate is high
Scale what's working. But first: measure if it's repeatable or coincidence. A 40% win rate on 5 MQLs is not a signal.

### If ABM accounts stalling
Account-by-account review:
1. Stakeholder coverage — are we reaching decision-makers?
2. Message fit — is offer calibrated to account size + situation?
3. Competitive dynamics — is incumbent defending?
4. Budget cycle — are we hitting their calendar?

### SDR cadence iteration cycle
Monthly:
1. Reply rate by step
2. Meeting-set rate by step
3. Drop-off point (where do prospects stop responding?)
4. Step-level A/B testing results
5. Kill worst-performing step; replace with experiment

## Working protocol additions

- **Never scale volume when precision is broken**
- **Never accept MQL handoff gaps >24h**
- **Never kill a channel based on <8 weeks of data**
- **Never score leads on behavior alone** — fit matters as much as intent
- **Always document ICP refinement** — it's a living doc
- **Always close the feedback loop** with sales on MQL quality

## Verification commands

```
# Pipeline coverage
{pipeline value / quarterly target}      # expect: 3-5x

# MQL → SQL conversion
{weekly conversion by channel}            # expect: stable; alert if <10% or >50%

# SDR activity
{cadence completion rate, meetings set}   # expect: 80%+ cadence complete

# Content performance
{MQL rate by asset}                       # expect: top-5 producing, bottom-10 killed

# Revenue team SLA
{MQL handoff acceptance time}             # expect: <24h median
```

## Common drift patterns

- **Volume-over-precision panic** — VP sees pipeline drop, scales SDR team; problem is ICP not volume
- **MQL definition creep** — marketing loosens definition to hit MQL number; sales rejects them all
- **Cadence decay** — SDRs skip middle steps of cadence; "break-up email" especially gets skipped
- **Intent-data theater** — paying for intent data but not acting on it
- **Content graveyard** — 50 assets live, 5 producing MQLs; no sunset discipline
