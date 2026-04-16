# Deep Research — Technical & Architectural Reference Archetype

> **Purpose:** produce a deep technical reference on a platform, SDK, framework, architecture, or methodology — for build-vs-buy decisions, integration planning, security review, vendor evaluation, or team onboarding.
>
> **Master template:** `deep-research-prompt-master.md`.
>
> **Primary Deep Research provider:** Gemini Deep Research (strongest on technical depth + doc/code ingestion). Secondary: Claude Research. Tertiary: ChatGPT DR. For high-stakes technical briefs, run all three.
>
> **Domain-agnostic:** works for any technical subject — SaaS platforms, APIs, SDKs, frameworks, infrastructure services, hardware, protocols, architectures, engineering methodologies, data pipelines, ML/AI systems, security tools, networking stacks, anything an engineering audience would need to evaluate.

---

## When to use this archetype

- **Build-vs-buy decision** on a platform or tool
- **Integration planning** before adopting a new dependency
- **Security / compliance review** of a vendor or architecture
- **Vendor shortlist evaluation** with a technical rubric
- **Onboarding a team** to an unfamiliar stack
- **Architecture due diligence** (acquisitions, partnerships, investment)
- **Migration planning** from one stack to another
- **Post-incident analysis** of an architectural failure mode

## When to combine with another archetype

- Combine with **Competitive landscape** when the technical evaluation is one input into a broader market-position question
- Combine with **Strategic portfolio** when technical capabilities will drive offering design (e.g., "given what this platform can do, what offerings can we productize?")

---

## THE PROMPT — copy from here

Produce a deep technical reference on **{{PLATFORM / SDK / FRAMEWORK / ARCHITECTURE / METHODOLOGY}}** ({{launch date · version · relevant anchor event}}) covering architecture, {{integration surface: SDK / API / protocol / methodology}}, {{operational concerns: deployment / observability / security}}, and {{decision support: build-vs-buy / migration / adoption}}.

This is for an **engineering audience** making a **{{build-vs-buy · integration · security-review · migration · vendor-selection · methodology-adoption}}** decision.

## Context I already have (don't re-derive)

{{List every technical fact the researcher should treat as given. Include:

- Core architecture abstractions and their relationships (services, layers, components)
- Key performance numbers already known (latency, throughput, TTFT, cost, reduction claims)
- Security / isolation / credential model primitives
- Official repos (with star counts if relevant) and versioning
- Official starter kits, reference implementations, or example apps
- Required headers, auth schemes, version flags, feature flags
- Known limitations already catalogued
- Team context: current stack, integration points that matter, compliance regime, scale envelope
- What's been ruled out from prior evaluations (vendors tried, approaches tested)

Err on the side of more. A thorough context block prevents wasted re-derivation.}}

## What I want you to research and synthesize

### 1. Architecture deep dive

Read the official engineering documentation and any deep-dive engineering blog posts:
- {{list specific blog post titles + authors if known}}
- {{docs URL pattern}} — every doc page relevant to architecture
- Official whitepapers if any exist

Reconstruct the **full request / operation lifecycle**:

- How a user action becomes a platform-level primitive (request / run / session / job / event / transaction)
- Where state/context lives at each stage (stateless vs. stateful, persisted vs. ephemeral)
- How abstractions communicate (sync/async, protocol, timeouts, retries, backpressure)
- How errors propagate — what fails gracefully vs. what aborts
- How failures recover (idempotency model, replay semantics, at-least-once vs. exactly-once guarantees)
- What's observable at each layer (logs, traces, metrics, events, and what they don't surface)
- Multi-tenancy primitives (isolation level, credential scoping, quota management, noisy-neighbor protection)

**Produce architecture lifecycle diagrams** — ASCII or clearly described — showing:
- Request path (happy case)
- Failure path (what happens when something breaks)
- Recovery/retry path

### 2. SDK / API deep dive

