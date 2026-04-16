# Deep Research Prompt — Master Template

> **Purpose:** produce a high-quality 4000-8000 word research brief from a Deep Research LLM (ChatGPT Deep Research, Gemini Deep Research, Claude Research, Grok DeepSearch, Perplexity Pro, OpenRouter Research) or from an agentic research skill (signalsweep, custom RAG pipelines, etc.).
>
> **Use when:** you need a substantive brief — a 30-minute research task, not a 30-second search. For quick facts, use plain web search.
>
> **Domain-agnostic:** works for ecommerce, SaaS, growth marketing, marketing ops, workflow automation, fintech, healthtech, consumer brands, B2B services, internal tooling, research — any business use case.

---

## Three archetype variants — pick one

| Archetype | File | Use when |
|---|---|---|
| **Competitive & market landscape** | `deep-research-competitive-landscape.md` | Positioning a product, service, or category against competitors; mapping buyer demand; identifying white-space; forecasting market shifts |
| **Technical & architectural reference** | `deep-research-technical-reference.md` | Build-vs-buy decisions; platform/SDK deep dives; architecture reconstruction; security threat modeling; vendor evaluation |
| **Strategic portfolio design** | `deep-research-strategic-portfolio.md` | Designing a product/service/offering portfolio; go-to-market plan; vertical plays; anchor choices; rollout sequence; anti-patterns |

**Combining archetypes:** real research briefs often span two archetypes (e.g., "evaluate a platform *and* design a portfolio of offerings on it"). Start with one, then borrow sections from another. Don't triple-count — if competitive intelligence informs both landscape and portfolio, write it once and reference it.

---

## The common skeleton (every archetype shares this)

Every deep-research prompt has four blocks:

1. **Context block** — "Context I already have (don't re-derive)." List every fact the researcher should treat as given. Prevents wasting half the deliverable re-explaining what you already know.
2. **Numbered research questions** — 5-15 questions, each answerable by a researcher who knows the field. No "help me understand X" — that's a conversation, not a research prompt.
3. **Deliverable spec** — explicit word count, structure (sections, tables, matrices), and format.
4. **Source priority guidance** — "Prioritize X, de-prioritize Y." Forces the researcher toward primary sources and away from AI-slop blogs.

---

## Dependencies & Capabilities Callout (global — applies to all three archetypes)

### Minimum required

