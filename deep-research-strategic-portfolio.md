# Deep Research — Strategic Portfolio Design Archetype

> **Purpose:** produce a practice-strategy / portfolio-design document — designing a product portfolio, service offering lineup, go-to-market plan, vertical plays, or any set of strategic choices where you need to pick anchors, specify what to build / sell / offer, and sequence the rollout.
>
> **Master template:** `deep-research-prompt-master.md`.
>
> **Primary Deep Research provider:** Claude Research (strongest at reasoning against user-specific context — delivery model, talent/capability bench, existing constraints). Secondary: ChatGPT DR. Tertiary: Gemini DR.
>
> **Domain-agnostic:** works for any portfolio-design task — SaaS product portfolio, service offerings (agency / consultancy / platform), go-to-market plans, vertical strategies, channel/partnership portfolio, hiring plan, M&A target list, product-line extensions, content/editorial portfolio, research agenda, internal platform capability portfolio.

---

## When to use this archetype

- Designing a new product / service / offering portfolio from scratch
- Adding a new line to an existing business (new vertical, new service tier, new channel)
- Productizing expertise into repeatable offerings
- Go-to-market planning for a specific product or vertical
- Channel / partnership / ecosystem strategy
- Sequencing a roadmap under capacity constraints
- Hiring / org-design plan with portfolio logic (what roles for what outcomes)
- M&A target landscape or build-vs-buy decision across multiple candidates

## When to combine with another archetype

- **After** a Competitive landscape brief — the landscape informs *what* the portfolio should contain; this archetype designs the actual portfolio
- **After** a Technical reference brief — the technical evaluation informs what's feasible; this archetype designs the offerings on top
- **Inside** a Strategic portfolio brief, you'll often embed competitive-landscape and technical-reference sub-sections — that's fine; keep them focused on portfolio implications

---

## THE PROMPT — copy from here

I'm designing **{{PORTFOLIO_NAME — e.g., "our agentic AI practice," "our Series B product roadmap," "our DTC vertical expansion," "our partnerships strategy," "our hiring plan for H1"}}** for **{{ORGANIZATION_NAME}}**, a **{{ORGANIZATION_TYPE — e.g., specialist-network consultancy, vertical SaaS, DTC brand, B2B agency, internal platform team, portfolio holding company}}**.

I want to productize / specify a set of **{{OFFERING_TYPE — e.g., offerings, products, services, channels, verticals, hires, M&A targets, content tracks, research programs}}** that leverage **{{ENABLING_CAPABILITY — technology, talent, methodology, relationship, asset, or IP}}** to solve real problems for **{{TARGET — customers / users / buyers / partners / stakeholders}}**, scoped and sequenced to fit the organization's existing delivery model.

## Context on {{ORGANIZATION_NAME}} (don't re-derive)

- **Delivery model:** {{describe — how work gets done, who does it, in what cadence}}
- **Scope discipline:** {{e.g., "productized sprints ≤30 days," "agile 2-week cycles with quarterly milestones," "one flagship product per 18 months + extensions"}}
- **Positioning:** {{current one-liner}}
- **Core target segments:** {{verticals · company-size band · buyer personas · geographic or channel focus}}
- **Existing lines / capabilities:** {{list — the current portfolio or capability set}}
- **Differentiated assets:** {{what the organization uniquely has — talent depth, proprietary tech, customer relationships, data, brand, distribution}}
- **Budget / capacity envelope:** {{headcount, budget, time horizon}}

## Context on {{ENABLING_CAPABILITY}} (don't re-derive)

{{Summarize the enabling capability — its current state, proof points, limitations, ecosystem. Include pricing if relevant, technical specifications if relevant, vendor relationships if relevant. See master template for guidance on what to include.}}

## What I want you to research and produce — all framed toward {{ORGANIZATION_NAME}}'s specific use

### 1. Landscape scan — who's already playing in this space?

Research the competitive and adjacent landscape for **{{PORTFOLIO_TYPE}}** offerings targeting **{{TARGET_SEGMENT}}**:

