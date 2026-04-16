# AI-Agent Prompt Templates

General-purpose, domain-agnostic, agent-agnostic templates for two recurring needs:

1. **Multi-session project work** — starting and resuming long-horizon AI-agent projects without context loss
2. **Deep research briefs** — 4000-8000 word research deliverables from any Deep Research provider or agentic research skill

All templates are:

- **Domain-agnostic** — work for code, research, ops/strategy, content, marketing ops, workflow automation, consulting, ecommerce, SaaS, internal tooling, anything
- **Agent-agnostic** — work with Claude Code, Cursor, Windsurf, Zed, Copilot, Codex CLI, Aider, Continue, Cline, hosted enterprise agents, and web-UI chat agents
- **Scale-adaptive** — include ceremony-level guidance for small (5-10 session) vs. standard (25-100 session) vs. heavy (100+ session) projects

---

## Placeholder conventions

Templates use two reference placeholders for personal infrastructure:

- **`{{KNOWLEDGE_BASE_ROOT}}`** — substitute your own knowledge base path if you maintain one (e.g., an Obsidian vault at `~/kb/`, a Notion workspace, a local wiki, a company confluence space). If you don't maintain a KB, delete the reference — nothing downstream depends on it.
- **`{{WORK_VAULT_ROOT}}`** — substitute your own work/project notes vault (e.g., an Obsidian folder at `~/Documents/Work/`, a Notion project workspace). Same rule: delete if unused.

References like `{{KNOWLEDGE_BASE_ROOT}}/amazon-ads/wiki/_index.md` are *suggestions* of where prior compiled research might live. If your equivalent is `~/Notion/Marketing/Amazon-PPC`, substitute accordingly. If none exists, the template still works — it just skips that step.

---

## Decision tree — pick the right template

```
Are you starting or resuming a multi-session project?
├─ Starting (session 1, expecting 10+ sessions) → session-kickoff-bootstrap.md
└─ Resuming (session 2 through N)               → session-kickoff-prompt.md

Do you need a research brief (4000-8000 words)?
├─ Not sure which type                          → deep-research-prompt-master.md
├─ Competitive / market positioning             → deep-research-competitive-landscape.md
├─ Technical platform / build-vs-buy            → deep-research-technical-reference.md
└─ Portfolio / offering / GTM design            → deep-research-strategic-portfolio.md

Need just a quick fact or single-source lookup  → plain web search, not these templates
Need an ongoing multi-session research project  → use BOTH kickoff (for the project)
                                                  AND the appropriate DR archetype (for briefs)
```

---

## The six templates

### Multi-session project templates (pair)

| File | Use for |
|---|---|
| `session-kickoff-bootstrap.md` | **Session 1 only.** Interview for a frozen goal, scaffold the four-file durable-state stack (Prompt / Plan / Implement / Documentation), set up task tracker + validators, seed optional persistent memory, produce first handoff. Ends with a hard gate contract. |
| `session-kickoff-prompt.md` | **Session 2 through N.** Declare session scope, read durable state, check prior-session history, verify state on disk, ask blocker questions before picking work, enforce working protocol, run compounding checkpoint ritual at key moments, print hard gate before any writes. |

**How they pair:** bootstrap produces the state that resumption assumes exists. If you're starting fresh, always run bootstrap first. If the four-file stack is missing when you try to resume, the resumption template will tell you to bootstrap.

### Deep research templates (master + three archetypes)

| File | Use for |
|---|---|
| `deep-research-prompt-master.md` | **Archetype selector + shared infrastructure.** Explains the common 4-block skeleton (Context / Questions / Deliverable / Sources), global dependencies, three-provider DR routing, universal quality bar, source-priority rules. Read this first if you're unsure which archetype fits. |
| `deep-research-competitive-landscape.md` | **Market / positioning research.** Map competitors, surface buyer demand signals, identify white-space, forecast 12-month trajectory. Best DR provider: **ChatGPT Deep Research**. |
| `deep-research-technical-reference.md` | **Technical / architectural research.** Reconstruct platform lifecycles, evaluate SDKs, catalog integrations + limitations, security threat model, build-vs-buy cost model. Best DR provider: **Gemini Deep Research**. |
| `deep-research-strategic-portfolio.md` | **Portfolio / offering / GTM design.** Productize N offerings under scope discipline, pick anchor 3, segment/vertical plays, qualification rubric, anti-offerings, 12-month roadmap. Best DR provider: **Claude Research**. |

