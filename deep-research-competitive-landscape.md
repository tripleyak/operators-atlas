# Deep Research — Competitive & Market Landscape Archetype

> **Purpose:** produce a strategic brief on a product, service, category, or market position — covering competitors, buyer demand signals, white-space, and 12-month trajectory.
>
> **Master template:** `deep-research-prompt-master.md` (shared skeleton, dependencies, provider routing, quality bar).
>
> **Primary Deep Research provider:** ChatGPT Deep Research (strongest on strategy synthesis). Secondary: Claude Research. Tertiary: Gemini Deep Research. For high-stakes briefs run all three and reconcile.
>
> **Domain-agnostic:** works for any category — software products, hardware, consumer brands, B2B services, platforms, infrastructure, content networks, marketplaces, financial products, educational programs, anything with competitors and buyers.

---

## When to use this archetype

- Entering a new market or category
- Positioning a new product or service launch
- Evaluating competitive threat from an incumbent move
- Quarterly / annual market refresh
- Preparing for a board presentation on market position
- Supporting a fundraising deck with credible market-size and competitive-dynamics evidence
- Designing a go-to-market strategy that needs to survive a buyer-side comparison shop

## When to combine with another archetype

- Combine with **Technical reference** when evaluating a platform that has both a competitive positioning dimension AND a build-vs-buy decision (e.g., "Should we build on Platform X or compete with them?")
- Combine with **Strategic portfolio** when the competitive landscape informs which offerings to productize (e.g., "Given the competitive white-space, what portfolio should we ship?")

---

## THE PROMPT — copy from here

