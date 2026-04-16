# SEO / Content Program — Bootstrap

> **Inherits from:** `~/.claude/templates/session-kickoff-bootstrap.md`
>
> **Use when:** starting a multi-session SEO or content program — topic-cluster build, content velocity ramp, SEO-driven growth program, or content-for-conversion program.

---

## Who this is for

Content marketers, SEO specialists, growth-content leads at DTC / B2B SaaS / marketplaces. Programs span 12-24 weeks for meaningful ranking gains — SEO compounds over time, so short programs rarely show decisive results.

## Opinionated defaults

### Content velocity

- **2-4 articles/week sustained.** Below 2, momentum dies; above 4, quality degrades without significant team.
- **Each article: 1,500-3,000 words** for commercial pages; 800-1,500 for quick-answer pages.
- **Publishing cadence matters more than bursts.** 2/week every week beats 8/week for a month then nothing.

### Topic strategy

- **Topic clusters, not keywords.** Pillar page + 8-15 supporting articles + internal linking graph.
- **Keyword clustering before content planning.** Use Ahrefs / SEMrush / Glimpse to group keywords by search intent before assigning topics.
- **Intent-first:** informational / commercial / transactional / navigational. Match article type to intent.

### Quality signals (E-E-A-T)

- **Author bylines with real credentials** — not "staff writer." Link to LinkedIn / bio.
- **Date stamps: published + updated.** Fresh updates signal ongoing investment.
- **Sources cited** — primary research, industry reports, expert interviews.
- **AI-generated content:** editorial review required. Pure AI content is penalized after it's crawled.

### Internal linking

- **3-5 internal links per new article** to related cluster members.
- **Pillar-page-first linking** — new articles link UP to pillar; pillar links DOWN to supporting articles.
- **No auto-generated related links** — curated only.

### Performance review

- **30/60/90-day review per article:** is it ranking? Any top-3 / top-10 rankings? Traffic trajectory?
- **Refresh cadence:** minor refresh at 6 months; major overhaul at 18 months.
- **Keyword migration tracking:** when an article shifts from ranking for target keyword to adjacent keyword, decide to update or spin off.

### Technical SEO baseline

- **Core Web Vitals pass** at LCP / INP / CLS thresholds
- **Sitemap + robots.txt clean** — no blocked resources
- **Internal 404s = 0**
- **Canonical tags on every URL**
- **hreflang for multi-region**

## Step 0 — Interview question additions

1. **Current domain authority / rating** (Ahrefs DR or Moz DA)
2. **Current organic traffic** — by page, by keyword, by intent
3. **Content backlog state** — CMS, WordPress, Webflow, custom?
4. **SEO tools in use** — Ahrefs / SEMrush / Moz / Search Console / Glimpse / Clearscope / Surfer
5. **Writer capacity** — in-house, freelance, agency, AI-assisted?
6. **Editorial process** — brief → draft → edit → SEO review → publish? Or ad-hoc?
7. **Past content performance** — top performers, duds, deleted pages
8. **Backlink profile** — organic, outreach-driven, paid (never), recent toxic links?
9. **Technical SEO baseline** — CWV, sitemap, crawl errors, schema markup
10. **Competitive content landscape** — which competitors rank for target topics?
11. **Commercial funnel** — where does organic traffic convert? (PDP, category, blog-to-lead?)

## Step 2 — Milestone template (16-week program)

```markdown
### M1 — Content Audit + Topic Cluster Mapping (week 1-2)
- Deliverable: current-content inventory; topic-cluster map; pillar-page inventory; content-to-delete / refresh / keep decisions
- Validation: every article tagged to cluster; pillar pages identified; sunset list ready
- Target: end of week 2

### M2 — Keyword Research + Priority Backlog (week 2-3)
- Deliverable: 50+ article backlog prioritized by volume × difficulty × intent × commercial value
- Validation: backlog ICE-scored; top-20 briefs written
- Target: end of week 3

### M3 — Content Production Cadence Launch (week 3+)
- Deliverable: 2-4 articles/week production rhythm
- Validation: first 4 weeks hit cadence without quality drops; editorial process working
- Target: ongoing from week 3

### M4 — Internal Linking Structure Build (week 4-6)
- Deliverable: pillar-up / support-down linking graph; audit of orphaned pages
- Validation: every cluster has ≥8 support articles linking to pillar
- Target: end of week 6

### M5 — Backlink / Authority Building (week 6+)
- Deliverable: outreach / digital PR / HARO / resource-page link campaigns
- Validation: new referring domains/month tracked; no toxic links
- Target: ongoing from week 6

### M6 — Performance Review + Refresh Cadence (ongoing past week 12)
- Deliverable: 30/60/90-day review on every article; refresh cadence locked
- Validation: top-10 articles refreshed at 6-month mark; traffic trend stable/up
- Target: ongoing
```

## Step 3 — Critical mental model

> **SEO is a compound interest game.**
>
> Quality + Consistency + Time = exponential growth.
>
> Tactics that short-circuit this (link farms, AI slop, scraped content, keyword stuffing) destroy the compound and ban you from the game. Google's algorithm has adapted; the short-term wins of 2015-2020 are 2024-2026 penalties.
>
> The corollary: measurable progress requires 6-12 months minimum. A 12-week SEO program will not move the needle on a new site. What it can do: lay foundations (topic clusters, technical SEO, editorial cadence) that pay off at month 12-18.
>
> Stakeholder alignment on time horizon is the #1 risk to SEO programs. If leadership expects 90-day traffic gains, either: extend horizon, scope to quick-win existing content, or pair with paid-search program for short-term demand.

## Step 4 — Domain validators

- **CWV:** LCP <2.5s, INP <200ms, CLS <0.1 — PageSpeed Insights weekly
- **Crawl errors:** 404s, server errors, render errors — Search Console weekly
- **Indexation:** published articles indexed within 14 days — Search Console
- **Internal linking:** every new article has 3+ links in from cluster
- **Editorial quality gate:** every article reviewed by author + editor + SEO specialist

## Step 8 — Working protocol additions

- **Never publish pure AI-generated content without editorial review.**
- **Never buy backlinks.** Ever.
- **Never keyword-stuff.** Intent-first; keyword-second.
- **Never delete historical content without redirect planning.**
- **Never change URLs without 301s** — watch rankings for 90 days post-change.
- **Always write for the user first, SEO second.** If the article doesn't help the reader, Google will notice over time.
- **Always cite primary sources.**
- **Always track refresh candidates** at the 6-month mark.

## KB integration

- `{{KNOWLEDGE_BASE_ROOT}}/content-and-edtech/wiki/_index.md` — **18 articles on content strategy, thought leadership, course creation; relevant for editorial strategy patterns**

## Common example fills

- **"Launch 100-article B2B SaaS content program over 24 weeks; target top-10 for 40+ commercial keywords"**
- **"Topic-cluster rebuild for DTC brand with 300 legacy blog posts; consolidate / delete / refresh"**
- **"SEO-driven PLG activation funnel for developer tools company — content-to-signup"**
- **"Quick-win content refresh — 20 existing articles ranking positions 8-15, target top-5"**
- **"Fix traffic collapse — diagnose March 2025 Google core update impact and remediate"**

## Hand-off

After bootstrap, use `~/.claude/templates/growth-ecommerce/seo-content/resumption.md`.
