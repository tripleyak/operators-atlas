# Launch / GTM Program — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Day-0 readiness checklist pass"
- "Creative iteration for scale wave"
- "Day-30 gate review + decision"
- "Inventory replanning — sell-through faster than forecast"
- "PR opportunity response (major media inquiry Day 3)"
- "Launch-week crisis: platform policy strike on listing"

## Blocker questions

1. **Where are we in the 90-day window?** (Pre-launch, launch, scale, post-30, post-90.) Different phases have different decision velocities.
2. **Any Day-0 or Day-30 gate decision pending?** If yes, is the data clean?
3. **Any platform policy / compliance issue active?** Amazon listing flag, Meta ad rejection, Google Merchant Center issue — fix before anything else during launch
4. **Any inventory / supply-chain crisis?** Sell-through faster than forecast = scale throttle; slower = pacing check
5. **Any competitor action or market event** that could shift the launch trajectory?
6. **Customer support signal?** Day-0 to Day-7 CS volume / sentiment is the leading indicator of product fit

## Ranked work patterns

### Pre-launch phase (Day -30 to Day -1)
Priority: checklist completion. Every day's work ladders to Day-0 readiness. No distractions.

### Launch week (Day 0 to Day +7)
Priority: real-time monitoring. Watch:
- Inventory burn rate vs. forecast
- Platform health (ads approved, listings live, site performance)
- Customer support ticket velocity + themes
- PR mentions + sentiment
- Review velocity + rating

Decision authority: compressed; launches make decisions hourly, not weekly.

### Scale phase (Day 7 to Day 30)
Priority: creative iteration + channel mix optimization. What's working + why? What's dying + why? Start building the Day-30 gate data pack.

### Day-30 gate
Honest assessment:
- CAC vs. target
- Conversion rate vs. target
- Inventory sell-through
- Review velocity + rating
- Repeat-purchase signal (if enough time)

Decision: scale / iterate / kill. Do not push the decision — the data is sufficient at Day 30.

### Post-30 scale
Priority: systematic expansion. Channel-by-channel optimization. LTV signal watching. Retention flow activation.

### Day-90 retro
Full retrospective. What worked, what didn't, what was learned. Year-1 plan locked.

## Working protocol additions

- **During launch week:** make decisions fast; over-communicate with all stakeholders; assume something will go wrong
- **Never break a pricing anchor** in first 90 days unless it's the only path to viability
- **Never scale paid before Day 14** unless signal is exceptional
- **Never hide a Day-30 kill decision** — even if it's hard, the data is the data
- **Always document learnings** — these compound across future launches

## Verification commands

```
# Day-0 readiness (pre-launch)
{checklist status}                  # expect: all items green 7 days before launch

# Launch health (launch week)
{inventory burn + ad approval status + CS tickets} # expect: monitored hourly

# Day-30 gate metrics
{CAC, CVR, inventory, reviews}      # expect: all tracked, benchmarked to plan

# Day-90 metrics
{LTV trajectory, channel mix, retention signal} # expect: evaluable by Day 90
```

## Common drift patterns

- **Launch-day hubris** — early positive signal gets extrapolated; paid scales too fast; creative doesn't iterate
- **Launch-day fear** — strong signal gets under-invested; inventory sits; opportunity missed
- **Day-30 can't-let-go syndrome** — weak signal gets "one more month" decisions; kill discipline matters
- **Launch scope creep** — "while we're launching, let's also launch Y" — kills focus
- **Post-launch retrospective deferral** — "we'll retro after Q" becomes "we never retro" — lock the date pre-launch
