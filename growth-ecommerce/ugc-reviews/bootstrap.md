# UGC / Reviews Program — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** launching or overhauling a user-generated content or reviews program — solicitation flows, review-management, UGC rights capture, review-platform integration, response protocols.

---

## Who this is for

Ecommerce / DTC / consumer-brand teams managing reviews + UGC as a core acquisition + conversion lever. Programs span 8-16 weeks to launch or rebuild; ongoing after.

## Opinionated defaults

### Review fundamentals

- **Review velocity matters more than count.** 20 reviews this month > 200 reviews last year.
- **Never pay for reviews.** Never solicit positive-only. Both are policy violations (Amazon, FTC) and brand-integrity violations.
- **Review content:** photos + videos outperform text-only 2-3× in social proof value.
- **Star-rating target: 4.3+ sustained.** Below 4.0 signals product or experience issue; above 4.8 signals selection bias or fake.

### Review solicitation

- **Post-purchase email: T+7 (delivered) + T+14 (usage) + T+30 (final)**
- **Incentivize participation, not positive outcome** — discount on next purchase for any review is OK; discount for 5-star review is not
- **Photo / video request: explicit** — "share a photo" yields 5-10× photo content vs. passive
- **SMS review requests:** emerging pattern, strong performance (20-40% response rate)
- **Review platform integrated with post-purchase flow** (Yotpo / Okendo / Stamped / Loox / Judge.me / Junip)

### Review-response protocol

- **Respond to all 1-3 star reviews within 48h publicly** — shows brand cares
- **Don't respond to 4-5 star reviews** routinely — looks performative
- **Private-channel follow-up for resolution** — move issue off public review
- **Never argue with reviewer publicly** — always acknowledge + resolve
- **Review disputes:** only dispute obvious fraud / policy violations; never dispute honest negative

### UGC solicitation + rights

- **Always capture usage rights** — submission includes permission for brand use
- **90-day paid-ad usage + 1-year organic usage** — standard terms
- **Compensation for UGC:** optional for regular customers; contracted for dedicated creators (see influencer-creator templates)
- **UGC platforms:** Yotpo Visual UGC / Bazaarvoice / Olapic / Pixlee TurnTo / Okendo — aggregate + curate

### Review platform choice

- **Yotpo:** enterprise-full-stack (reviews + loyalty + SMS + UGC); higher cost
- **Okendo:** modern UX, Shopify-native, strong for growing brands
- **Stamped:** mid-market, reviews + loyalty combo
- **Loox:** photo-first reviews, Shopify-ecosystem
- **Judge.me:** budget-friendly, solid core features
- **Junip:** newer, good UX, growing
- **Reviews.io / Trustpilot:** independent third-party; valuable for off-site trust signals
- **Google Seller Ratings:** requires third-party review platform integration

### Cross-posting + aggregation

- **Post reviews to Google Seller Ratings** — ad star-rating display
- **Post to Trustpilot / BBB** for brand trust
- **Post to Yahoo / Bing Ads** for multi-platform ad star-ratings
- **Cross-post to Amazon — never** — Amazon has strict TOS; paid promotion to post bans accounts

### Anti-patterns

- **Never pay for reviews**
- **Never filter out negative reviews pre-publication** (some platforms tempt this; strict FTC violation)
- **Never "solicit only satisfied customers"** — selection bias is fraudulent
- **Never manufacture UGC** (AI-generated, stock imagery presented as customer) — regulatory + trust risk

### Measurement

- **Review velocity:** reviews/month trend
- **Review-to-purchase ratio:** % of orders that produce review
- **Average star rating:** monthly
- **UGC rate:** % of submissions with photo/video
- **Response coverage:** % of 1-3 star with response within 48h
- **Review-driven conversion impact:** A/B test with vs. without on PDP

## Step 0 — Interview question additions

