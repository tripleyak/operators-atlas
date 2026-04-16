# Session Kickoff — Bootstrap (Session 1 of a Long-Horizon Project)

> **Purpose:** establish durable external state so every future session of a multi-session AI-agent project resumes without context loss.
>
> **Use when:** session 1 of a project you expect will span 10+ working sessions with any AI coding, research, ops, content, or strategy agent — across any domain (software, ecommerce, growth marketing, marketing ops, workflow automation, research, content, consulting, internal tooling, etc.).
>
> **Produces:** four external-state files (Prompt / Plan / Implement / Documentation), a first handoff artifact, optional persistent-memory seeds, optional knowledge-base anchoring, and a declared working protocol.
>
> **Sibling:** `session-kickoff-prompt.md` — use from session 2 onward. This bootstrap ends by producing the state that resumption assumes.

---

## When to use this template

All three must be true:

1. You expect **10+ working sessions** with an AI agent on this project
2. The **goal is stable** enough to write down once and not rewrite every session
3. Some of the work state **lives outside the agent's context window** — in a repo, database, document set, external service, file system, etc.

**Skip if:**
- Task is one-shot or <5 sessions → use a plain prompt
- Goal is still being shaped → do a few exploration sessions first, *then* bootstrap
- There's no external state and no cross-session continuity needed

---

## Why this template exists (the problem it solves)

Long-horizon AI-agent work fails in one predictable way: **the context window becomes a landfill.** Each session starts fresh, the agent re-derives what past sessions already decided, and hallucinated "prior decisions" pile up. By session 30 the project has drifted.

The fix is to **externalize state into stationary files the agent reads + appends to every session**, not into a context window that compacts every few hours. The four-file stack below is the minimum viable implementation of that pattern.

---

## Adaptation guide (read before using)

### Agent platform

This template works with any AI agent that can read files, write files, and optionally run shell commands. Specifics:

| Agent | Notes |
|---|---|
| Claude Code (CLI or IDE) | Full feature set: persistent project memory, hooks, skills, slash commands, subagents. Steps 5-6 work natively. |
| Cursor / Windsurf / Zed AI / Copilot | No native persistent memory — four-file stack is *more* critical. Skip Step 5. |
| Codex CLI / Aider / Continue / Cline | File-system-driven; treat the four-file stack as authoritative. |
| OpenAI Operator / Anthropic Managed Agents / enterprise hosted agents | Platform-specific persistence varies; the four-file pattern works if the agent can read markdown files in the project. |
| ChatGPT / Claude.ai / Gemini web UI | No native file system — you manually ferry content between agent and local files, or paste files at session start. |

### Project type

| Project type | Scaffolding addition |
|---|---|
| Code project | Git repo + task tracker + test suite + CI |
| Research / knowledge project | Raw-source folder + citation conventions + synthesis artifacts |
| Ops / strategy / consulting project | Stakeholder map + decision log with owner per decision + review cadence |
| Content / editorial project | Editorial calendar + style guide + voice reference + publishing pipeline |
| Marketing operations / automation | Tool inventory + integration map + KPI/metric contract + runbook per automation |
| Hybrid (most real projects) | Combine relevant items, designate one as the "primary axis" |

### Scale

| Sessions expected | Ceremony level | Skip these steps |
|---|---|---|
| 10-25 | Light | Steps 5, 6 optional; mental-model doc optional |
| 25-100 | Standard | Full template |
| 100+ | Heavy | Full template + add review cadence + stakeholder reporting rhythm |

---

## THE TEMPLATE — copy from here

You are starting a new long-horizon project: **{{PROJECT_NAME}}**. This session's only job is to establish durable state so every future session can resume without context loss. **Do not start implementation work today** unless the user explicitly says so after bootstrap is complete.

### Step 0 — Project identity interview (ask, do not guess)

Interview the user with these questions. Do not proceed until all are answered. Answers go into `Prompt.md` verbatim — they become the *frozen goal*.

