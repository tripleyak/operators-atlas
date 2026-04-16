# SEO / Content Program — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Content brief batch for next sprint"
- "Content refresh pass on top-10 declining articles"
- "Keyword research for Q3 cluster expansion"
- "Technical SEO audit — CWV regression investigation"
- "Backlink outreach campaign launch"

## Blocker questions

1. **Any Google core update in last 30 days?** If yes, expect traffic volatility; diagnose before restructuring
2. **Any CWV regression?** Speed loss suppresses rankings; fix first
3. **Any indexation issue?** Articles not getting indexed = no ranking possible
4. **Manual action or algorithmic penalty active?** Remediate first
5. **Any URL / site structure change since last session?** Can cause ranking loss independent of content

## Ranked work patterns

### If core update hit
Diagnostic sequence:
1. Identify impacted pages (traffic declines >20%)
2. Pattern-match to known core-update themes (E-E-A-T, helpful content, spam, product reviews)
3. Remediate root cause — often E-E-A-T signals, sources, author credentials
4. Wait 4-12 weeks for re-evaluation; don't over-react to early noise

### If cadence is falling behind
Diagnose: editorial bottleneck or writing bottleneck?
- Editorial: simplify review process, batch reviews, elevate second reviewer
- Writing: add capacity, improve briefs, consider structured templates

### If rankings are stagnant
Usually: (a) too-competitive target keywords, (b) weak internal linking, (c) slow indexation, (d) duplicate/thin content signals. Segment the backlog by topic-cluster health and address weakest cluster first.

### If outreach is yielding zero
Re-segment targets. HARO + resource-page + guest-post outreach usually needs category-specific angle tuning.

### If refresh opportunity appears
6-month refresh procedure:
1. Check current ranking, traffic, CVR
2. Identify keyword migration (still ranking for original or adjacent?)
3. Decide: minor refresh (update stats, add sources, freshen dates) or major rewrite
4. Schedule; don't just keep creating new articles when old ones are ranking decayers

## Working protocol additions

- **Never buy backlinks.**
- **Never publish AI-generated content without editor review.**
- **Never delete old content without a 301 plan.**
- **Always write for user first.**
- **Always check keyword-volume before committing a cluster.**
- **Always run a competitor SERP check** before finalizing a brief.

## Verification commands

```
# Search Console health
{GSC weekly report}              # expect: no indexation drops, no manual actions

# CWV
{PageSpeed / Search Console}     # expect: LCP / INP / CLS in green

# Traffic / ranking trend
{Ahrefs + GA4 weekly}            # expect: stable or up for mature pages

# New-article indexation
{GSC URL inspection for week's new articles} # expect: indexed within 14d

# Refresh candidate list
{analysis of 6-month-old articles} # expect: top-20 identified for next refresh batch
```

## Common drift patterns

- **Chasing algorithm volatility** — core updates take weeks to settle; don't restructure on day 3
- **Backlink shortcut temptations** — paid links always catch up with you
- **Thin-content creep** — when velocity is stressed, articles get thinner. Editor must hold the line.
- **Keyword-stuffing on refreshes** — refreshes are for updating, not for re-stuffing keywords
- **Forgetting to internal-link new articles** — defeats the cluster strategy
