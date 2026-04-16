# UGC / Reviews — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "Monthly review metrics review"
- "Response backlog for 1-3 star reviews"
- "UGC library refresh for Q3 paid creative"
- "Review-solicitation flow A/B test"
- "Negative-review crisis response"
- "Cross-platform review-sync audit"

## Blocker questions

1. **Any rating collapse** (e.g., 4.5 → 4.0 over 30 days) requiring investigation?
2. **Any review-solicitation flow break** — emails not sending, tracking broken?
3. **Any legal / compliance notice** on review practices?
4. **Any platform policy change** affecting review acceptance (Amazon, Google)?
5. **Any UGC rights issue** — creator disputing, customer revoking?

## Ranked work patterns

### If rating is declining
Diagnostic:
1. Time-window — is it recent reviews or accumulation?
2. Product issue — quality / delivery / sizing problem?
3. Expectation mismatch — marketing over-promising vs. product reality?
4. Competitor comparison — is category rating dropping overall?
5. Review-solicitation selection — is flow reaching unhappy customers?

Fix root cause; don't manipulate through filtering.

### If response backlog
Triage:
1. 1-star first (highest visibility, highest trust damage)
2. 2-star second
3. 3-star third
4. Recent before old
5. High-traffic product reviews before long-tail

Standard response: acknowledge + offer private-channel resolution.

### If UGC library needs refresh
Procedure:
1. Current library age + usage-rights expiration audit
2. Gap analysis — which products need UGC
3. Solicitation campaign — existing customers, photo contest, creator seeding
4. Rights capture workflow
5. Library curation + ad-ready formatting

### Monthly review + UGC cadence
Standard:
1. Velocity trend — reviews / month, UGC submissions / month
2. Rating trend — overall + by SKU
3. Response coverage — 1-3 star within 48h
4. UGC usage — % of reviews with photo/video
5. Top/bottom SKUs by review health
6. Crisis any — early warning signals

## Working protocol additions

- **Never pay for reviews**
- **Never filter negative reviews**
- **Never argue publicly**
- **Always respond within 48h to 1-3 star**
- **Always capture rights on UGC submission**

## Verification commands

```
# Review velocity
{monthly reviews trend}                    # expect: stable or growing

# Rating trend
{monthly avg rating by SKU}                 # expect: stable, 4.3+

# Response SLA
{% of 1-3 star with response <48h}         # expect: 95%+

# UGC library
{rights-cleared UGC inventory}              # expect: sufficient for paid + organic

# Cross-platform sync
{Google / Trustpilot / BBB review counts}  # expect: synced
```

## Common drift patterns

- **Solicitation flow breakage** — silent; reviews stop coming, no one notices for weeks
- **Response-SLA drift** — from 48h to 1 week to never; visible publicly
- **UGC rights expiration** — content ages out without refresh; ads get pulled
- **Negative-review panic** — filtering tempts; regulatory + brand risk
- **Cross-platform drift** — Google Seller Ratings stops syncing; ad star ratings disappear