1. **Review platform in use** — none, DIY, integrated?
2. **Current review count + rating** — by SKU / overall
3. **Review solicitation flow** — manual, automated, frequency?
4. **UGC capture** — rights-cleared library exists?
5. **Response protocol** — who responds, SLA, escalation?
6. **Photo/video capture rate** — % of reviews with visual
7. **Cross-platform footprint** — Google Seller Ratings, Trustpilot, BBB?
8. **Amazon review independence** — separate or cross-functional team?
9. **SMS review capability** — testing, deployed, not?
10. **Legal / compliance stance** — any past review-fraud concerns or legal notices?

## Step 2 — Milestone template (12-week program)

```markdown
### M1 — Audit + Platform Decision (week 1-3)
- Deliverable: current-state review audit; platform selection; response protocol definition
- Validation: clear gaps + strategy; platform committed
- Target: end of week 3

### M2 — Platform Integration + Flow Build (week 3-5)
- Deliverable: platform live; solicitation flows (email + SMS) configured; UGC rights-capture integrated
- Validation: test transactions produce review requests; rights capture in flow
- Target: end of week 5

### M3 — Response Protocol + Training (week 5-7)
- Deliverable: team trained; 48h response SLA on 1-3 star; crisis / escalation paths
- Validation: response metrics tracking; first week of responses executed
- Target: end of week 7

### M4 — Cross-Platform Posting (week 6-9)
- Deliverable: Google Seller Ratings + Trustpilot + ad platform integrations
- Validation: multi-platform review flow confirmed
- Target: end of week 9

### M5 — UGC Activation (week 8-11)
- Deliverable: UGC library curated; PDP UGC galleries live; paid-ad UGC creative library
- Validation: UGC driving measurable PDP lift in A/B test
- Target: end of week 11

### M6 — Performance Review + Iteration (week 11-12+)
- Deliverable: performance dashboard; monthly review cadence; iteration backlog
- Validation: program self-operating; KPIs trending
- Target: end of week 12+
```

## Step 3 — Critical mental model

> **Reviews and UGC are the third-most important conversion element on a PDP — after price and image — and they compound.**
>
> Each review adds to the social-proof library; each UGC photo adds to the visual trust library. Products with 50 reviews convert materially better than products with 5. Products with 200 reviews + 20 UGC photos dominate paid-ad CTR + on-site conversion.
>
> This compounds: higher conversion → more sales → more reviews → higher conversion. Brands that invest in systematic solicitation at product launch capture the compound advantage. Brands that wait for organic reviews never catch up.
>
> The flip side: one high-visibility 1-star review can crater a product's rating and conversion. Response protocol is insurance — when the rare catastrophe happens, professional response preserves trust.

## Step 4 — Domain validators

- **Solicitation active:** automated flow firing on 100% of eligible orders
- **Response SLA:** 1-3 star reviews with response within 48h
- **UGC rights capture:** every submission includes permission
- **Cross-platform sync:** Google / Trustpilot / ad platforms receiving data
- **Review fraud monitoring:** unusual patterns flagged for review

## Step 8 — Working protocol additions

- **Never pay for reviews**
- **Never solicit positive-only**
- **Never filter negative reviews pre-publication**
- **Never argue publicly with negative reviewers**
- **Always respond to 1-3 stars within 48h**
- **Always capture rights with UGC submission**
- **Always cross-post to Google Seller Ratings** for ad star-rating lift

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/wiki/_index.md` — PDP + conversion patterns
- `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/wiki/_index.md` — competitive review analysis

## Common example fills

- **"Launch Okendo review program for $20M DTC brand — target 10% review-to-purchase ratio, 4.3+ average rating"**
- **"Rebuild review-solicitation flow — current response rate 3%, target 15%"**
- **"UGC rights capture + ads library build — 200 rights-cleared UGC assets for paid media in 12 weeks"**
- **"Review crisis response — product-issue driving 1-star wave; response + product-fix coordination"**
- **"Cross-platform review footprint expansion — Google Seller Ratings + Trustpilot + BBB + Reviews.io"**

## Hand-off

After bootstrap, use `~/.claude/templates/growth-ecommerce/ugc-reviews/resumption.md`.
