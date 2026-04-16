# CRO — Deep Research Template

> **Inherits from:** `~/.claude/templates/deep-research-competitive-landscape.md` or `deep-research-technical-reference.md` (for testing-platform evaluations)

---

## Use cases

- **Testing platform evaluation** — VWO / Convert / Optimizely / AB Tasty / Statsig / LaunchDarkly / build-in-house
- **Category CRO benchmarks** — what's the typical CVR / AOV / cart-abandonment for ecommerce in your vertical?
- **Checkout competitive teardown** — Shopify One / Fast (RIP) / Bolt / custom — who's got the shortest funnel?
- **Personalization technology evaluation** — Dynamic Yield / Monetate / Bloomreach / in-house
- **Speed / Core Web Vitals impact research** — what's the measured revenue impact per 100ms?
- **Form / checkout UX research** — field count, address autofill, payment-method ordering

## Opinionated source priorities

**Prioritize:**

- **Academic research on A/B testing methodology** — papers from Microsoft, Google, Booking.com, LinkedIn on their experimentation platforms
- **Conference talks from testing-heavy companies** — Booking, Airbnb, Etsy, Spotify publish detailed case studies
- **Baymard Institute** — deep UX research on ecommerce, especially checkout (subscription but worth it for serious CRO)
- **NNGroup (Nielsen Norman)** — usability research, especially mobile
- **Platform-published benchmarks** — Shopify, BigCommerce, Magento (Adobe Commerce) publish category CVR data
- **Operator podcasts** — Good Decisions, Conversion Insights, Experimentation Podcast (Ronny Kohavi)

**De-prioritize:**

- Generic "top 10 CRO tactics" blogs
- Vendor-sponsored benchmarks with motivated bias
- One-anecdote case studies from agency marketing

## Question-set specializations

### For testing platform evaluation:

1. Feature comparison — visual editor, code-based, mobile apps, server-side
2. Stats engine — frequentist / Bayesian / sequential; can you access the math?
3. Integration depth — analytics, personalization, feature flags, CDP
4. Variant exposure logging — native analytics integration or custom?
5. Traffic allocation precision — URL targeting, segment targeting, QA modes
6. Pricing — traffic-based / feature-based / seat-based
7. Migration cost — test logic portability, historical data export
8. Scale — max concurrent tests, traffic ceiling, latency impact

### For category CRO benchmarks:

1. Median CVR by traffic source (organic / paid search / paid social / direct / email)
2. Median AOV and cart-abandonment by vertical
3. Checkout completion rate industry benchmark
4. Mobile vs. desktop CVR gap (usually 40-60% of desktop)
5. New vs. repeat customer CVR
6. International / shipping-friction CVR impact

### For speed / CWV impact:

1. What's the measured revenue impact per 100ms of LCP?
2. What CWV thresholds correlate with meaningful CVR change?
3. Which specific CWV (LCP / INP / CLS) moves conversion most?
4. Speed improvements at what scale justify engineering investment?

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/product-research-and-competitive-intelligence/wiki/` — for scoring frameworks and customer research that informs hypothesis generation

## Example filled-in briefs

- "Evaluate Statsig vs. VWO vs. Optimizely X vs. build-in-house for a $200M DTC brand with strong eng team"
- "Research checkout benchmarks for premium apparel $100-$500 AOV category — CVR, cart abandonment, return rate, mobile vs. desktop split"
- "Research measured revenue impact of Core Web Vitals improvements at ecommerce scale — is the 7%-per-100ms-LCP often-cited number real?"
- "Research personalization-technology ROI at $50-$100M ARR SaaS — does it move activation / conversion in measurable ways vs. cost?"
- "Research checkout-field-count research: Baymard, academic, platform data — what's the real impact of removing fields at 10% / 20% / 30% reduction?"
