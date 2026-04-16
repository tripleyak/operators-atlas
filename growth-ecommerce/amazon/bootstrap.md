# Amazon Program — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** starting a multi-session Amazon marketplace program — listing launch / relaunch, PPC restructure, account health recovery, Seller Central ops buildout, or Amazon-focused growth.

---

## Who this is for

Amazon operators, brand managers, PPC specialists, and Seller Central admins at DTC / CPG / consumer brands. Programs span 6-12 weeks for a focused PPC rebuild, 8-16 weeks for a listing launch, or 12-24 weeks for a full Amazon growth program.

## Opinionated defaults

### Listing readiness (the launch gate)

- **10+ reviews and 4.0+ rating before significant PPC scale.** Launching PPC into a low-social-proof listing wastes spend at poor CVR.
- **30+ days of inventory buffer** at target run-rate before scaling ads. Going OOS mid-scale destroys ranking.
- **A+ Content (EBC) required on hero SKUs** — bullets + images + comparison tables; ≈10-15% CVR lift typical.
- **Main image: 85%+ product fill, white background, 2000px min** — compliant and conversion-optimal.
- **Backend search terms: 249 bytes maxed out** — no repeat words, no brand name, no competitor trademarks, no misspellings (Amazon handles those).

### PPC architecture

- **Launch with Auto campaigns only** for 7-14 days to harvest search terms.
- **Cascade:** Auto → Broad (manual) → Phrase → Exact, with negative-keyword mining at each step to prevent cannibalization.
- **Separate campaigns by match type** — never mix; allocation and bid logic differs.
- **Separate campaigns by intent** — brand defense, competitor conquest, category, category-plus-brand; different strategies.
- **Budget pacing by campaign** — Auto budget-capped lower than Manual to preserve learning.

### Economics

- **TACoS target: 10-15% for mature listings, 20-30% for launches**, decreasing as organic rank builds.
- **ACoS is diagnostic, TACoS is the decision.** ACoS high + TACoS low = healthy (organic rank benefit).
- **Inventory health metric: Inventory Performance Index (IPI) ≥ 400.** Below that → storage limits start.
- **Bid strategy: "Down only" for most campaigns.** "Up and Down" only when you have time to monitor daily.

### Account health

- **Order Defect Rate (ODR) <1%.** If approaching, pause aggressive growth until fixed.
- **Policy violations = 0.** A single violation can cascade to suspension.
- **Response time to messages <24h** (Amazon enforces)
- **Inventory Performance Index >400** sustained

### Seasonality

- **Q4 / Prime Day / back-to-school / seasonal moments: 60-day lead time.** Inventory locks down earlier than you expect; freight rates spike; ad auctions intensify.

### Reviews

- **Never pay for reviews. Never buy fake reviews.** Full stop. Amazon's fraud detection has caught up; suspensions are existential.
- **Vine + Amazon's Request-a-Review button are the only sanctioned tools.**
- **Review velocity matters more than absolute count** — 20 reviews this month > 200 reviews last year.

## Step 0 — Interview question additions

1. **Amazon presence:** Seller Central (direct), Vendor Central (wholesale), or both?
2. **Brand Registry:** enrolled? Level (basic, Amazon Brand Registry + trademarks)?
3. **Category + BSR starting point:** where does the flagship SKU rank now?
4. **Listing count + SKU depth:** single hero SKU or full catalog?
5. **PPC current state:** account spend level, current TACoS, campaign organization
6. **Inventory infrastructure:** FBA only, FBM, SFP (Seller Fulfilled Prime)?
7. **Account health:** any suspensions, violations, IPI issues?
8. **Review count + rating by SKU**
9. **Content state:** A+ Content done? Videos? Brand Story? Posts?
10. **Competitive landscape on category:** who owns the top-5 organic spots?
11. **External support:** Helium10 / JungleScout / Perpetua / Pacvue / DataDive / SmartScout in use?
12. **Cross-channel coordination:** Amazon vs. DTC / retail inventory split — any conflicts?

## Step 2 — Milestone template (12-week program)