- **Web search** (WebSearch tool, or the DR provider's built-in web access)
- **Web fetch** (WebFetch tool, or provider's built-in URL read)
- **At least one Deep Research provider:**
  - ChatGPT Deep Research (OpenAI Plus/Pro)
  - Gemini Deep Research (Google One AI Premium)
  - Claude Research (Claude.ai Pro/Max)
  - Grok DeepSearch (X Premium+)
  - Perplexity Pro
  - OpenRouter Research (model-router variant)

### Strongly recommended (raise the ceiling)

- **Agentic research skill** — something like signalsweep / custom RAG / multi-source research skill that aggregates across SEC EDGAR, arXiv, Semantic Scholar, earnings transcripts, analyst reports, podcast transcripts, LinkedIn, Stack Overflow, review sites, ad libraries, and more. If available, prefer it over single-provider DR for competitive/market-sensing work.
- **Research-synthesizer subagent** — consolidates findings across multiple DR runs (different providers) into one reconciled brief
- **Framework-docs-researcher subagent** — for library/framework/SDK doc mining (technical archetype)
- **Issue-intelligence-analyst subagent** — for systematic GitHub issue / user-feedback pattern analysis (technical + competitive archetypes)
- **Best-practices-researcher subagent** — for external best-practice synthesis
- **Organizational-context researcher** — if you have a Slack, Notion, or internal comms archive where decisions/constraints live (competitive + strategic archetypes)

### External accounts / APIs that raise the ceiling

- **Analyst subscriptions:** Gartner · Forrester Research · IDC · CB Insights · PitchBook. **Fallback:** a16z Marketplace · Sequoia perspectives · Battery OpenCloud · Redpoint OpenView · SaaStr · Lenny's Newsletter · First Round Review · Thomvest · Tomasz Tunguz
- **Financial/filings data:** SEC EDGAR (free) · Seeking Alpha · Motley Fool · Yahoo Finance · company IR pages. **Fallback:** direct company investor relations pages + quarterly press releases
- **GitHub API** (for issue/PR mining) — unauthenticated works for public repos; authenticated raises rate limits 83× (5K req/hr vs. 60 req/hr)
- **Customer / buyer intelligence:** LinkedIn Sales Navigator · ZoomInfo · Apollo. **Fallback:** LinkedIn public profiles + press-release crawling + earnings call transcripts where public customers name their vendors
- **Review aggregators:** G2 · Capterra · Clutch · TrustPilot · Product Hunt · Gartner Peer Insights. **Fallback:** Reddit / operator communities / industry Slack groups
- **Compensation / hiring:** Levels.fyi · Glassdoor · Payscale · H1B salary database. **Fallback:** public job-posting salary ranges (now required in many US states)
- **Ad libraries (all free):** Meta Ad Library · Google Ads Transparency Center · TikTok Ad Library · LinkedIn Ad Library
- **Historical / archival:** Wayback Machine CDX (free) — for positioning drift, pricing page history, product pivots
- **Patents / regulatory:** USPTO (PatentsView, PEDS) · EPO OPS · Federal Register · SEC XBRL · openFDA · CourtListener. All free.
- **Academic / scientific:** arXiv · Semantic Scholar · OpenAlex · PubMed · bioRxiv · medRxiv. All free.
- **Domain-specific (ecommerce-focused briefs):** Keepa · Helium10 · JungleScout · SmartScout · SimilarWeb · SEMrush · SpyFu · DataDive
- **Podcast / video transcripts:** Rev.com · Descript · YouTube auto-captions · AssemblyAI · Whisper (local)

### Fallback protocol if a capability is missing

Substitute the nearest free/open source. **Document the substitution in the deliverable's Methodology section** so the reader knows what was sacrificed. A brief that used a16z instead of Gartner is still usable; a brief that silently hides its source limitations is not.

---

## Three-provider Deep Research routing (when running multi-provider for stakes)

| Provider | Relative strength | Use as primary for |
|---|---|---|
| ChatGPT Deep Research | Strategy synthesis; cross-source reconciliation; long-form narrative | Competitive & market landscape |
| Gemini Deep Research | Technical depth; code/doc ingestion; large-context reasoning; multi-modal | Technical & architectural reference |
| Claude Research | Reasoning against user-provided context; nuance in soft-domain (positioning, buyer voice, design principles); faithful quotation | Strategic portfolio design |
| Grok DeepSearch | Real-time + X-native signal capture | News / real-time supplements (not primary) |
| Perplexity Pro | Fast citation-dense answers with source lists | Quick fact-checking + citation seed |

**For high-stakes briefs:** run the same prompt through all three primary providers and reconcile the outputs. Provider disagreement is itself a signal — surface it in the brief.

---

## Universal source-priority rules

### Prioritize

- **Primary documents:** SEC filings (10-K, 10-Q, S-1, proxies), earnings call transcripts, official engineering/product blogs, published enterprise case studies, press releases, analyst reports, regulatory filings, court records
- **Code / docs (for technical briefs):** official docs, SDK source code (read it, not just the README), GitHub issues with reactions/comments, merged PRs from maintainers, arXiv/peer-reviewed papers, technical conference recordings
- **Operator voice:** named LinkedIn posts from executives, podcast interviews with named operators, conference talks with published slides, Reddit/HN comments from verifiable practitioners
- **Financial / quantitative:** public company financials, funding announcements (Crunchbase/PitchBook), pricing case studies with actual dollar figures, procurement forum leaks

### De-prioritize

- YouTube reaction videos and "breaking down X" creator content, unless the creator is the primary source (e.g., a founder demoing their own product)
- Twitter / X takes without operator credentials
- Thin listicle blogs ("Top 10 X for 2026")
- "What is X" explainers (tertiary at best)
- AI-generated summary content (often uncited and confidently wrong)
- Medium / Substack posts without code, data, or named affiliation
- Vendor marketing pages (use as positioning data, not as truth claims)
- Speculative threads without primary-source grounding

---

## Universal deliverable quality bar

Every deep-research deliverable must satisfy these:

1. **Survives a counter-brief.** If a well-informed skeptic reads it, they should not be able to cite a primary source you missed, a competitor you underweighted, or a pricing data point you got wrong. Self-test: "Would a sharp operator in this space laugh at this?"
2. **Every numeric claim cited.** Dollar figures, market sizes, growth rates, customer counts, latency numbers — each has a source link or an explicit methodology note ("Estimated from X plus Y; ±30% error bar").
3. **Every positioning claim has a countervailing view noted.** If you say "X dominates Y," note the bear case.
4. **Methodology section.** Explicit list of: providers used · sources available vs. unavailable · substitutions made · date range of evidence · confidence level per section.
5. **No AI-slop prose.** No "In today's rapidly evolving landscape." No "It's important to note." No hollow transitions. Tight, operator-voiced.
6. **Directly actionable.** If the brief is for a decision, the decision-maker should be able to use it without a second meeting. If for a pitch, the seller should be able to cite specific claims in live conversation.

---

## How to use these templates

1. **Pick the archetype** that matches your research goal (or combine two).
2. **Fill in every `{{placeholder}}`.** If a field doesn't apply, delete it — don't leave empty braces.
3. **Fill in the Context block thoroughly.** Err on the side of more context. A 500-word context block is fine and prevents 2000 words of wasted re-derivation.
4. **Decide provider routing** per the table above. For high stakes, run multiple providers and reconcile.
5. **For recurring briefs** (e.g., quarterly competitive refreshes), save the filled prompt to your project's research-prompts folder so the next run is a diff, not a rewrite.
6. **After the deliverable comes back:**
   - Route learnings per the compounding checkpoint ritual in `session-kickoff-prompt.md` Step 5.5
   - Append to your project's `Documentation.md` if project-local
   - Add to your knowledge base if domain-general and reusable
   - Promote to a reusable skill if the research shape recurs 3+ times

---

## When NOT to use these templates

- **Single-source lookups or quick facts** — use plain web search
- **Open-ended "help me understand X"** — have a conversation first; these templates assume you know what questions to ask
- **Internal code / repo / database questions** — use a code-exploration tool or internal-data tool, not a DR provider
- **Real-time news monitoring** — use a news-specific tool with a short lookback; don't request a 6000-word brief
- **Personal-domain expertise questions** — if it's in your own KB / notes, check there first
