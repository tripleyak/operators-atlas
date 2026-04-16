# Lifecycle Program — Deep Research Template

> **Inherits from:** `~/.claude/templates/deep-research-competitive-landscape.md` or `deep-research-technical-reference.md` (for ESP evaluation)
>
> **Use when:** researching lifecycle competitive landscape, ESP evaluation, deliverability benchmarks, SMS strategy, or retention methodology.

---

## Use cases

- **ESP vendor evaluation** — Klaviyo vs. Braze vs. Iterable vs. Attentive vs. Postscript vs. Omnisend
- **Competitive lifecycle teardown** — sign up for a competitor's list and analyze their flow architecture, offer cadence, content strategy
- **SMS launch feasibility** — category fit, compliance complexity, expected revenue contribution
- **Deliverability benchmark** — by vertical, what's best-in-class inbox placement / complaint rate / unsubscribe rate
- **Personalization depth research** — what personalization tactics actually lift revenue/message at your scale
- **Subscription retention benchmarks** — monthly churn by category, win-back effectiveness

## Opinionated source priorities

**Prioritize:**

- **ESP-published data reports** — Klaviyo Benchmarks, Attentive State of SMS, Braze Customer Engagement Report (note: these are vendor-published; read critically)
- **Deliverability research firms** — Validity, Litmus, Return Path (now Validity), 250ok — actual inbox placement and consumer data
- **Postmaster tools / research** — Gmail postmaster blog, Microsoft's postmaster guidance, Yahoo sender hub
- **Operator voice on Klaviyo / Attentive / Braze communities** — real practitioner benchmarks
- **Industry reports** — MessageBird, Twilio State of Customer Engagement
- **Compliance sources** — FTC guidance (CAN-SPAM), state AG actions (TCPA), EU DPA guidance (GDPR)

**De-prioritize:**

- ESP-sales-led "case studies" (treat as marketing)
- Generic lifecycle blog content
- Influencer-marketer content on "how to write emails that convert"

## Question-set specializations

### For ESP vendor evaluation:

1. Feature comparison — segmentation, flow builder, A/B, SMS, personalization, predictive
2. Integration depth — Shopify / other ecom / warehouse / reviews / returns / support
3. Pricing — list-size tier + SMS add-on + advanced features
4. Migration cost — flow export format, segment logic portability, list hygiene preservation
5. Support quality — operator community reports, tier SLAs
6. Compliance — SOC 2, GDPR-ready, CCPA, HIPAA if needed
7. Scale ceiling — list size and send rate where vendor starts pushing enterprise
8. Vendor health — funding, retention, product cadence

### For competitive lifecycle teardown:

1. Welcome flow structure — how many emails, what cadence, what offers, what narrative?
2. Cart recovery — how many touches, T+ timing, SMS included?
3. Post-purchase sequence — review request cadence, replenishment, cross-sell?
4. Content calendar cadence — how often do they send campaigns, what mix of offer vs. content?
5. SMS integration — if they SMS, at what consent architecture and frequency?
6. Personalization depth — names, locations, product categories, browsed items?
7. Brand voice consistency — flow vs. campaign voice aligned?
8. Unsubscribe experience — preference center or hard opt-out?

### For SMS launch feasibility:

1. Category norms — is SMS standard in your vertical? (skincare yes, B2B SaaS rarely)
2. Consent complexity — US TCPA (express written) vs. EU (already-email-opted-in not sufficient, need SMS-specific)
3. Average revenue/SMS benchmarks for your category (Klaviyo / Attentive publish by vertical)
4. Complaint rate risk — SMS complaints carry larger legal weight than email
5. Content constraints — 160 character limit (SMS) vs. 1600 (MMS); link-shorteners flag as spam
6. Send time restrictions — TCPA 8am-9pm recipient local time enforcement
7. Subscription incentive — opt-in offer benchmarks by vertical
8. Deliverability differences — SMS carriers filter differently; carrier-specific opt-in health

## KB integration

- Reference `{{KNOWLEDGE_BASE_ROOT}}/retail-sales-enablement/` for retention and customer-experience context

## Example filled-in briefs

- "Evaluate Klaviyo vs. Attentive vs. Postscript for a $50M DTC brand adding SMS to existing Klaviyo — cost model, migration effort, feature parity"
- "Research lifecycle strategy at 5 premium coffee subscription brands: Blue Bottle, Trade Coffee, Atlas Coffee, Driftaway, Bean Box — flow architecture, SMS adoption, win-back tactics"
- "Research deliverability benchmarks for ecommerce senders 500K-2M list size — what's Gmail primary inbox placement, complaint rate, unsubscribe rate best-in-class vs. median?"
- "Research Klaviyo Predictive Analytics + Segmentation 2025 feature set and compare to Braze Intelligent Journeys / Iterable AI — does predictive actually lift revenue per message in real data, or is it theater?"
- "Research SMS compliance requirements across US (TCPA), EU (GDPR + member-state variations), Canada (CASL), UK (PECR) for a multi-region DTC launch"