1. **One-sentence goal.** "This project exists to {{verb}} {{outcome}}." No qualifiers, no hedging. If the user can't compress it, keep interviewing.
2. **Definition of done.** What *observable state* proves the project is complete? (e.g., "Dashboard renders X metric live," "50 customers onboarded," "p95 checkout latency <300ms," "Pipeline processes 10K leads/day," "Content calendar fills for 90 days.") Not "when it's good."
3. **Non-goals.** What is this project explicitly NOT? At least 2. (e.g., "Not a rewrite of auth," "Not a multi-tenant system," "Not a brand-new channel strategy," "Not a full agency rebrand.")
4. **Time horizon.** Realistic finish date. If "I don't know," ask for 50% / 90% confidence dates separately.
5. **Constraints that won't change.** Stack choices, vendor commitments, budget ceiling, compliance requirements, team availability, regulatory deadlines.
6. **Stakeholders.** Who cares if this succeeds, and what does each need to see? (e.g., "CFO needs quarterly budget adherence," "Head of Growth needs weekly CAC trend," "Board needs Q4 revenue number.")
7. **Prior art.** Has the user tried this before? Dead repos, abandoned plans, past agent sessions, failed vendor pilots? Surface so we don't repeat.
8. **External systems touched.** Every repo, database, SaaS tool, API, spreadsheet, document store, messaging system, or service this project will read from or write to. Each gets a blast-radius classification in Step 3.

> **Why:** a vague goal at session 1 guarantees drift by session 20. Push back on vague answers. "Make the app better" is not a goal. "Reduce p95 checkout latency to <300ms" is. "Improve growth marketing" is not. "Lift blended MER from 2.1 to 2.8 by Q4" is.

### Step 1 — Choose the project path and scaffolding

Ask the user:

- **Where does this project live?** (Absolute path on disk — typically a folder under a projects directory, or an existing repo.)
- **Project type?** Code / research / ops-strategy / content / marketing-ops / hybrid. Answer selects scaffolding below.
- **Task tracker?** Pick one and commit:
  - Issue database (GitHub Issues, Linear, Jira, Beads, Height)
  - Kanban (Notion, Trello, GitHub Projects, Linear)
  - Plain markdown checklists in `Plan.md` (fine for small teams, non-code projects)
- **Version control?** Git repo if the project produces artifacts that benefit from diff-able history. Initialize now. Default visibility: private unless the project is open-source by design.
- **Remote storage?** Where do handoffs, logs, and generated artifacts live? (Local only / synced via Dropbox/iCloud/Drive / remote repo / shared S3 bucket.)

### Step 2 — Create the four-file durable-state stack

Create these four files at the project root. Use the stubs below. Commit them as the project's first commit (`chore: bootstrap durable-state stack`).

> **Why four files?** Separation of concerns by *write pattern*:
> - **Prompt.md** — frozen; answers *what* and *why we're doing this*
> - **Plan.md** — edited in place; answers *when and in what order*
> - **Implement.md** — evolves as we learn; answers *how we operate*
> - **Documentation.md** — append-only; answers *what decisions we made and why*
>
> Together they replace the agent's volatile context window as the project's memory. The agent reads them every session and appends to them.

#### `Prompt.md` — frozen goal (NEVER edit after first commit)

```markdown
# {{PROJECT_NAME}} — Prompt

**Created:** {{YYYY-MM-DD}}
**Status:** FROZEN — create an ADR (Architecture / Adjustment Decision Record) if the goal changes; do not edit this file.

## Goal
{{one-sentence goal from Step 0.1}}

## Definition of Done
{{from Step 0.2 — observable, measurable state}}

## Non-Goals
- {{from Step 0.3, item 1}}
- {{from Step 0.3, item 2}}
- {{more if needed}}

## Horizon
- 50% confidence finish date: {{date}}
- 90% confidence finish date: {{date}}

## Constraints
- {{stack / vendor / budget / compliance / team / regulatory constraints}}

## Stakeholders
- {{name or role}}: needs {{what they need to see and when}}

## Prior Art
- {{dead repo / abandoned plan / past failed attempt — or "None" if greenfield}}

## External Systems (blast-radius classified)
- {{system name}}: class={{read-only | shared-substrate | write-owned}}; consumers={{who else reads/writes this}}
```

> **Blast radius classes:** `read-only` (we consume but never write), `shared-substrate` (we write but other systems/teams also write — risky), `write-owned` (we alone write; safe to mutate freely).

