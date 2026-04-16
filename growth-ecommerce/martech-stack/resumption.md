# Martech Stack Program — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "CDP implementation — segment-taxonomy design"
- "Tool-sunset migration plan"
- "Integration audit — 14 broken data flows"
- "Renewal negotiation prep for ESP contract"
- "Warehouse schema review"
- "Identity-resolution match-rate investigation"

## Blocker questions

1. **Any active data-pipeline break?** Broken pipelines compound silently; fix before any other work.
2. **Any tool renewal in next 30 days?** Don't auto-renew; evaluate + negotiate window.
3. **Any compliance flag?** GDPR / CCPA / consent issues need immediate attention.
4. **Any active tool migration in flight?** Sequence matters — don't start a new migration mid-existing.
5. **Any security / access-review overdue?** Tools that shouldn't have access still having it is common + risky.

## Ranked work patterns

### If pipeline is broken
Immediate:
1. Identify break point (source → ELT → warehouse → CDP → activation → tool)
2. Stop downstream contamination
3. Fix at source (data-level) vs. symptom (tool-level)
4. Backfill if needed
5. Add monitoring so it doesn't happen silently again

### If renewal is imminent
Process:
1. Actual usage analysis (users, features used, value delivered)
2. Alternative vendor evaluation (at least 2)
3. Pricing negotiation (benchmark against market)
4. Decision: renew / downgrade / migrate

### If consolidating tools
Standard migration:
1. Document current tool's data, configs, users
2. Map to target tool
3. Parallel run (both tools live)
4. Data migration
5. User migration
6. Sunset old tool
7. Contract termination

### Annual audit cadence
Run once a year or quarterly for stacks >50 tools:
1. Tool-by-tool: is this still needed?
2. User-by-user: is every seat active?
3. Integration-by-integration: is this still working?
4. Data-flow: is this current?
5. Compliance: any new regulations?
6. Cost trend: per-tool YoY growth

## Working protocol additions

- **Never add tool without kill-switch** documented
- **Never integrate tool-to-tool directly** — warehouse or CDP as middle
- **Never let renewals auto-pass** — negotiate or migrate
- **Always measure tool time-to-value** — 30 / 60 / 90 days
- **Always document vendor lock-in risks** — data export, contract terms

## Verification commands

```
# Pipeline health
{ELT + warehouse + CDP activation status} # expect: no breaks > 24h

# Tool usage
{active-user analysis per tool}           # expect: match license count

# Integration status
{integration health dashboard}            # expect: all green

# Renewal calendar
{next 90 days renewal list}               # expect: each with decision status

# Data quality
{warehouse quality monitoring}            # expect: no silent failures
```

## Common drift patterns

- **Tool bloat creep** — "just one more tool" multiplies; audit regularly
- **Integration decay** — integrations break silently when vendors change APIs
- **Auto-renewal tax** — missing the 90-day window costs negotiation leverage
- **Shadow IT** — individual teams buying tools without central visibility
- **Data-team under-resourcing** — warehouse / CDP require ownership; without it, all downstream suffers