**Archetype combinations:** real briefs often span two. Start with one and borrow sections from another. The master template has guidance on combinations.

---

## Three-provider DR routing (from master)

| DR Provider | Strongest for | Archetype match |
|---|---|---|
| ChatGPT Deep Research | Strategy synthesis, cross-source reconciliation | Competitive landscape (primary) |
| Gemini Deep Research | Technical depth, code/doc ingestion, large context | Technical reference (primary) |
| Claude Research | Reasoning against user-provided context, nuance | Strategic portfolio (primary) |
| Grok DeepSearch | Real-time + X-native signal capture | News / supplement |
| Perplexity Pro | Fast citation-dense answers | Quick citation seed |

For high-stakes briefs, run the same prompt through all three primary providers and reconcile. Provider disagreement is a signal worth surfacing.

---

## Quick-start

1. **Copy the relevant template** (as markdown or paste from the .docx into your DR provider / agent)
2. **Fill in every `{{placeholder}}`.** Delete sections marked `[optional — delete if N/A]` that don't apply.
3. **Read the adaptation guide** at the top of each template — it tells you what scales up or down with your project size and agent platform.
4. **For recurring work** (e.g., quarterly competitive refreshes, weekly standup handoffs), save the filled template to your project's prompts folder so the next run is a diff, not a rewrite.
5. **Route learnings** back per the compounding-checkpoint ritual in `session-kickoff-prompt.md` Step 5.5.

---

## Available formats

Each template exists as both:

- **Markdown (`.md`)** — for pasting into agents, version-controlling alongside a project, or reading in a markdown viewer
- **Word (`.docx`)** — for sharing with non-technical stakeholders or editing in Word / Pages / Google Docs

Regenerate docx from md with pandoc: `pandoc FILE.md -o FILE.docx --from=gfm --to=docx`.

---

## Version history

| Version | Date | Change |
|---|---|---|
| v1 | 2026-04-14 | Initial release — user-specific (contained hardcoded paths, tools, domain examples). Archived at `archive/v1-user-specific-2026-04-14/` |
| v2 | 2026-04-14 | **Current.** Generalized to be domain-agnostic, agent-agnostic, path-agnostic. Added adaptation guides for agent platform + project type + scale. Added filled-in examples spanning 8-10 diverse use cases per template. Renamed `deep-research-productized-practice.md` → `deep-research-strategic-portfolio.md` and broadened scope. |

---

## When NOT to use these templates

- **Single-session tasks** — a plain prompt is better
- **Quick lookups or fact-check** — use web search directly
- **Open-ended exploration where you don't know the right questions yet** — have a conversation with the agent first, then use a template once the shape is clear
- **Strictly personal / non-work tasks** — these are calibrated for business-use seriousness; they'll feel bureaucratic for journaling, fitness tracking, etc.

---

## Design principles baked into every template

1. **Externalize state** — context windows compact; disk files persist. Structured files beat memory.
2. **Verify before trusting** — disk > memory > handoff-claim. Always verify.
3. **Gate routing on answers, not guesses** — blocker questions before work picks
4. **One-task-per-session** — topic mixing costs ~40% on agent performance
5. **Fail fast on drift** — hard gates with Y/N output contracts, not advisory prose
6. **Compound learning at checkpoints** — not only at session end
7. **Survive a counter-brief** — every claim cited, every positioning claim has a countervailing view
8. **Graceful degradation** — every capability has a documented fallback

These principles travel across all six templates — they're what makes the set coherent.
