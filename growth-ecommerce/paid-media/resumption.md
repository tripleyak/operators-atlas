# Paid Media Program — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`
>
> **Use when:** sessions 2+ of a paid-media program bootstrapped with `paid-media/bootstrap.md`.

---

## Domain-specific session scope examples

- "Creative test readout + next-wave brief"
- "Audience expansion test launch"
- "Scale ladder decision on winning creative"
- "MER decline diagnosis"
- "Account restructure phase 2"

If your session scope falls outside these, stop and ask whether this should be a different session type or a fresh project.

## Domain-specific blocker questions (routing-changing)

Add to master Step 3:

1. **Is the MMM refresh complete for this quarter?** If no → budget-allocation decisions must wait; work on creative/audience tests only.
2. **Did the current creative test complete its learning phase?** If no → scaling or killing decisions are premature; wait for ≥50 conv/7d.
3. **Are there any platform policy flags or account restrictions active?** If yes → resolve before any new creative launches; content strikes compound.
4. **Is there a live incrementality test running?** If yes → do not change spend levels or campaign structure; wait for test conclusion.
5. **Any Q4 / Prime Day / category-seasonal moment approaching in next 30 days?** If yes → lock structure 14+ days before; no experiments in peak.

## Domain-specific ranked work patterns

### If MMM is fresh + tests completed
Scale ladder decisions on winners; audience expansion on validated creatives.

### If creative test is mid-flight
No scale decisions. Creative production for next wave; documentation of hypotheses; prep for readout.

### If MER has declined suddenly
Drop other work. Diagnosis protocol:
1. Check pixel / attribution integrity (is the measurement broken?)
2. Check creative fatigue (frequency cap hit? Creative >30 days old?)
3. Check audience saturation (CPM trend? new vs. returning mix?)
4. Check competitor action (ad library scan; new entrant?)
5. Check seasonality (comp to same period last year)

Do not scale during a decline. Diagnose → stabilize → then scale.

### If account is in violation / restriction
Account health work takes priority over everything else. A banned account destroys the program.

## Domain-specific working protocol (adds to master Step 5 universal rules)

**Sacred rules** — violate these and the program degrades:

- **Never toggle a campaign during learning phase.** Signals reset; previous spend wasted.
- **Never scale >20% in 72h.** Triggers re-learning; CAC spikes.
- **Never run more than 1 structural change per campaign per week.** Attribution becomes impossible.
- **Never cut a test <2 weeks old** unless it's a visible fraud / policy issue. Insufficient signal.
- **Never change attribution settings mid-test.** Invalidates the test retroactively.

**Decision discipline:**

- Every test has a written hypothesis in `Documentation.md` before launch
- Every kill / scale / continue decision references the hypothesis
- Every scaling decision checks blended MER *before* platform ROAS
- Every channel allocation change cross-references MMM refresh date — if >30 days old, flag as caveat

**Measurement discipline:**

- Blended MER first, platform ROAS second, model-attributed third
- Conversion match rate check weekly (platform vs. GA4 vs. Northbeam vs. bank) — alert if >15% delta
- Pixel / CAPI health check weekly
- Attribution-window documented on every readout

## Domain-specific Step 2 verification commands

```
# MER dashboard freshness
{check dashboard last-refresh timestamp} # expect: <24h ago

# Pixel fire check
{platform pixel-health tool output} # expect: firing + de-duplicated

# Conversion match rate
{daily revenue query across 4 sources} # expect: within ±15%

# Budget pacing
{weekly spend vs. budget query} # expect: within ±10% target

# Account health
{platform account health check} # expect: no active restrictions
```

## KB integration reminders

Before any significant channel-allocation decision, read:
- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — relevant section for this decision type
- `{{KNOWLEDGE_BASE_ROOT}}/amazon-ads/wiki/_index.md` — if Amazon is in the mix

Before any creative strategy decision:
- `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/wiki/` — for competitor creative benchmarks

## Common drift patterns to watch for

- **Scope creep into lifecycle / CRO** — these are different programs. If paid-media data suggests lifecycle or CRO work, document as a cross-program learning in `Documentation.md` and stay scoped.
- **Agency / vendor direction conflicting with program mental model** — agencies often optimize for platform ROAS; program optimizes for blended MER. Surface the conflict, don't absorb it silently.
- **Stakeholder pressure to scale mid-test** — written hypothesis + milestone cadence protects against this; cite them.
