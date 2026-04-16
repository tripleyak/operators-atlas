# CRO / Landing Page Program — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** starting a multi-session CRO program — landing-page optimization, checkout optimization, mobile UX, A/B testing cadence, on-site personalization.

---

## Who this is for

CRO specialists, growth engineers, UX researchers, and product managers running on-site optimization programs at DTC / ecommerce / B2B SaaS / marketplace businesses. Programs typically span 8-16 weeks for structured test cycles or 12+ weeks for a full checkout overhaul.

## Opinionated defaults

### Statistical discipline

- **Sample size calculator required before launching every test.** Underpowered tests are worse than no test (they mislead).
- **Minimum test duration: 2 weeks OR 10,000 visitors OR 200 conversions per variant** (whichever hits first). Short tests pick up seasonality noise.
- **Minimum detectable effect: 5% relative lift.** Below that, the statistical noise dominates and the test won't conclude in reasonable time at typical traffic.
- **Significance threshold: 95% (p<0.05) one-tailed; 97.5% for high-stakes tests.** Don't peek at 90% and call it.
- **No peeking.** Don't kill a test based on mid-flight numbers; pre-register the duration and let it run.
- **Sequential testing / multivariate only with trained stats capability** — otherwise the false-positive rate balloons.

### Hypothesis discipline

- **Written hypothesis before every test** — "If we change X, users will do Y because Z." Documented in `Documentation.md`.
- **Primary KPI pre-registered.** Secondary metrics monitored but not used to declare winners.
- **ICE scoring on backlog** — Impact × Confidence × Ease — to prioritize what ships

### Measurement

- **Primary KPI:** RPV (Revenue Per Visitor) for ecommerce · Signup Rate for leadgen · Activation Rate for PLG SaaS
- **Segmented post-hoc:** mobile vs. desktop · traffic source · new vs. repeat
- **Holdout: always maintain 10% global control** — for measuring cumulative program impact
- **Winning tests require segment stability** — if winning only on desktop but losing on mobile, it's not a winner

### Hygiene

- **No changes to pages during an active test** (even unrelated copy tweaks can contaminate)
- **One test per page at a time** (no overlapping tests on same URL)
- **Flicker testing on every variant** — no FOUC (flash of unstyled content) or flash of original content
- **Mobile tested separately from desktop** — different behaviors, often different winners

## Step 0 — Interview question additions

1. **Current on-site conversion rate** — overall and by traffic source
2. **Testing platform** — VWO / Convert / Optimizely / Google Optimize (sunset) / AB Tasty / Statsig / LaunchDarkly / build-in-house
3. **Analytics stack** — GA4 / Mixpanel / Amplitude / Heap / Fullstory / Hotjar / Microsoft Clarity
4. **Traffic volume** — weekly uniques and sessions by device / source
5. **Conversion KPI** — what counts as a conversion? Revenue, lead, trial, etc.
6. **Past tests — results + documentation?** What's been tried, won, lost?
7. **Developer capacity** — in-house eng? Marketing-dev? Agency? Determines test velocity
8. **Speed / performance baseline** — Core Web Vitals, page load, mobile-first?
9. **Personalization in use** — are we running personalization on top of A/B already?
10. **Testing platform integration with analytics** — is test-variant exposure logged into GA/Amplitude?

## Step 2 — Milestone template (12-week program)

```markdown
### M1 — Research + Baseline (week 1-2)
- Deliverable: heatmap + session recording baseline; user-research synthesis; conversion funnel audit
- Validation: GA4 funnel exports showing drop-off by step; heatmap tool recording live
- Target: end of week 2

### M2 — Hypothesis Backlog with ICE Scoring (week 2-3)
- Deliverable: 20+ hypothesis backlog with ICE scores and evidence
- Validation: every hypothesis has data support (heatmap, recording, funnel, user research)
- Target: end of week 3

### M3 — Top-3 Test Launch (week 3-4)
- Deliverable: 3 tests live, each with pre-registered hypothesis + duration + primary KPI
- Validation: tests running, flicker-free, sample size calculated
- Target: end of week 4

### M4 — Analysis + Decision Cycle (week 5-6)
- Deliverable: test readouts for completed tests; implementation of winners
- Validation: winners live on 100%; losers documented with learning
- Target: end of week 6

### M5 — Test Cycle 2 (week 6-10)
- Deliverable: next wave of 3 tests informed by prior learnings
- Validation: cycle rhythm established
- Target: end of week 10

### M6 — Program Cadence + Runbook (week 10-12)
- Deliverable: weekly test-launch cadence; monthly program review; quarterly strategy refresh
- Validation: test velocity = 2-3 concurrent tests sustained; learning log accessible
- Target: end of week 12
```

## Step 3 — Critical mental model

> **CRO is not trickery; it's removing friction from customer intent.**
>
> Winning tests come from understanding the user's actual decision-making process — not from tactics like fake urgency ("5 left!"), dark patterns, or gimmicks. Those win short-term and destroy trust / LTV long-term.
>
> The highest-leverage tests address: *page doesn't answer the question the visitor came to ask*, *critical information is hidden below the fold / behind an accordion*, *a step in checkout adds friction without adding value*, *mobile layout misorders content priority*. Everything else is rearranging deck chairs.
>
> Most tests will be "flat" (no significant winner). That's fine. A testing program's value is in the 10-20% of tests that win materially, not in every test being a win.

## Step 4 — Domain validators

- **Test infrastructure:** flicker-test each variant (target: <100ms delay before paint)
- **Traffic allocation:** test reaches target % (usually 50/50) within 24 hours of launch
- **Segment stability:** winners check segment-level (mobile / desktop / source) before declaring
- **Analytics logging:** test-variant exposure logged in GA4/Amplitude/Mixpanel
- **Goal tracking integrity:** conversion events match between testing platform and analytics (within ±2%)

## Step 8 — Working protocol additions

- **Never peek at significance early** — set duration, let it run
- **Never change unrelated elements during a test** — contamination risk
- **Never declare a winner without checking segments** — overall win can hide mobile loss
- **Never ship a losing-variant learning without documenting it** — losing tests are data too
- **Always screenshot both variants** at launch and archive to `Documentation.md`
- **Always post-mortem every test** within 7 days of conclusion
- **Always run on 100% a full cycle** before building on top — layer with care
- **Always hold 10% global control** for program-impact measurement

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/wiki/_index.md` — for customer research and scoring-engine patterns that inform CRO hypotheses

## Common example fills

- **"Reduce checkout abandonment from 72% to 60% over 12 weeks"**
- **"PDP CRO program — test variant layouts across 30 hero SKUs, roll out winners to remainder"**
- **"Mobile-first checkout rebuild — current mobile CVR 55% of desktop, target 80%"**
- **"B2B SaaS signup flow optimization — reduce signup-to-activation friction from 8 steps to 3"**
- **"Personalization layer on top of static page — test 1:1 personalization on pricing page vs. control"**

## Hand-off

After bootstrap, use `~/.claude/templates/growth-ecommerce/cro/resumption.md` for sessions 2+.
