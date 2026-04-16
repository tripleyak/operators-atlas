# B2B Lead Generation Program — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** starting a multi-session B2B lead generation program — outbound SDR, ABM, inbound demand, content-to-lead, webinar engine, or full-funnel pipeline build.

---

## Who this is for

VPs of growth, demand generation leaders, marketing operations at B2B SaaS / services / industrial / enterprise software companies. Programs span 12-24 weeks for structured pipeline build or 16+ weeks for full-funnel rebuild.

## Opinionated defaults

### ICP + qualification

- **ICP first, volume second.** A precise ICP hits conversion benchmarks; a loose one wastes SDR time and ad spend.
- **ICP scoring model:** firmographic (company size, revenue, industry, tech stack) + behavioral (intent signals, website engagement) + fit score combined
- **MQL ≠ SQL** — define handoff criteria explicitly with sales; MQL is marketing's output, SQL is sales' acceptance
- **Healthy MQL → SQL conversion:** 10-30%. Below 10% = targeting issue; above 50% = MQL bar is too high (missing volume)

### ABM vs. demand gen

- **ABM for $100K+ ACV; usually wrong for <$30K ACV** (economics don't work)
- **Target account list:** 50-500 accounts for most mid-market ABM programs; 20-50 for enterprise
- **1:many ABM:** thousands of accounts, category-level messaging
- **1:few:** dozens of accounts, segment-customized
- **1:1 ABM:** strategic accounts, fully-personalized program
- **ABM measurement:** pipeline-generated per target account, not MQL count

### SDR motion

- **Outbound: 6-12 touches over 14-21 days** across email + phone + LinkedIn
- **Cadence structure:** Day 1 email → Day 2 call → Day 4 LinkedIn → Day 6 email → Day 8 call → Day 10 LinkedIn → Day 14 break-up email
- **Personalization:** research-based, not token-substitution; 10-15 minutes per prospect for strategic tier
- **Break-up email** is highest-response email in cadence; never skip
- **SDR quota:** reply rate 5-15%, meeting-set rate 2-5%, meeting-held rate 60-80% of set

### Inbound + content

- **Gate or no-gate:** Default to lightly-gated (5-10 fields only on high-value assets); ungated for top-of-funnel
- **Pipeline-generating content:** calculator / assessment / comparison guide / benchmarks — data-rich + industry-specific
- **Webinar conversion:** 20-40% of registrants attend; 10-20% of attendees take next step
- **Content-to-MQL benchmark:** 2-5% of content downloaders become MQLs

### Pipeline + conversion

- **Pipeline coverage: 3-5× quarterly revenue target** to hit number with normal win rates
- **Attribution:** multi-touch with time-decay for B2B; MTA alone is noise at long sales cycles
- **Win rate benchmarks:** 20-30% inbound; 10-20% outbound; varies wildly by segment
- **Sales cycle discipline:** stage-gates with exit criteria; no stale opportunities in pipeline

### Revenue team alignment

- **SLA on MQL handoff:** SDR accepts within 24h; contacts within 48h; dispositions within 7d
- **Weekly marketing-sales review:** MQL quality, SDR performance, pipeline gaps
- **Quarterly ICP calibration:** is the definition still right? Win analysis + loss analysis

## Step 0 — Interview question additions

1. **Current ICP** — how precisely defined? Documented?
2. **Target market size** — addressable + obtainable + niche you've picked
3. **ACV band** — determines ABM vs. broad demand gen economics
4. **Current MQL → SQL → Win rates** by channel
5. **Pipeline coverage ratio** today; target
6. **Sales cycle length** — median and by ACV band
7. **SDR team size + structure** — inbound, outbound, hybrid? Tooling?
8. **Content inventory** — what's converting, what's stale
9. **Intent data in use** — Bombora / 6sense / G2 / Demandbase / ZoomInfo?
10. **Tech stack** — CRM, MAP (marketing automation platform), sales engagement (Outreach / Salesloft / Apollo / Groove), ABM platform
11. **Revenue team alignment** — cadence, friction points, SLA status

## Step 2 — Milestone template (16-week program)

```markdown
### M1 — ICP + Pipeline Audit (week 1-3)
- Deliverable: ICP documented; win/loss analysis; pipeline coverage report
- Validation: ICP signed off by revenue team; gap analysis complete
- Target: end of week 3

### M2 — Target Account + Channel Strategy (week 3-5)
- Deliverable: target account list (sized by ABM tier); channel mix + budget
- Validation: list scored + prioritized; channel plan approved
- Target: end of week 5

### M3 — SDR Playbook + Content Ready (week 5-8)
- Deliverable: cadence sequences; personalization library; top-of-funnel + mid-funnel content
- Validation: first SDR cohort running; content deployed
- Target: end of week 8

### M4 — Outbound + Inbound Launch (week 8-12)
- Deliverable: SDR cadences active; paid channels live; webinar engine running
- Validation: MQL volume trending to target; SDR meeting-set rate measured
- Target: end of week 12

### M5 — Pipeline Optimization (week 12-15)
- Deliverable: performance review; iteration on cadences, content, channels
- Validation: conversion benchmarks hit or diagnosed
- Target: end of week 15

### M6 — Ongoing Cadence + Reporting (week 15+)
- Deliverable: weekly pipeline rhythm; monthly ICP calibration; quarterly program review
- Validation: program self-operates; pipeline coverage sustainable
- Target: ongoing
```

## Step 3 — Critical mental model

> **Pipeline is a function of ICP precision × channel fit × message resonance × execution discipline.**
>
> When pipeline underperforms, operators often reach for volume (more ads, more SDRs, more content) when the real issue is precision (wrong ICP, wrong channel, wrong message). Volume amplifies whatever the current system is producing — if the system is producing low-quality MQLs, volume produces more low-quality MQLs.
>
> The diagnostic sequence: Are we targeting the right accounts? → Are we reaching them through channels they pay attention to? → Is the message answering their actual problem? → Is execution (response time, cadence completion, content quality) on par? Each layer multiplies. Fix them in order, not all at once.

## Step 4 — Domain validators

- **ICP defined + scored:** every lead has fit score; definition revisited quarterly
- **MQL → SQL conversion:** tracked weekly with benchmark
- **SDR cadence completion:** 80%+ of prospects get full cadence; not skipped mid-sequence
- **Pipeline coverage:** 3-5× target; alert if below
- **Content performance:** MQL rate by asset; sunset zero-performers

## Step 8 — Working protocol additions

- **Never scale SDR team without ICP precision proven** — you'll scale waste
- **Never ship content without conversion goal defined**
- **Never run ABM below $50K ACV** — economics don't support it
- **Never let MQLs sit >24h before SDR acceptance**
- **Always measure win rate by channel** — not all channels produce equal pipeline quality
- **Always document lost-deal reasons** — input to ICP refinement
- **Always respect SLAs** with revenue team — broken SLAs destroy alignment

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/wiki/_index.md` — B2B content strategy patterns
- `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/wiki/_index.md` — ICP research + competitive positioning
- `{{KNOWLEDGE_BASE_ROOT}}/ai-engineering/wiki/_index.md` — AI/LLM applications for SDR + content automation

## Common example fills

- **"Launch ABM program for $50M B2B SaaS — 300 target accounts across 3 ICPs; 6-12 month sales cycle"**
- **"Build outbound SDR engine from scratch for $10M ARR PLG SaaS expanding from self-serve to sales-led"**
- **"Diagnose MQL → SQL conversion collapse — dropped from 22% to 8% over 6 months"**
- **"Pipeline rebuild for Series B company — previous program produced volume but won only 8% of opportunities"**
- **"Webinar engine for enterprise cybersecurity — target 500 attendees/quarter, 100 SQLs"**
- **"Intent-data-driven outbound — Bombora + 6sense integration + cadence redesign"**

## Hand-off

After bootstrap, use `~/.claude/templates/growth-ecommerce/b2b-leadgen/resumption.md`.