Read every official SDK and every official API reference. For SDKs, also read:
- Top **20 open issues** ranked by reactions + comments (developer-reported pain)
- **10 most-recent merged PRs** (what's being actively improved)
- Top 5 discussions on the SDK's discussion forum / Discord / Slack community

For each SDK or primary API:

- **Idiomatic primitive declaration** — how a developer defines the core unit of work
- **Tool / integration registration pattern** — how external things get wired in
- **Streaming / event handling** — how async output reaches the application
- **Auth / permission / consent prompt flows** — how the user-level authorization works
- **Error handling patterns** — what the SDK does on failure, what it surfaces
- **Top 5 developer complaints** — each with a GitHub issue link, a reproduction description, and the current maintainer response status
- **Versioning and migration posture** — how breaking changes are handled; what "stability" means in practice

### 3. Integration patterns

Catalog how **{{PLATFORM}}** integrates with external systems — protocols, APIs, plugins, adapters, connectors:

- **Which integrations are most commonly wired in production?** Find open-source examples on GitHub (search by import / dependency, not just README mention).
- **Auth / credential-handling patterns** — code-level detail. How do credentials flow? Where are they stored? Who has them in scope?
- **Performance cost per integration** — round-trip time, token/call overhead, rate-limit constraints, failure-mode impact
- **Common anti-patterns** — what do new teams typically get wrong, and what's the fix?

### 4. Deployment reference architecture

Build a canonical reference for production deployment:

- **Config variants:** when to deploy single-tenant vs. multi-tenant, dev vs. prod, region-pinned vs. global, high-availability vs. best-effort
- **Multi-tenancy:** isolation primitives, credential scoping, quota management, tenant-level observability
- **Permission / authz routing:** how end-user permissions flow through the platform
- **Observability:** logs, traces, metrics — what's native, what requires external tooling, how to correlate across the stack
- **Versioning / rollout:** how to version configs and roll out safely (canary, staged, dark launch)
- **Migration path:** from a DIY equivalent or a competing platform
- **Compliance posture:** SOC 2 / HIPAA / GDPR / FedRAMP / industry-specific certifications; where the line of responsibility falls

**Surface working examples from public GitHub repos.** Name the repo, link the file, describe what it demonstrates.

### 5. Security model under adversarial conditions

Evaluate the security claims of **{{PLATFORM}}**. How does the architecture hold up against:

- **Injection attacks** — prompt injection (for LLM systems), SQL injection, command injection, XSS, CSRF
- **Isolation escapes** — sandbox escape, container escape, multi-tenant boundary violations, privilege escalation
- **Credential exfiltration** — both via intended output channels and via covert/side-channels (timing, memory, log leakage)
- **Confused-deputy attacks** — getting the platform to do something it has permission for but the caller doesn't
- **Supply-chain attacks** — compromised dependencies, malicious plugins, poisoned configs
- **Insider threats** — platform operator access to tenant data; audit-log tampering resistance

Build a **security threat model table:**

| Attack vector | Platform's defense | Residual risk | Operator mitigation |
|---|---|---|---|
| {{vector}} | {{defense}} | {{what's still exposed}} | {{what the operator must do}} |

Include **confidence level** for each row: "documented + tested externally," "documented only," "inferred from architecture," "unknown."

### 6. Current limitations with workarounds

Known gaps: **{{list user's pre-identified limitations}}**.

For each limitation, surface **community workarounds** with code-level detail:

- Workaround description
- Source link (GitHub issue, Stack Overflow, Reddit, dev.to, Medium, HN)
- Who's using it (if named)
- Gotchas and operational costs
- When / whether an official fix is expected

**Discover additional limitations** the user didn't mention — dig into the issue tracker for "cannot" / "won't" / "hack" / "workaround" language; look for limitation acknowledgments in maintainer responses.

### 7. Build-vs-buy cost model (or migration / adoption cost model as applicable)

What does a DIY equivalent cost in engineering time and infrastructure?

Reference:

- The vendor's own "months of infrastructure work" claim (if made)
- Community estimates from named teams who rolled their own
- Published case studies of teams that chose to build — conference talks, engineering blog posts, HN launch posts, r/ExperiencedDevs build-vs-buy threads

Build a **decision cost table:**

| Dimension | Buy (this platform) | Build (DIY) | Migrate (from {{alternative}}) |
|---|---|---|---|
| Engineer-weeks to MVP | {{#}} | {{#}} | {{#}} |
| Engineer-weeks to production-ready | {{#}} | {{#}} | {{#}} |
| Engineer-weeks to enterprise-ready | {{#}} | {{#}} | {{#}} |
| Ongoing FTE fraction | {{fraction}} | {{fraction}} | {{fraction}} |
| Low-scale infra cost | {{$}} | {{$}} | {{$}} |
| High-scale infra cost | {{$}} | {{$}} | {{$}} |
| Hidden costs | {{list: compliance, on-call, security reviews, etc.}} | {{list}} | {{list}} |
| Time-to-value | {{days/weeks}} | {{months}} | {{varies}} |

Then: **scenarios where buy beats build** and **scenarios where build beats buy** — be specific about which team profile, scale band, compliance regime, and timeline makes each the right answer.

## Deliverable

A **{{5000-8000}}** word technical reference with:

- **Architecture lifecycle diagrams** (ASCII or described — request, failure, recovery paths)
- **Annotated code snippets** for the 5 most common patterns (complete and runnable, not pseudocode)
- **Integration recipe** — one end-to-end walkthrough with a realistic external system
- **Security threat model table** (vector × defense × residual × mitigation × confidence)
- **Limitations + workarounds table**
- **Build-vs-buy decision cost model** with engineer-weeks estimates and scenario guidance
- **Methodology section** — providers used, docs/repos read, issue-snapshot date, source limitations

## Source priority

**Prioritize:** official documentation · official engineering blog posts · SDK source code (actually read it, don't just summarize the README) · GitHub issues with reactions/comments · merged PRs from maintainers · arXiv / peer-reviewed papers on the architectural patterns used · dev.to technical writeups with working code · HN comment threads where practitioners cite code or case studies · conference talks with published slides or recordings.

**De-prioritize:** marketing blogs · "what is X" explainers · AI-generated summary content · Medium posts without code · Twitter/X threads without reproductions · vendor-sponsored "case studies" that read like press releases.

Every architectural claim is traceable to a primary source (blog post + file/line in the SDK, or docs page + specific section). Every performance number cites a specific benchmark, engineering blog post, or user-published benchmark.

---

## Dependencies & Capabilities Callout

### Required minimum

- Web search + web fetch (tool or provider built-in)
- At least one Deep Research provider (Gemini DR strongly preferred for this archetype)
- **File-read tools** if you'll be reading a locally-cloned SDK — this dramatically improves quality vs. README-only analysis

### Strongly recommended

- **Framework-docs-researcher subagent** — dedicated library/framework doc mining
- **Issue-intelligence-analyst subagent** — systematic GitHub issue pattern analysis across repos
- **Code-archaeologist subagent** — if research involves tracing execution paths through a cloned codebase
- **Agentic multi-source research skill** — for the arXiv / Semantic Scholar / Stack Overflow / dev.to / Reddit / HN scan
- **GitHub MCP server** (if configured with your agent) — direct issue/PR queries

### External accounts / APIs

- **GitHub API** — unauthenticated is fine for public repos but rate-limited (60 req/hr). Authenticated = 5000 req/hr. **Fallback:** web-fetch GitHub HTML; slower but no rate limit issue for light queries.
- **Academic:** arXiv · Semantic Scholar · OpenAlex · PubMed — all free, no account needed
- **Community:** Stack Overflow · Reddit · HN — free web search; APIs exist but usually not needed
- **Vendor beta / feature-flag access** — required if the platform needs a beta header or special enrollment. **Fallback:** docs + SDK source; skip live verification.
- **Cloud provider accounts** (if evaluating a hosted platform) — free tiers usually suffice for architecture verification

### Local environment prereqs

- Ability to clone SDK repos and run file search / text search against them
- Ability to read manifest files (`package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, etc.) for dependency graphs
- If research involves running code: language runtime installed for the target language(s)
- If research involves containers / k8s: Docker Desktop or equivalent
- Optionally: a sandbox/scratch account on the target platform for quick "does this actually work?" verification

### Fallback protocol

If GitHub API rate limits hit: switch to web-fetch on public repo HTML pages. If the agentic research skill is unavailable: the SDK README + top 20 issues + 10 merged PRs can be gathered manually via `gh api` calls or web UI — slower but no capability lost.

### Local knowledge prerequisite

If you maintain a personal or team knowledge base on your stack or on adjacent technologies, search it first. Prior technical evaluations may already have the architecture sketched. Cite KB hits in the Methodology section.

### Example filled-in use cases (diverse technical domains)

- **Cloud platform evaluation:** "Produce a technical reference on Cloudflare Workers vs. Vercel Edge Functions as of {{date}} for a team considering moving global serverless workloads."
- **Database migration:** "Produce a technical reference on migrating from MongoDB to PostgreSQL with JSONB columns for a mid-scale SaaS (50M records, 2K RPS) as of {{date}}."
- **SDK evaluation:** "Produce a technical reference on Segment's Unify CDP vs. Rudderstack vs. mParticle for a DTC brand with multi-store Shopify + Klaviyo + Braze as of {{date}}."
- **Agent framework:** "Produce a technical reference on LangGraph vs. CrewAI vs. AutoGen vs. building on raw SDK for a team shipping multi-agent customer-support automation as of {{date}}."
- **Protocol adoption:** "Produce a technical reference on adopting MCP (Model Context Protocol) for a team with existing REST tools as of {{date}}."
- **Payments integration:** "Produce a technical reference on Stripe Checkout vs. custom Elements vs. PaymentIntents API for a subscription SaaS entering EU markets (SCA compliance required) as of {{date}}."
- **Observability stack:** "Produce a technical reference on DataDog vs. New Relic vs. Grafana Cloud vs. open-source (Prometheus + Loki + Tempo) for a Series B SaaS at 100 engineers as of {{date}}."
- **Security tool:** "Produce a technical reference on adopting Semgrep vs. Snyk vs. CodeQL for SAST in a polyglot codebase (TS, Python, Go, Rust) as of {{date}}."
- **Infrastructure pattern:** "Produce a technical reference on adopting event sourcing + CQRS for our order management system, scoped to migration from a CRUD-on-Postgres baseline, as of {{date}}."