#### `Plan.md` — milestones + validation (update status inline; do not rewrite)

```markdown
# {{PROJECT_NAME}} — Plan

**Last updated:** {{YYYY-MM-DD}}

## Milestones

### M1 — {{milestone name}}
- **Status:** `[ ]` not started · `[~]` in progress · `[x]` done · `[!]` blocked
- **Deliverable:** {{concrete artifact — not "improve X", but "ship Y"}}
- **Validation command:** `{{exact command or check that proves it's done}}` (e.g., `curl $URL/health | jq .status == "ok"`, `npm test -- --testPathPattern=M1`, `psql -c "SELECT COUNT(*) FROM orders WHERE status='complete'"`, "screenshot review by stakeholder")
- **Dependencies:** {{none | M0 | external event | stakeholder approval}}
- **Target date:** {{date}}

### M2 — {{milestone name}}
(same structure)

### M3 — …

## Current Focus
{{which milestone is active right now — 1 sentence}}

## Risk Register
- **{{risk}}** — likelihood: {{L/M/H}}, impact: {{L/M/H}}, mitigation: {{plan}}
```

#### `Implement.md` — active runbook (what the agent follows during execution)

```markdown
# {{PROJECT_NAME}} — Implementation Runbook

**Last updated:** {{YYYY-MM-DD}}

## Session-start protocol
1. Read `Documentation.md` tail (last 10-20 entries) for recent decisions.
2. Check task tracker current state: `{{tracker status command}}`.
3. Verify state on disk matches expectations (see state-verification rules below).
4. Pick the next unblocked item in the current milestone.

## Session-execution loop
Implement → validate → commit (or artifact-save) → update `Plan.md` status inline → append decisions/outcomes to `Documentation.md`.

## Session-close ritual
- {{tracker push/sync command}} && {{repo push or artifact upload}}
- Update `SESSION_HANDOFF.md` with this session's summary
- Append significant decisions to `Documentation.md`

## Non-negotiable rules (project-specific)
- {{rule 1 — e.g., "all writes to $SHARED_DB run pre-flight classify check"}}
- {{rule 2 — e.g., "tests must stay green: $VALIDATION_COMMAND}}"
- {{rule 3 — tool/CLI quirks discovered}}

## Critical mental model
{{2-3 sentences naming the ONE load-bearing concept that reframes how everything else is read. If none exists yet, write: "TBD — capture as ADR before M1 completes." Examples:
- Code project: "Service A is source-of-truth; Service B is a read-replica; all writes go through A or they desync silently."
- Ecommerce: "Shopify is storefront-of-record; our ERP is financial-of-record; reconciliation lag is 24h, so don't compute margin from Shopify alone."
- Marketing ops: "HubSpot is lead-of-record; Salesforce is opportunity-of-record; contacts created in SF without HS sync get stranded."
- Content: "Editor approves; legal reviews; only then publish. Out-of-order causes republishing which breaks analytics attribution."}}

## State verification rules
- Disk > memory > handoff claim. If handoff says "X shipped," verify on disk before trusting.
- Source-of-truth files (e.g., settings, schemas, manifests) win over derived registries or summaries.
- Don't run slow full-build or full-test-suite checks at kickoff — trust the handoff snapshot unless you're about to modify the relevant code.

## Model / provider preferences
- Default model: {{model name and tier}}
- Long-context override: {{when to opt into 1M context tier or equivalent}}
- Provider routing (if multi-provider workflow): {{when to use which provider}}
```

#### `Documentation.md` — append-only audit log

```markdown
# {{PROJECT_NAME}} — Decision Log

Append-only. Never delete entries. Use ISO dates. Each entry: decision, rationale, alternatives rejected, who decided.

## {{YYYY-MM-DD}} — Project bootstrapped
- Created `Prompt.md` (frozen), `Plan.md`, `Implement.md`, `Documentation.md`.
- Task tracker: {{choice}} — chosen because {{reason}}.
- Project path: {{path}}.
- Initial milestone count: {{N}}.
- Stakeholders notified: {{list}}.
```

### Step 3 — Critical mental model document (if load-bearing)

If the project has a **non-obvious architectural, operational, or strategic concept** that every future session must absorb before acting, write it now as `docs/adr/0001-{{mental-model-slug}}.md` (or the equivalent in your project structure). Keep it under 1 page. Reference it from `Implement.md` "Critical mental model" section.

> **Examples of load-bearing mental models:**
> - Software: "System X uses eventual consistency between regions; reads can be 2-10s stale; UI must handle."
> - Ecommerce: "Our Amazon and Shopify listings share SKUs but not inventory; overselling during sales is the #1 reliability issue."
> - Growth marketing: "Attribution is last-click Facebook, 7-day view / 1-day click — do not compare against our GA4 UTM model, which is MMM-weighted."
> - B2B SaaS: "Our free tier is capped by seat count, not usage; most churn comes from usage-driven companies who hit seat limits, not usage limits."
> - Agency ops: "Clients pay monthly retainer + performance bonus; bonus triggers on monthly MER, not LTV — so short-term spend efficiency wins vs. growth optimization."

If no such concept exists yet, skip this step and add a reminder in `Plan.md` M1 to capture one before M1 completes.

### Step 4 — Set up task tracker and validators

- **Task tracker:** initialize per the choice in Step 1. Seed with the first 3-5 items from `Plan.md` M1 deliverables.
- **Validators:** if the project has automated checks that must stay green (tests, linters, schema validators, content-style checkers, SQL query validators), document the *exact commands* and *expected counts/output* in `Implement.md`. Future sessions will run these at kickoff to verify state.
- **CI (if code project):** scaffold a minimal workflow that runs validators on every commit. Don't skip — CI catches regressions far cheaper than re-discovering them mid-session.
- **Review cadence (if ops/content/strategy project):** schedule the first checkpoint review date — weekly, biweekly, or at each milestone.

### Step 5 — Persistent memory seeds [optional — skip if your agent lacks persistent memory]

If your agent has persistent cross-session memory (Claude Code, some enterprise agents), create seed memory files that future sessions will auto-load:

- `{{project-slug}}-architecture.md` (type: project) — 1-paragraph architecture/model summary + blast-radius notes for external systems. Future sessions read this BEFORE touching code.
- `{{project-slug}}-quirks.md` (type: feedback) — seeded empty; grows as you discover tool/test/process quirks.
- `{{project-slug}}-design-principles.md` (type: feedback) — if the project has UX / API / editorial / operational design principles, encode them here.

Add pointers to the agent's memory index file (MEMORY.md, AGENTS.md, or equivalent) under a new `## {{Project Name}}` section. Keep each line under ~150 characters.

> **Why:** persistent memory keeps project-local rules out of the main system prompt (smaller surface) while auto-loading them when this project is active. If your agent doesn't support this, the four-file stack fully substitutes.

### Step 6 — External knowledge anchoring [optional — skip if you don't maintain a KB or work vault]

If you maintain a personal or team knowledge base (Obsidian vault, Notion workspace, wiki, etc.):

- Add a raw-source entry with the `Prompt.md` contents: `{{kb-root}}/raw/{{project-slug}}-bootstrap.md`
- If your KB has compilation conventions, compile a wiki article per those conventions.
- Link from the relevant index page.

If you maintain a work/project vault distinct from KB:

- Create a project folder with a pointer to the repo/project path and the `Prompt.md` contents.

> **Why:** future sessions that search the KB before using web search will find this project and skip re-researching what you already know. If you don't have a KB, skip this step — nothing depends on it downstream.

### Step 7 — Write the first `SESSION_HANDOFF.md`

Drop this at the project root. If your agent's tooling supports auto-injecting a handoff file at session start, point the hook at this file.

```markdown
# Session Handoff — {{PROJECT_NAME}}

**Last Updated:** {{YYYY-MM-DD HH:MM}}
**Session Duration:** Bootstrap (session 1)

---

## Git / artifact state
- Branch: `{{default branch}}`
- Uncommitted Files: None (clean after bootstrap commit)

## Recent Commits / Artifacts
- `{{sha or artifact ID}}` chore: bootstrap durable-state stack

## Session Summary
### Work Completed
- Interviewed user for frozen goal; wrote `Prompt.md`
- Scaffolded `Plan.md` with {{N}} milestones
- Created `Implement.md` runbook and `Documentation.md` log
- {{"Seeded persistent memory" | "Deferred — agent lacks persistence"}}
- {{"Wrote ADR 0001" | "Deferred mental-model ADR until M1"}}
- {{"Anchored to KB" | "Deferred — no KB maintained for this project"}}

### Key Implementation Decisions
- Task tracker: {{choice}} — chosen because {{reason}}
- Project path: {{path}} — chosen because {{reason}}
- {{other bootstrap decisions}}

### Outputs
- `Prompt.md` · `Plan.md` · `Implement.md` · `Documentation.md`
- {{repo URL if pushed}}
- {{memory seed paths if seeded}}
- {{KB entry path if anchored}}

### In Progress
- Nothing — bootstrap session with no implementation work.

### Blockers/Issues
- {{anything the user must resolve before session 2 can be productive — or "None"}}

## Next Session Priorities
1. {{first concrete task from M1}}
2. {{second task}}
3. {{third task}}

---
*First session. From session 2 onward, this file is auto-updated at session close.*
```

### Step 8 — Declare the working protocol and scope guardrails

Write these into `Implement.md` now so session 2 inherits them. Adapt wording to your agent platform where needed.

**Universal working rules:**

- **Level-of-effort routing:** 1-2 files → execute directly · 3-4 → create task list first · 5+ → plan first via formal planning step
- **Disk > memory > handoff** — verify state against disk before trusting any remembered or handed-off claim
- **Source-of-truth files win** over derived registries, summaries, or agent memory for config/schema/state questions
- **One-task-per-chat** — clear context on topic switch; mixing topics degrades agent performance ~40%
- **Checkpoint before context compaction** when mid-plan or mid-long-running task; auto-compaction during flight kills state
- **Grep local knowledge before web search** on any topic you've researched before — the prior work is in your KB / vault / notes
- **Destructive ops always ask** — deleting files / tables / branches / integrations requires explicit user confirmation every time
- **Rewrite >50% of a file means full rewrite; modify <20% means in-place edit; avoid the middle zone** (it produces confusing diffs)
- **Don't delegate verbatim content porting to subagents** — they regenerate content from the prompt rather than copying verbatim; do ports directly with read + write
- **New skills / plugins require session restart** to load — if you create one mid-session, tell the user to restart before relying on it
- **Before bulk `git add -A`** — scan for nested `.git/` directories inside the tree; bulk-add with nested repos corrupts state
- **Never bypass hooks or checks** (`--no-verify`, `--force`, etc.) — fix the underlying issue or explicitly relax the check
- **Dead-output code → delete, not refactor** — if a function's output is never consumed, remove it rather than "cleaning it up"

**Project-specific rules:** {{list any captured in the interview — test commands, validation requirements, review gates, etc.}}

### Step 9 — Hand off to the resumption template

Tell the user (literal text, not paraphrased):

> **Bootstrap complete.** From session 2 onward, use `session-kickoff-prompt.md` filled in with these values:
>
> - PROJECT_NAME: {{name}}
> - PROJECT_PATH: {{absolute path}}
> - DEFAULT_BRANCH (if applicable): {{branch}}
> - HANDOFF_DOC: `SESSION_HANDOFF.md`
> - CRITICAL_MENTAL_MODEL_DOC: {{ADR path | "TBD — scheduled for M1"}}
> - ACTIVE_PLAN_DOC: `Plan.md`
> - PROJECT_MEMORY_SEEDS: {{slugs from Step 5 — or "none, agent lacks persistence"}}
> - TASK_TRACKER: {{choice and status command}}
> - VALIDATOR_COMMANDS: {{list}}
>
> The four-file stack (`Prompt.md`, `Plan.md`, `Implement.md`, `Documentation.md`) is now the project's memory. Every future session reads from and appends to it. The context window is scratch space, not state.

### Step 10 — Hard gate before ending bootstrap

Before declaring this session complete, print exactly:

```
PROMPT_FROZEN: [Y/N]
PLAN_HAS_VALIDATION_COMMANDS: [Y/N — each milestone has one]
IMPLEMENT_HAS_MENTAL_MODEL: [Y/N — or explicitly deferred with reason]
DOCUMENTATION_SEEDED: [Y/N]
TASK_TRACKER_INITIALIZED: [Y/N]
MEMORY_SEEDED: [Y/N — or "agent lacks persistence, N/A"]
KB_ANCHORED: [Y/N — or "no KB maintained, N/A"]
HANDOFF_WRITTEN: [Y/N]
FIRST_COMMIT_MADE: [Y/N — or "no VCS, artifact saved at {{path}}"]
```

If any field is **N** (and not explicitly N/A), fix it before ending the session. A bootstrap that ships with gaps poisons every future resume.

---

## Appendix A — Why each step exists

| Step | Failure mode it prevents |
|---|---|
| 0 — Identity interview | Goal drift across sessions; agent re-derives intent instead of executing |
| 1 — Path + scaffolding | Cross-session "where does X live?" confusion; forgotten tool choices |
| 2 — Four-file stack | "AI Alzheimer's" — context window compaction losing project state |
| 3 — Mental model doc | Agent re-learns load-bearing concept every session; wastes tokens + introduces errors |
| 4 — Tracker + validators | "Is it done?" ambiguity; silent regressions between sessions |
| 5 — Memory seeds | Project-local rules spill into main system prompt or get forgotten |
| 6 — KB anchoring | Redoing research the user already did (expensive agent time) |
| 7 — First handoff | Session 2 starts from scratch with no orientation |
| 8 — Working protocol | Rediscovering the same rules every session |
| 9 — Resumption handoff | Session 2 doesn't know how to resume |
| 10 — Hard gate | Bootstrap "looks done" but has silent gaps |

## Appendix B — Minimum-viable bootstrap (for 5-10 session projects)

If the project is small but still multi-session, you can skip:

- Step 3 (mental model doc) — capture in `Implement.md` section only
- Step 5 (persistent memory) — four-file stack is enough
- Step 6 (KB anchoring) — add later if project grows
- Step 8 universal working rules — rely on agent's default behavior

Keep:
- All of Step 0 (interview)
- All of Step 2 (four-file stack) — even if lightweight
- Step 7 (first handoff)
- Step 10 (hard gate)

## Appendix C — Filled-in examples (three diverse project types)

### Example 1: Code project (SaaS product feature)
- PROJECT_NAME: "Checkout latency reduction"
- Goal: "Reduce p95 checkout API latency from 1200ms to <300ms"
- Definition of done: "p95 /checkout ≤300ms for 7 consecutive days in prod, observed in DataDog"
- Non-goals: "Not a checkout UI redesign · Not a payment-provider swap"
- External systems: "Postgres (shared-substrate), Stripe API (read-only), Redis cache (write-owned)"
- Task tracker: GitHub Issues
- Critical mental model: "Checkout is a saga across 3 microservices; latency is dominated by the idempotency-check round-trip to Postgres"

### Example 2: Marketing operations project (attribution overhaul)
- PROJECT_NAME: "MTA → MMM migration"
- Goal: "Replace last-click MTA with MMM-weighted attribution for channel spend decisions"
- Definition of done: "CMO makes Q3 budget with MMM outputs; MTA deprecated from all dashboards; reconciliation shows <15% weekly delta vs. revenue"
- Non-goals: "Not replacing GA4 tracking · Not changing pixel infrastructure"
- External systems: "GA4 (read-only), Northbeam (read-only), Looker (write-owned), Excel workbook used by CFO (shared-substrate — she edits)"
- Task tracker: Linear
- Critical mental model: "MMM outputs are weekly; MTA is real-time; dashboards must carry both for 90 days before MTA removal — otherwise operators panic"

### Example 3: Research / content project (market-intel brief)
- PROJECT_NAME: "Hosted agent platforms competitive intelligence"
- Goal: "Deliver a quarterly competitive-intelligence brief on hosted AI agent platforms, updated against a fixed scorecard"
- Definition of done: "Q1 brief published + template for quarterly refresh documented"
- Non-goals: "Not building an evaluation tool · Not a buyer's guide for end users"
- External systems: "Google Drive (write-owned), CRM (read-only for customer quotes), internal KB (write-owned)"
- Task tracker: Markdown checklist in `Plan.md`
- Critical mental model: "Every claim in the brief must have a primary source cited; marketing-blog citations discredit the whole brief"