Research the competitive landscape for **{{SUBJECT — product category, service line, market segment, or positioning question}}** as of **{{DATE}}**, centered on **{{ANCHOR_ENTITY_OR_PRODUCT}}** ({{launch date · inflection event · announcement · your own project if you're the anchor}}).

## Context I already have (don't re-derive)

{{Paragraph or bulleted list of every fact the researcher should treat as given. Include:

- Subject/category definition and scope
- The anchor's positioning, pricing, and launch/inflection specifics
- Known marquee customers, case studies, proof points
- Architecture / delivery / production primitives the anchor uses
- Community / press / analyst framing already circulating (with brief assessment — is it accurate?)
- What's been ruled out from prior research — hypotheses already tested and discarded
- Internal context: why this research is happening (fundraising, board meeting, launch prep, competitive defense, M&A diligence, etc.)

Err on the side of more. A 500-word context block prevents 2000 words of wasted re-derivation.}}

## What I want you to research

### 1. Competitive positioning map

Position **{{ANCHOR}}** against:

- **{{PRIMARY_COMPETITORS}}** — direct substitutes in the same category, with the same buyer, at similar price points. Include 3-8 named competitors.
- **{{ADJACENT_COMPETITORS}}** — one category over, but competing for the same buyer budget. Include 3-5 named competitors.
- **{{OPEN_SOURCE_OR_SELF_BUILD_ALTERNATIVES}}** — if applicable. When "build it yourself" or "use an open-source stack" is a real option for buyers, this counts as a competitor.
- **{{DOWNSTREAM_INTEGRATORS_OR_BUNDLERS}}** — if applicable. When a bigger platform can fold your category in as a feature, that's existential competition, not adjacent.

For each competitor, produce:

- **Offering primitives:** architecture / delivery model / service model / production approach
- **Pricing model:** anchors, tiers, usage metrics, visible rate cards, known enterprise discount patterns
- **Differentiators vs. the anchor:** 2-4 bullets on what they do that's distinct
- **Gap list:** what they don't do that the anchor does, and vice versa
- **{{CATEGORY-SPECIFIC_DIMENSION_1}}** — e.g., enterprise auth/compliance posture (for B2B SaaS), retail channel coverage (for consumer brands), certification credentials (for services), regulatory footprint (for fintech/healthtech)
- **{{CATEGORY-SPECIFIC_DIMENSION_2}}** — another dimension relevant to your category
- **Momentum signals:** recent funding, hiring velocity, customer-count growth, partnership announcements, product-launch cadence

### 2. Buyer-side demand signals

What are real buyers in this space actually evaluating? Surface:

- **Analyst coverage:** {{Gartner Magic Quadrants · Forrester Waves · IDC MarketScapes}} — or free substitutes: {{a16z · Sequoia · Battery · Redpoint · SaaStr · Lenny's · First Round · relevant newsletters}}
- **Conference talks + keynotes** from the last 12 months at {{relevant industry conferences}}
- **Earnings call mentions** for public companies in the buyer segment — what are they saying about this category?
- **RFP language** and procurement signals — search {{RFP databases · G2 buyer intent · Clutch · Agency Spotter · public tender portals · FreelancerMap}}
- **Community voice:** {{relevant subreddits · LinkedIn communities · podcasts · operator Slack groups · industry Discord servers · Twitter/X operator accounts}}
- **Job postings** from {{target buyer titles}} mentioning this category — what skills, tools, and responsibilities are being asked for? What does that imply about where buyers are investing?

**Synthesize: the 5-10 most frequently articulated pain points** buyers voice in this space right now. Direct quotes with source links where possible.

### 3. Strategic trajectory

What does **{{ANCHOR}}'s** current position imply about its 12-month roadmap? Connect to:

- Adjacent product / SKU launches or rumored products
- Pricing moves — tier changes, usage-metric changes, enterprise-discount patterns
- Partnership announcements — who's being tied to whom, and what's the strategic read?
- Acquisition patterns — who the anchor (or its competitors) is buying or being bought by
- Regulatory / compliance tailwinds or headwinds
- Ecosystem shifts — platform changes, API deprecations, integration opportunities

Is this the **{{strategic positioning claim being tested}}** the press frames it as, or is it narrower / broader / different? Make a clear call and defend it.

### 4. Who's at risk (threat tiers)

Which startups, categories, and incumbents are most threatened by **{{ANCHOR}}'s** trajectory?

Evaluate by threat tier:

- **Tier 1 (existential):** {{categories directly displaced}} — will likely be swallowed or forced to pivot within 12-18 months
- **Tier 2 (margin compression):** {{categories where anchor's features become table-stakes}} — survive but with reduced pricing power
- **Tier 3 (feature-becomes-bundle):** {{standalone tools that get absorbed}} — still exist but lose strategic independence

For each named competitor:

- **Specific reason** they're at risk
- **Timeline to impact** (immediate / 6-12 months / 18+ months)
- **Defenses they've announced** (or "none visible")
- **Escape hatches** — verticals, segments, or pivots they could run

### 5. [optional — delete if not applicable] Pricing intelligence

Surface real dollar figures for:

- **Implementation / onboarding fees** — fixed-scope project pricing
- **Ongoing subscription / retainer tiers** — monthly or annual anchors
- **Usage-based pricing** — unit metrics and per-unit costs
- **Enterprise contract benchmarks** — from leaks, case studies, procurement forums, public-sector contracts (FOIA-able in some jurisdictions)
- **Bundled pricing** — what's thrown in "free" when the main product is purchased
- **Hidden costs** — onboarding services, integration consulting, required add-ons, support tiers

Build a **pricing comparison table** with one row per competitor, columns for pricing model type, anchors, notable discount patterns, and source for each data point.

### 6. [optional — delete if not applicable] Named-account intelligence

Which customers are buying what, from whom, at what scale?

Surface from:

- LinkedIn announcement posts (client hires, new engagements, featured customers)
- Press releases from vendors / agencies
- Earnings call mentions when public buyers name their service providers
- Industry trade publications ({{relevant pubs for your space}})
- Case study publications (treat with care — these are marketing, not reporting)

**Pattern-match:** what's getting bought, by which buyer profiles, from which vendors, at what deal sizes? Which vendor is winning the category-defining logos right now?

### 7. [optional — delete if not applicable] Objection-handling research

What are the **10 most common buyer objections** to the anchor's category right now? For each:

- The objection as it's articulated (direct quote where possible)
- The strongest response pattern used by successful sellers — with specific evidence, stats, or case-study references
- Categories to mine: privacy/security · cost · ROI skepticism · lock-in fear · build-vs-buy bias · readiness concerns · compliance/regulatory · talent-retention risk · integration complexity · measurement/attribution difficulty

### 8. [optional — delete if not applicable] Partner / channel landscape

Which ecosystems should a vendor in this space plug into to drive demand?

For each relevant ecosystem (e.g., {{App Store partner programs · Solutions Partner programs · industry associations · marketplace listings}}):

- What does partnership buy (leads / co-marketing / certification / API access / co-selling)
- Qualification bar (requirements, volume minimums, certifications)
- Competitive density (how many other vendors are already listed)
- ROI signals (what does a typical partnered vendor get out of it)

### 9. Positioning white-space analysis

Given everything above, where is the defensible position for **{{ANCHOR}}**?

Map competitors on 3 axes relevant to your category. Suggestions:

- **Horizontal vs. vertical** (general-purpose vs. specialized-by-industry)
- **Enterprise-ready vs. developer-first**
- **Productized / fixed-scope vs. consultative / bespoke**
- **Self-serve vs. sales-assisted**
- **Price-anchor vs. premium-anchor**
- **Regulated-domain ready vs. general-purpose**
- **Single-product vs. platform**

Plot 10-15 direct and adjacent competitors on the chosen 3 axes. Circle where **{{ANCHOR}}** has a defensible corner — or declare it doesn't have one and recommend a repositioning move.

### 10. 12-month outlook (bull / base / bear)

By **{{DATE + 12 months}}**:

- **Bull case:** what does success look like for the anchor? What moves would be required? What metrics would prove success? What external conditions would support it?
- **Base case:** given current signals, what's the realistic trajectory?
- **Bear case:** what kills this? What competitor move, regulatory change, pricing war, customer-behavior shift, or market downturn would invalidate the anchor's positioning?

For each scenario, list **leading indicators to track** — the metrics and signals you'd watch quarterly to know which scenario is playing out.

## Deliverable

A **{{4000-6000 for tighter briefs · 6000-8000 for board-facing briefs}}** word strategic brief with:

- **Executive summary** (1 page — 3 sharpest insights up top, bold each)
- **Competitive positioning matrix** — table, named competitors × evaluation dimensions
- **Per-competitor deep dives** — 1-2 paragraphs each, with a "what they beat us on / what we beat them on" note
- **Buyer demand signals synthesis** — top 5-10 articulated pain points, cited, with quote snippets
- **Strategic trajectory** — what the anchor's moves imply for 12 months, with bold claim + defense
- **Who wins / who loses** — threat tiers with named competitors
- [Pricing comparison table — if included]
- [Named-account intelligence — if included]
- [Objection-handling playbook — if included]
- [Partner-channel recommendation matrix — if included]
- **Positioning white-space map** — 3 axes with all named competitors plotted, anchor's corner circled
- **12-month scenarios** — bull / base / bear with leading indicators per scenario
- **Methodology section** — providers used, sources available vs. unavailable, date range, confidence level per section

## Source priority

**Prioritize:** SEC filings · earnings call transcripts · official engineering/product blogs · published enterprise case studies · LinkedIn posts from named executives · conference talks with published recordings · press releases · analyst reports · procurement forum discussions with actual data.

**De-prioritize:** YouTube reaction videos (unless creator is a primary source) · Twitter/X takes without operator credentials · thin listicle blogs · "what is X" explainers · speculative Medium threads · competitor marketing pages (treat as positioning data, not truth).

**Required:** every numeric claim cites a source. Every positioning claim notes a countervailing view. Every dollar figure has a methodology note.

---

## Dependencies & Capabilities Callout

### Required minimum

- Web search + web fetch (tool or provider built-in)
- At least one Deep Research provider (ChatGPT DR preferred for this archetype)

### Strongly recommended

- **Agentic multi-source research skill** (signalsweep / custom RAG / similar) — aggregates SEC EDGAR, earnings, analyst reports, LinkedIn, review sites, ad libraries, podcast transcripts, Wayback Machine. Dramatically raises quality of the competitive-scan and demand-signal sections.
- **Research-synthesizer subagent** — consolidate findings across multi-provider runs
- **Issue-intelligence-analyst subagent** — if evaluating competitors with public issue trackers (open source, platform products)

### External accounts that raise the ceiling

- **Analyst subscriptions:** Gartner · Forrester · IDC · CB Insights. **Fallback:** a16z Marketplace · Sequoia perspectives · Battery OpenCloud · Redpoint OpenView · SaaStr · Lenny's · First Round · sector-specific newsletters
- **Financial data:** Seeking Alpha · Motley Fool · Yahoo Finance · company IR pages. **Fallback:** direct IR pages + Rev.com transcription for key earnings calls not publicly transcribed
- **Customer intelligence:** LinkedIn Sales Navigator · ZoomInfo · Apollo. **Fallback:** LinkedIn public profiles + press release crawling + earnings customer-name mentions
- **Review/pricing:** G2 · Capterra · Clutch · TrustPilot · Gartner Peer Insights. **Fallback:** Reddit communities · operator Twitter · industry-specific review blogs
- **Ad libraries (all free, no fallback needed):** Meta Ad Library · Google Ads Transparency · TikTok Ad Library · LinkedIn Ad Library
- **Historical:** Wayback Machine CDX — free; use for positioning drift and pricing page history

### Fallback protocol

Substitute nearest free source. **Document substitution in the Methodology section.** A brief that used a16z instead of Gartner is still usable; a brief that hides source limitations is not.

### Local knowledge prerequisite

If you maintain a personal or team knowledge base on your domain, search it before web research. Prior work may already have 30-60% of the competitive map sketched. Cite KB hits in the Methodology section.

### Example filled-in use cases (diverse domains)

- **Ecommerce:** "Research the competitive landscape for Amazon PPC optimization platforms as of {{date}}, centered on Pacvue's pro-seller tier launch"
- **Growth marketing services:** "Research the competitive landscape for MMM-as-a-service providers targeting $10M-$100M DTC brands as of {{date}}"
- **Marketing operations tools:** "Research the competitive landscape for HubSpot-Salesforce sync orchestration tools as of {{date}}"
- **Workflow automation:** "Research the competitive landscape for no-code internal-tools builders as of {{date}}, centered on Retool's enterprise push"
- **Content production:** "Research the competitive landscape for AI-assisted podcast-production services as of {{date}}"
- **Consumer brand:** "Research the competitive landscape for premium pickleball paddles in the $150-$300 tier as of {{date}}, centered on Joola's new launch"
- **B2B SaaS:** "Research the competitive landscape for AI observability platforms targeting enterprise AI teams as of {{date}}"
- **Fintech:** "Research the competitive landscape for embedded-lending APIs for vertical SaaS as of {{date}}"
- **Internal tooling:** "Research the competitive landscape for LLM-based customer-support triage systems as of {{date}}"
