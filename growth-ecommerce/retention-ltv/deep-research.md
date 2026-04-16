# Retention / LTV — Deep Research Template

> **Inherits from:** `~/.claude/templates/deep-research-competitive-landscape.md` or `deep-research-technical-reference.md`

---

## Use cases

- **Category LTV:CAC benchmarks** — what's typical for your vertical / stage / business model?
- **Retention tool evaluation** — Retention.com / Churnkey / ProfitWell / Churnbuster / Klaviyo native / custom
- **Loyalty program research** — Smile / Yotpo Loyalty / LoyaltyLion / Stamped / Rise.ai / custom
- **Subscription retention benchmarks** — monthly churn by category, win-back effectiveness, pause-vs-cancel dynamics
- **LTV modeling methodology** — probabilistic vs. deterministic; Shifted Beta Geometric vs. Pareto/NBD vs. simple cohort
- **Competitor retention teardown** — what are category leaders doing to retain?

## Opinionated source priorities

**Prioritize:**

- **Academic research** — Peter Fader's work on BTYD models; Sunil Gupta on LTV; Daniel McCarthy on recurring-revenue modeling
- **Public-company cohort disclosures** — in S-1 filings and earnings decks (Warby Parker, Allbirds, Figs, Olaplex, etc. have published cohort data)
- **Operator research** — Lenny's Newsletter (PLG retention), Bessemer Cloud Index (SaaS retention benchmarks), Battery OpenCloud
- **Category-specific benchmarks** — Recharge (subscription), Bold (subscription), Shopify reports (DTC)
- **Podcasts** — Lenny's Podcast (PLG), Operators (DTC), 2X eCommerce (DTC)

**De-prioritize:**

- Generic "how to improve retention" listicles
- Loyalty-platform vendor marketing (treat as positioning)
- AI-generated LinkedIn "10 retention hacks"

## Question-set specializations

### For category LTV benchmarks:

1. Median 1yr / 2yr / 3yr LTV by category
2. Typical LTV:CAC ratios that survive — public company data
3. Cohort retention curves — week 1 / week 12 / month 12 for your vertical
4. New-customer vs. repeat-customer ratio at healthy companies
5. Seasonality in cohort quality — Q4 cohorts vs. mid-year cohorts
6. Channel-level LTV variance — paid social vs. paid search vs. organic vs. referral

### For subscription retention research:

1. Monthly churn rate benchmarks — CPG, beauty, coffee, meal kits, pet, SaaS
2. Pause-rate benchmarks (when offered) — what % pause vs. cancel
3. Win-back rates — what % return within 30 / 90 / 180 days
4. Price increase impact — churn elasticity by category
5. Cohort-quality benchmarks — what's "good" first-month retention
6. Subscription-model variant results — subscribe-and-save vs. committed vs. flex

### For loyalty program evaluation:

1. Measured LTV lift at peer brands — not vanity engagement, real revenue
2. Pricing model comparison — per-member / flat / revenue-share
3. Feature set — tiers, referrals, reviews, points, VIP
4. Integration depth — Shopify / Klaviyo / Yotpo / Gorgias
5. Time-to-value — realistic weeks from launch to measurable lift
6. Exit cost — member-data portability

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/mmm-and-response-curves/` for LTV modeling + retention-curve mathematics
- `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/` for segmentation frameworks

## Example filled-in briefs

- "Research LTV:CAC benchmarks for premium DTC beauty brands $10-$50M revenue — 1yr LTV, payback period, repeat-purchase rate by cohort month"
- "Research subscription churn benchmarks for CPG beauty subscription boxes $20-$60 AOV — Month-1, Month-3, Month-12 retention curves"
- "Evaluate LoyaltyLion vs. Yotpo Loyalty vs. Smile for $25M DTC brand — feature set, pricing, measured LTV impact at published case-study brands"
- "Research BTYD model performance (Shifted Beta Geometric, Pareto/NBD) at ecommerce scale — when does it outperform simple cohort analysis, what's the data requirement?"
- "Research retention strategies at 5 category-leading DTC brands (Allbirds, Warby Parker, Figs, Olaplex, Olipop) — pull from S-1s and earnings disclosures"