```markdown
### M1 — Account Audit + Listing Health (week 1-2)
- Deliverable: account health report, listing quality score per SKU, competitive positioning baseline
- Validation: IPI + ODR + violations documented; A+ Content + Brand Story status per SKU
- Target: end of week 2

### M2 — Listing Optimization (week 2-4)
- Deliverable: hero SKU listings optimized (title, bullets, A+, images, backend keywords)
- Validation: listings live; CVR baseline established; organic rank snapshot
- Target: end of week 4

### M3 — PPC Restructure + Launch (week 4-6)
- Deliverable: PPC account restructured; Auto + Broad + Phrase + Exact cascade live
- Validation: campaigns organized by match type + intent; budgets pacing; bid rules documented
- Target: end of week 6

### M4 — Keyword Harvest + Scale (week 6-10)
- Deliverable: search-term mining running; winning keywords promoted to tight Exact; negatives harvested
- Validation: promoted keywords TACoS <target; negative list preventing cross-contamination
- Target: end of week 10

### M5 — Coupons + Promotions + Deals Layer (week 8-12)
- Deliverable: promotion cadence (coupons, Lightning Deals, Prime Exclusive); Vine enrollment if applicable
- Validation: review velocity accelerating; conversion rate stable through promotions
- Target: end of week 12

### M6 — Brand Analytics + Search Term Deep Mine (ongoing)
- Deliverable: weekly Brand Analytics review; competitor monitoring; SQP integration
- Validation: Brand Analytics insights feeding back into PPC and listing decisions
- Target: ongoing past week 12
```

## Step 3 — Critical mental model

> **Amazon is a search engine, not a marketplace.**
>
> The listing is the landing page. PPC is the traffic. Reviews are the social proof. Inventory is the non-negotiable prerequisite. Skip any of these and the flywheel does not start.
>
> The virtuous loop: ads drive traffic + conversions → conversion velocity raises organic rank → organic rank drives free traffic → free traffic + reviews compound over time → TACoS drops → margin improves → reinvest in more ads.
>
> The vicious loop: out-of-stock kills rank → rank recovery takes weeks → ads become more expensive → inventory gets deprioritized → OOS again. Inventory management is the hidden foundation of Amazon growth.

## Step 4 — Domain validators

- **Listing quality:** A+ Content live, main image compliant, backend keywords maxed
- **PPC organization:** campaigns by match type + intent; no orphan keywords
- **Budget pacing:** daily budgets hitting without midday exhaustion
- **Inventory health:** IPI >400; days-of-supply >30 for hero SKUs
- **Account health:** ODR <1%; zero policy violations; message response <24h
- **TACoS trend:** weekly direction (up / flat / down) reported

## Step 8 — Working protocol additions

- **Never pay for reviews. Never buy reviews. Never.**
- **Never launch aggressive PPC on a listing <10 reviews / <4.0 rating** — poor CVR wastes spend
- **Never let inventory drop <14 days** without a plan — OOS destroys rank
- **Never run Lightning Deals at a loss just for velocity** — Amazon will repeat-promote you into a margin hole
- **Never ignore the IPI score** — below 400 = existential
- **Always mine search terms weekly** — promote winners to Exact, add losers to negatives
- **Always document campaign changes** — Amazon's algorithm punishes frequent restructuring
- **Always cross-reference Brand Analytics weekly** — it reveals what competitors are bidding on your branded terms

## KB integration

**Primary KB for this program:**

- `{{KNOWLEDGE_BASE_ROOT}}/amazon-ads/wiki/_index.md` — **32 articles on PPC architecture, bid optimization, campaign consolidation — read before M3**
- `{{KNOWLEDGE_BASE_ROOT}}/amazon-product-launches/wiki/_index.md` — **9 articles on launch playbooks and case studies — read before M2**
- `{{KNOWLEDGE_BASE_ROOT}}/amazon-developer-tools/wiki/_index.md` — 15 articles on SP-API, MCP server, catalog CLI — relevant for data-access automation

**Highly relevant:**

- `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/wiki/_index.md` — 33 articles on ShelfWins, planograms, buyer decks (retail strategy transfers)
- `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/wiki/_index.md` — 12 articles on market research, scoring

## Common example fills

- **"Launch new flagship SKU on Amazon — zero reviews to $50K/mo run-rate in 16 weeks"**
- **"Rebuild collapsed PPC account — TACoS drifted from 12% to 32% over 6 months; diagnose + restructure"**
- **"Recover account health after repeated policy warnings — return IPI from 350 to 500, ODR below 1%"**
- **"Q4 prep — 60-day lead time to Prime Day + Black Friday, covering inventory, deals, PPC scaling, review velocity"**
- **"Vendor-to-Seller transition — migrate wholesale Amazon relationship to Seller Central direct over 20 weeks"**
- **"Scale hero SKU from $200K/mo to $1M/mo while holding TACoS <15%"**

## Hand-off

After bootstrap, use `~/.claude/templates/growth-ecommerce/amazon/resumption.md`.
