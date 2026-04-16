# Affiliate Program — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** launching, overhauling, or operating an affiliate marketing program — network-based (CJ, Impact, Rakuten, Awin, ShareASale), in-house, or creator-commerce (ShopMy, LTK).

---

## Who this is for

Affiliate marketers, partnerships leaders, performance-marketing leads at DTC / ecommerce / subscription brands. Programs span 12-24 weeks for structured launch or ongoing optimization.

## Opinionated defaults

### Network vs. in-house vs. hybrid

- **Network (CJ / Impact / Rakuten / Awin / ShareASale / Pepperjam):** faster to launch, built-in affiliate base, more overhead cost
- **In-house:** higher margin, more control, requires tech infrastructure (Refersion, Tapfiliate, LeadDyno, custom)
- **Hybrid:** creator / content affiliates in-house; mass / coupon on network
- **Default recommendation:** start on network, move to in-house at $1M+ annual affiliate revenue

### Affiliate types (distinct strategies)

- **Content affiliates** (NYT Wirecutter, Business Insider Reviews, review sites): highest value; long-form content; 3-12 month recruitment cycles
- **Creator affiliates** (Instagram / TikTok / YouTube creators): content + audience; overlap with influencer program
- **Coupon affiliates** (RetailMeNot, Honey, Capital One Shopping): last-click grabbers; low-intent; limit commission
- **Cashback sites** (Rakuten, Ebates): last-click; fraud risk; consider exclusion or capped commission
- **Loyalty apps** (Ibotta, Fetch): last-click coupon-adjacent
- **Email affiliates / media buyers** (newsletter monetization, display partners)
- **Employee / customer referral** (often bundled with loyalty, separate from affiliate)

### Commission structure

- **Ecom: 5-15% typical for non-coupon affiliates; 1-5% for coupon**
- **SaaS: 20-30% first-year revenue; often recurring for 12-24 months**
- **Tiered commission:** higher rates for top-performing affiliates
- **Exclusive codes:** for top affiliates (offer unique % discount with dedicated tracking)
- **Performance bonuses:** monthly bonuses for exceeding thresholds

### Cookie / attribution window

- **7-30 days typical for ecom**
- **60-90 days for SaaS**
- **Last-click within window:** standard industry
- **Cross-device tracking** increasingly important (Impact, Everflow, AvantLink specialize)

### Attribution conflicts

- **Coupon affiliates vs. paid / creator:** coupon affiliate gets last-click credit on someone who was originally driven by creator or paid ad — controversial
- **De-duplication logic:** preferred-channel priority rules; cookie-last-seen vs. cookie-first-seen
- **Non-commissioning on branded search:** affiliates bidding on brand terms is cannibalistic; ban in terms

### Fraud prevention

- **IP + device fingerprinting** — multiple orders from same IP/device across different affiliates
- **Order-pattern analysis** — unusual velocity, geographic clustering, payment-method concentration
- **Cookie-stuffing detection** — invalid cookies, suspicious referrer strings
- **Void fraudulent orders** — chargeback affiliate; terminate if pattern continues

### Program launch

- **Start with content + creator affiliates** — cleaner attribution, brand-safe
- **Add coupon network later** (or never) — they last-click-grab but can add margin-free revenue
- **Recruit top-20 affiliates at launch** — personally onboard; they set the tone
- **Commission ladder published** — transparency + motivation

### Creator commerce (ShopMy, LTK, etc.)

- **Adjacent to influencer program** — often merged in DTC
- **Creator-owned audience + shoppable content**
- **Commission 10-20% typical; sometimes higher for exclusives**
- **Different attribution model** — creator-code-based rather than cookie-based

## Step 0 — Interview question additions

1. **Current affiliate state** — program exists? Network? In-house?
2. **Revenue attribution today** — affiliate share of revenue
3. **Cookie / attribution window** in use
4. **De-duplication logic** — what happens when affiliate + paid ad both touch?
5. **Fraud detection capability** — manual review? Tool?
6. **Commission structure** — flat or tiered?
7. **MAP policy** — enforceable on affiliate sites?
8. **Top existing affiliates** — who are they, what channels, what performance?
9. **Content affiliate relationships** — Wirecutter / NYT / review sites?
10. **Creator commerce overlap** — ShopMy / LTK program exists?
11. **Network contracts (if applicable)** — terms, exclusivity, override rates?