a. **Direct competitors** — {{list 6-12 named organizations}}: what exact offerings, deliverables, price bands, vertical focus, proof points?

b. **Adjacent players** — {{categories one step over — e.g., "AI-native consultancies" if you're a traditional agency adding AI, or "full-stack platforms" if you're a specialized tool}}: where are they winning, and where do they leave service-provider / product / positioning gaps?

c. **Upstream talent / capability suppliers** — {{where the talent or capability your offering depends on comes from — freelancer networks, agency trainees, AI bootcamps, etc.}}

d. **Tool / platform vendors bolting on {{CATEGORY}} offerings** — {{vendors that might displace your offering by building it in-house to their product}}: which are landing in real accounts, where do they leave gaps?

e. **[optional — delete if not applicable] Vertical-specific vendors** — {{vertical-tool ecosystem that might compete in one segment}}

For each competitor or category: offerings · deliverables · price bands · vertical focus · proof points. **Where are the gaps {{ORGANIZATION_NAME}}'s model can wedge into?**

### 2. Buyer / target demand signals

What are **{{ORGANIZATION_NAME}}'s target {{buyers/users/partners/stakeholders}}** actually asking for?

- Job postings from target-title buyers mentioning {{ENABLING_CAPABILITY}} / {{CATEGORY}} responsibilities — what skills, what scope, what budget?
- RFP language in the space — {{RFP databases, public procurement, FOIA, Agency Spotter, Clutch, G2 buyer intent}}
- Earnings-call / board-deck mentions from public companies about {{category}} investment priorities
- Operator voice on {{industry podcasts · LinkedIn · target community Slack/Discord groups · Reddit · Twitter/X}}
- Analyst demand signals: {{relevant Gartner MQs, Forrester Waves, IDC forecasts}} or fallbacks (a16z / SaaStr / Lenny's / sector newsletters)

**Synthesize the 5-10 most frequently articulated pain points** {{ORGANIZATION_NAME}}'s targets voice right now. Direct quotes with source links where possible.

### 3. Case-study and proof-point inventory

Collect the strongest published case studies as of **{{DATE}}** of **{{ENABLING_CAPABILITY}}** deployed against **{{TARGET_PROBLEM}}** — organized by {{ORGANIZATION_NAME}}'s service/product line.

For each case study:

- Who built it (vendor · service provider · in-house team)
- Who commissioned / deployed it (named client if public)
- **Measurable outcome** (specific numbers, not vague claims)
- Tools / architecture / methodology used
- Quotable headline number for sales-deck / investor-deck / internal-pitch use

This becomes **{{ORGANIZATION_NAME}}'s ammunition.** Organize so a seller / product manager / internal champion can find the right proof point per portfolio slot in <30 seconds.

### 4. Pricing / economics intelligence

Surface real current prices and economics for:

a. **Implementation sprints / upfront / launch fees** — fixed-scope project pricing with typical ranges
b. **Ongoing / recurring economics** — monthly retainers, subscriptions, usage-based, hybrid models
c. **Category features bundled into existing {{vendor/platform/competitor}} products** — what's the embedded value vs. standalone?
d. **Fractional / advisory / strategic-tier pricing** — fractional heads, advisor retainers, specialist bench rates

Build a **pricing / economics comparison table** {{ORGANIZATION_NAME}} can anchor against. Include **source per data point** (case study link, public rate card, procurement forum thread, Glassdoor data).

### 5. "Who's winning what" intelligence

Which organizations are winning the headline {{CATEGORY}} engagements / deals / placements right now?

Surface from LinkedIn announcements · press releases · earnings-call customer mentions · industry trade pubs · podcast interviews.

**Pattern-match:** what's getting bought / placed / adopted, by whom, from whom, at what scale?

### 6. Objection-handling research

What are the **10 most common buyer / target objections** to {{CATEGORY}} offerings?

For each:
- The objection as articulated (direct quote where possible)
- The **strongest response pattern** used by successful sellers — with specific evidence, stats, or case-study references
- Categories to mine: privacy/security · cost · ROI skepticism · lock-in fear · build-vs-buy bias · readiness concerns · compliance/regulatory · talent/capability concerns · integration complexity · measurement/attribution difficulty

### 7. {{ORGANIZATION_NAME}}'s portfolio — design {{10-15}} {{OFFERING_TYPE}} slots

Design a portfolio of **{{ENABLING_CAPABILITY}}-powered {{OFFERING_TYPE}}** that fits {{ORGANIZATION_NAME}}'s **{{scope discipline}}**. Group by service / product / vertical line.

For each slot in the portfolio, specify:

- **Name + 1-line pitch**
- **Exact problem / job-to-be-done** the target is hiring this for
- **What gets built / delivered** — specifics, not abstractions
- **Scope fit** — how it fits {{scope discipline}}: what ships in {{timebox 1}} / {{timebox 2}} / {{timebox 3}} / {{timebox 4}}
- **Pricing model:** fixed / recurring / hybrid / usage-based — with $ bands based on pricing research (Section 4)
- **Staffing / capability model:** who from the organization's bench / platform delivers it
- **Success metric + proof artifact** delivered to target
- **Upsell / continuation arc** — what the follow-on looks like
- **Required pre-qualification** — who is NOT a fit for this slot

### 8. High-leverage anchor offerings — top 3

Of the {{10-15}} portfolio slots, identify the **3 most defensible and most scalable** slots {{ORGANIZATION_NAME}} should lead with.

Scoring rubric:
- Clarity of ROI / value to target
- {{ORGANIZATION_NAME}}'s existing talent / capability / asset strength
- Productizability — ability to template across targets, not bespoke every time
- Competitive moat — hard for a generic player to replicate
- Upsell arc — does landing it naturally create the next engagement?
- Strategic fit — does it strengthen the organization's positioning, not dilute it?

**Produce a 1-page anchor brief for each of the 3** — pitch, target profile, deliverable, pricing, staffing, proof point, upsell arc.

### 9. Vertical / segment plays

{{ORGANIZATION_NAME}}'s strongest target segments are **{{top verticals}}**. Produce segment-specific offerings / plays:

- **{{SEGMENT_1}}:** {{3-5 specific offerings or plays}} — with target problem, who at the target buys it, proof-of-concept scope
- **{{SEGMENT_2}}:** {{3-5 specific plays}}
- **{{SEGMENT_3}}:** {{3-5 specific plays}}
- **{{SEGMENT_4}}:** {{3-5 specific plays}}

### 10. Target qualification rubric

Not every target is a fit. Build a scorecard {{ORGANIZATION_NAME}} can use at intake to determine **readiness** for the category of offerings. Include:

- Data / infrastructure readiness
- Existing {{category}} maturity
- Capacity for the change the offering requires
- Compliance / regulatory constraints
- Volume / scale signals — is there enough of {{X}} to justify this?
- Budget / economics signals — can this target actually write a {{$X}}-{{$Y}} check?
- Stakeholder alignment — is the decision-maker identified?

**Provide a scoring worked example** — one real or plausible target profile scored end-to-end.

### 11. Competitive moat / positioning

What's {{ORGANIZATION_NAME}}'s **defensible positioning** vs. generic competitors?

Consider:
- Unique assets (talent / IP / data / relationships / distribution)
- Accountability model (outcome-accountable vs. activity-billed)
- Integration with existing capabilities (vs. standalone strategy engagements)
- Delivery primitive that rivals can't easily copy
- Operator credibility vs. pure consulting

**Write the positioning statement** — one paragraph, ready to appear on website / in sales conversation / in pitch deck.

### 12. Internal enablement plan

What does {{ORGANIZATION_NAME}} need to stand up this portfolio?

- **Talent to hire / train:** {{specific roles, seniority, target count}}
- **Platform / capability investments:** {{shared infrastructure, templates, automation, tools}}
- **Process changes:** intake, scoping, QA, post-launch monitoring, review cadence
- **Risk management:** client/customer-data handling, error/hallucination policies, SLAs, insurance posture
- **Change management:** how to introduce this to existing team / customers / partners without disrupting current work
- **Investment envelope:** {{budget · headcount · timeline}}

### 13. Anti-offerings — what {{ORGANIZATION_NAME}} should explicitly NOT do

Identify **3-5 tempting-but-wrong** slots for this organization. Examples:

- "Strategy consulting" without deliverables
- One-shot implementation with no retention
- Anything where a lighter alternative would work better
- Anything where compliance / regulatory risk outweighs upside
- Training workshops as a standalone line (vs. as onboarding to an offering)
- Offerings that dilute positioning into generic commodity space

For each anti-offering: **why tempting, why wrong for this organization.**

### 14. Go-to-market plan

How does {{ORGANIZATION_NAME}} actually bring this to market?

- **Existing-target upsell sequences** — who's primed, whose contract / relationship is due for expansion?
- **New-target acquisition motion** — positioning updates, collateral rewrites, sales play design
- **Flagship proof path** — which target goes first and why? How is the case study developed?
- **Content / thought-leadership angle** — podcast appearances, long-form LinkedIn, speaking slots, industry analyst briefings
- **Pricing experiments** — what to test in the first 90 days vs. lock in afterward
- **Partner channels** — {{relevant ecosystem partners: platform partner programs, referral networks, alliance programs, reseller channels}}
- **Internal activation** — how the organization's own team learns to sell / deliver the new portfolio

### 15. 12-month roadmap

Quarter-by-quarter plan from 0 to a full productized practice.

- **Q1:** what ships? what's learned? what's the flagship target?
- **Q2:** what ships? what's locked in from Q1 learnings? what bench is added?
- **Q3:** what scales? what consolidates? what segments are prioritized?
- **Q4:** what's the revenue / adoption / outcome target? what's the proof point for the next phase (fundraising, strategic hire, press moment)?

**Realistic end-of-Q4 target** with leading indicators per quarter — the signals you'd watch monthly to know if the portfolio is working.

## Deliverable

A **{{5000-8000}}** word practice-strategy / portfolio-design document with:

- **Executive summary** (1 page — 3 sharpest insights up top)
- **Landscape section** (tables by category)
- **Buyer / target demand signals** (top 5-10 pain points, cited)
- **Case-study inventory** (sales-ready / pitch-ready, organized by portfolio line)
- **Pricing / economics comparison table** (with sources per data point)
- **"Who's winning what" intelligence**
- **Objection-handling playbook** (10 × response patterns)
- **Portfolio** ({{10-15}} slot cards, 1 page each, in organization's native format)
- **Top-3 anchor briefs** (1 page each)
- **Segment / vertical plays**
- **Qualification rubric + worked example**
- **Positioning statement + competitive moat**
- **Internal enablement plan**
- **Anti-offerings list**
- **Go-to-market plan**
- **12-month roadmap with quarterly milestones + leading indicators**
- **Methodology section**

## Source priority

**Prioritize:** company websites · published case studies · press releases · analyst reports · earnings calls · LinkedIn announcements from named executives · podcast transcripts with named operators · SEC filings · procurement forum discussions.

**De-prioritize:** thin listicles · marketing-fluff blogs · speculative threads · AI-generated "top 10" content · vendor-sponsored case studies that read as PR.

**Every insight should be directly usable** in a live sales conversation, pitch-deck slide, roadmap review, investor meeting, or internal briefing — not an abstract strategy frame.

## DNA check (non-negotiable)

The deliverable must reflect **{{ORGANIZATION_NAME}}'s specific DNA** — not generic category-transformation advice:

- **Offerings fit the scope discipline.** {{e.g., "Fixed-scope sprints beat open-ended retainers" · "Productized SKUs beat custom projects"}}
- **{{Accountability model}} beats {{alternative}}.** {{e.g., "Outcome-accountable pricing beats hourly" · "Self-serve adoption beats long enterprise deals"}}
- **{{Delivery primitive}} beats {{alternative}}.** {{e.g., "Specialists + operators beat pure engineers" · "Vertical depth beats horizontal coverage"}}
- **Every slot should feel like "what happens when {{distinctive capability}} meets {{enabling technology}}"** — not "we'll build you a generic {{thing}}."

Generic transformation advice doesn't apply. {{ORGANIZATION_NAME}}'s targets are **{{specific target archetype}}** who need specific outputs solving specific problems — not a strategy roadmap.

---

## Dependencies & Capabilities Callout

### Required minimum

- Web search + web fetch
- At least one Deep Research provider (Claude Research preferred for reasoning against organization-specific DNA)

### Strongly recommended

- **Agentic multi-source research skill** — for the competitive scan, buyer-voice mining, pricing intelligence, named-account mining, RFP language extraction
- **Research-synthesizer subagent** — reconcile findings across multi-provider runs
- **Organizational-context researcher** — if your organization has a Slack / Notion / internal-comms archive where past strategic discussions live, search it first

### External accounts that raise the ceiling

- **Customer / account intelligence:** LinkedIn Sales Navigator · ZoomInfo · Apollo. **Fallback:** LinkedIn public profiles + press releases + podcast transcripts
- **Analyst reports:** Gartner · Forrester · IDC · CB Insights. **Fallback:** a16z · Sequoia · Battery · SaaStr · Lenny's · First Round · sector newsletters
- **Pricing / review data:** G2 · Capterra · Clutch · TrustPilot · Gartner Peer Insights. **Fallback:** Reddit communities · operator Twitter · agency-review blog posts
- **Compensation / hiring:** Levels.fyi · Glassdoor. **Fallback:** LinkedIn job postings with salary bands (required in many US states)
- **Ad libraries (all free):** Meta · Google · TikTok · LinkedIn
- **Wayback Machine** (free) — positioning drift, historical pricing pages
- **Industry podcasts** — most are free; transcribe key episodes via Rev.com / Whisper / AssemblyAI if transcripts aren't published

### Fallback protocol

Substitute free/open sources and document in Methodology. A brief that used a16z + SaaStr + Lenny's instead of Gartner is still usable; a brief that silently omits coverage is not.

### Organization-specific context files (attach to DR provider at prompt start)

Dramatically improves deliverable fit to the organization's DNA:

- Current positioning one-pager or deck
- Existing service-line / product-line definitions
- Sample prior engagement scopes / SOWs / case studies (anonymized if needed)
- Talent / capability bench summary (roles, specialist depth, current utilization)
- Known competitor list with competitive-intel notes
- Current financial envelope / capacity constraints
- Recent board-level strategic decisions (if shareable)

### Example filled-in use cases (diverse domains)

- **Consultancy / agency practice design:** "I'm designing our agentic AI consulting practice for a specialist-network growth consultancy; target clients $10M-$500M DTC / ecommerce / B2B SaaS"
- **SaaS product portfolio:** "I'm designing Q2 product-line extensions for a $30M ARR vertical SaaS serving dental practices, with budget for 4 new features"
- **DTC brand expansion:** "I'm designing a 3-SKU extension for our $15M premium outdoor-gear brand — which adjacent categories?"
- **Channel / partnership strategy:** "I'm designing our partner portfolio for a growth-stage B2B SaaS — which ecosystems to join, in what sequence, at what investment"
- **Internal platform capability:** "I'm designing the capability roadmap for our internal data-platform team over the next 18 months"
- **Hiring plan:** "I'm designing H1 engineering hires for a Series B SaaS — which specialties, in what sequence, to unblock what outcomes"
- **M&A target portfolio:** "I'm designing the target list for our vertical roll-up strategy in HVAC software"
- **Content / editorial portfolio:** "I'm designing the content track portfolio for a new B2B media brand in developer tooling — which topics, in what formats, targeting what buyers"
- **Research agenda:** "I'm designing the research portfolio for a small AI-safety lab over the next 24 months"
- **Marketing operations tech stack:** "I'm designing the martech rebuild for a 200-person SaaS — which tools for which jobs, in what rollout order"