## Step 2 — Milestone template (16-week program)

```markdown
### M1 — Program Design + Infrastructure (week 1-4)
- Deliverable: affiliate strategy, network decision, commission structure, fraud logic, T&C
- Validation: legal-reviewed T&C; attribution logic tested
- Target: end of week 4

### M2 — Launch Infrastructure (week 4-6)
- Deliverable: network contracts signed OR in-house tool deployed; tracking integrated
- Validation: test orders tracked correctly end-to-end; commissions calculated correctly
- Target: end of week 6

### M3 — Affiliate Recruitment Wave 1 (week 6-10)
- Deliverable: top-50 affiliate outreach; content + creator focus; contracts signed
- Validation: 20+ active affiliates driving traffic
- Target: end of week 10

### M4 — Coupon + Scale Affiliates (week 10-12)
- Deliverable: coupon network activation (if included); scaled affiliate base
- Validation: program producing meaningful revenue; fraud detection operational
- Target: end of week 12

### M5 — Optimization + Reporting (week 12-15)
- Deliverable: performance dashboard; affiliate-by-affiliate management cadence; tier movements
- Validation: top-affiliate-driven revenue concentrated but diverse
- Target: end of week 15

### M6 — Ongoing Program (week 15+)
- Deliverable: monthly review cadence; quarterly commission + program review; ongoing recruitment
- Validation: program self-operates; performance sustained
- Target: end of week 16+
```

## Step 3 — Critical mental model

> **Affiliate is partnership, not channel.**
>
> Treating affiliate as "another ad channel" produces coupon-dominated programs with poor margins. Treating affiliate as partnership produces content-driven programs with high margins, brand alignment, and compound value.
>
> The 80/20 of well-run programs: 20% of affiliates produce 80% of revenue. Those top affiliates are managed like business partners — personal relationships, exclusive offers, co-created content, early access. The bottom 80% are self-service.
>
> Programs that treat all affiliates the same (flat commission, no relationship management, no content support) optimize for coupon-site last-click grabbers and leave the content / creator upside on the table.

## Step 4 — Domain validators

- **Tracking integrity:** test orders trace end-to-end
- **Fraud detection operational:** detection rules firing on suspicious patterns
- **Commission calculation accurate:** no systematic errors
- **Affiliate segmentation:** content / creator / coupon / cashback tracked separately
- **De-duplication working:** cross-channel attribution conflicts resolved per policy

## Step 8 — Working protocol additions

- **Never let affiliates bid on brand terms** — cannibalistic
- **Never pay for fraud** — void + chargeback + terminate
- **Never treat all affiliates same** — segment, manage top-20 personally
- **Never skip MAP enforcement** on affiliate sites
- **Always publish commission ladder** — transparency motivates
- **Always document de-duplication rules** — affiliates will challenge; be clear
- **Always review top-20 affiliates monthly** — relationships compound

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/wiki/_index.md` — attribution methodology (affiliate fits multi-touch model)
- `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/wiki/_index.md` — partnership-management frameworks

## Common example fills

- **"Launch affiliate program on Impact for $25M DTC brand — network-based; target 10% of revenue within 12 months"**
- **"Migrate from CJ to in-house (Refersion) for $50M brand — 16-week migration without revenue disruption"**
- **"Add content affiliate strategy — recruit Wirecutter, Business Insider Reviews, top review sites"**
- **"Creator-commerce program launch via ShopMy for fashion DTC — 100 creator partnerships in 90 days"**
- **"Fraud investigation + remediation — coupon affiliate showing anomalous velocity; audit + terminate if fraud"**

## Hand-off

After bootstrap, use `~/.claude/templates/growth-ecommerce/affiliate/resumption.md`.
