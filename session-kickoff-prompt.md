# Session Kickoff — Resuming a Long-Horizon Project

> **Purpose:** resume a multi-session AI-agent project without context loss, drift, or re-deriving what prior sessions already decided.
>
> **Use when:** session 2 through session N (where N can be 100+) of any multi-session AI-agent project — code, research, ops, content, strategy, marketing operations, workflow automation, consulting, internal tooling, anything.
>
> **Requires:** the four-file durable-state stack from `session-kickoff-bootstrap.md` already exists at the project root. If it doesn't, run the bootstrap template first.

---

## Why this template exists

Long-horizon AI-agent work has one recurring failure mode: **each new session rediscovers what prior sessions already figured out.** The agent hallucinates "prior decisions," reinvents abandoned approaches, misses carryover caveats, and drifts from the frozen goal.

The fix is a structured resumption that:

1. **Verifies state on disk** before trusting memory or handoff claims
2. **Reads durable files first**, not context-window fragments
3. **Gates routing decisions behind blocker questions** instead of guessing priority
4. **Declares session scope explicitly** to prevent topic-mixing (which costs ~40% on performance)
5. **Produces an output contract** before any code/artifact writes

This template codifies that structure into one fillable prompt.

---

## Adaptation guide

### Agent platform

| Agent | Notes |
|---|---|
| Claude Code / Cursor / Windsurf / Zed / Copilot / Aider / Codex CLI / Continue / Cline | Full template applies |
| Hosted enterprise agents (Managed Agents, Operator, Devin) | Skip Step 2.5 compaction rules if the platform handles context differently; keep everything else |
| Web-UI agents (ChatGPT, Claude.ai, Gemini) | Paste the four files at session start; skip verification commands that require shell access |

### Project type

Applies to any long-horizon project — software, ecommerce ops, growth marketing, marketing operations, workflow automation, content, research, consulting, internal tooling. The template is domain-agnostic; fill placeholders with your project's specifics.

### Scale

| Sessions elapsed | Ceremony level |
|---|---|
| 2-10 | Light — steps 0, 1, 3, 6 essential; others optional |
| 10-50 | Standard — full template |
| 50+ | Heavy — full template + extra rigor on step 0.5 (prior-session lookup) since the history is long |

---

## THE TEMPLATE — copy from here

You are resuming the **{{PROJECT_NAME}}** project (`{{PROJECT_PATH}}`{{, `{{DEFAULT_BRANCH}}` branch if VCS}}). The previous session ended **{{DATE}}** {{at commit `{{COMMIT_SHA}}` | at artifact version `{{VERSION}}`}} with **{{CLEAN | DIRTY | UNKNOWN}}** state.

**Session scope declaration:** this session is scoped to **{{NARROW_TASK_OR_CLUSTER}}**. If I drift into unrelated topics ({{LIST_LIKELY_DRIFT_TARGETS}}), stop me and tell me to clear context and start a fresh session. Topic-mixing costs ~40% on agent performance — one-task-per-chat.

### Step 0 — Durable-state stack (READ + APPEND, don't just read)

These four files ARE the project memory. Your job is to keep them current, not just consume them. If any are missing, stop and flag before proceeding.

1. `{{PROJECT_PATH}}/Prompt.md` — frozen goal. Never edited after first commit. Re-read every resume to re-anchor intent.
2. `{{PROJECT_PATH}}/Plan.md` — milestones + validation command per milestone. Update status inline; never rewrite.
3. `{{PROJECT_PATH}}/Implement.md` — current runbook / active protocol. This is what you follow during execution.
4. `{{PROJECT_PATH}}/Documentation.md` — append-only audit log of decisions, tradeoffs, and outcomes. Every non-trivial decision gets an entry before the session ends.

### Step 0.5 — Prior-session lookup

Before proposing any non-trivial approach, check if a past session already tried and abandoned it. Sources (use what's available):

- Agent session history search (if your agent provides it — e.g., Claude Code session history, Cursor chat log export)
- `git log --all --oneline | head -50` — scan branch names and commit messages for prior attempts
- `{{PROJECT_PATH}}/Documentation.md` — the append-only log is the first place past rejections are recorded
- Task tracker closed/wontfix items — filtered by the current topic

**If a past attempt exists: read *why* it was abandoned before proposing the same path.** The user's time is worth more than your novelty.

### Step 1 — Read these IN ORDER, do not skip

1. `{{HANDOFF_DOC}}` (typically `SESSION_HANDOFF.md` — auto-injected at session start if your agent supports it) — {{git/artifact state, recent commits, open issues, test snapshot}}.
2. `{{CRITICAL_MENTAL_MODEL_DOC}}` — **CRITICAL mental model.** {{2-3 sentence inline summary of the load-bearing concept}}. Reframes how every other doc is read.
3. `{{ACTIVE_PLAN_OR_DECOMP_DOC}}` — {{mandatory section — e.g., "M3 pre-flight checklist," "Current sprint backlog"}}.
4. `{{ROADMAP_OR_INDEX_DOC}}` — current priority tiers and counts, reflecting {{any recent pause/block}}.
5. [optional] `{{NARRATIVE_DOC}}` — full session narrative if the handoff is thin.

[Optional — skip if your agent lacks persistent memory or if project has no memory seeds]

**Load-bearing persistent-memory seeds for this project** (auto-loaded by agent — follow links rather than re-dumping content):

- `{{PROJECT_MEMORY_SEED_1}}`
- `{{PROJECT_MEMORY_SEED_2}}`
- `{{PROJECT_MEMORY_SEED_3}}`

**Memory freshness rule:** any persistent-memory entry >30 days old that claims facts about *active* code / config / process must be re-verified against disk (read / grep / log) before you cite or act on it.

### Step 2 — Verify state on disk (not in memory, not in registries)

Run these and confirm outputs match expectations:

```
cd {{PROJECT_PATH}}
{{VCS_STATUS_CMD}}          # e.g., git status — expect: clean, up-to-date with remote
{{TASK_TRACKER_STATUS_CMD}} # e.g., gh issue list --state open --limit 5 — expect: {{N}} open
{{VALIDATOR_CMD}}           # e.g., npm test, pytest, schema validator — expect: {{counts}}
```

**Source-of-truth rules:**

- **Disk > memory > handoff.** If the handoff says "X is done," verify on disk. If memory says "Y uses pattern Z," grep for Z. Do not trust claims without verification.
- **Configuration files are truth for config questions** — never derived registries, auto-generated summaries, or cached inventories (these drift silently and are a common source of wrong assumptions).
- **Skip slow checks at kickoff.** Do NOT run {{full test suite / full build / full e2e run}} now — trust the handoff snapshot ({{last known counts}}) unless you later touch the relevant code.

**If state has drifted** (unexpected branch, divergent counts, uncommitted work from another session or collaborator, stale lockfile, schema mismatch), STOP and report the deltas before proceeding. Do not auto-resolve.

### Step 2.5 — Context hygiene + compaction policy

- **Context-budget awareness:** 0-30% used = healthy · 30-70% = normal · 70-85% = critical (wrap up or checkpoint) · 85%+ = auto-compaction fires and state is lossy. Watch the indicator; don't launch a subagent or long subtask with the window already at 70%+.
- **Checkpoint before context compaction** when mid-plan, mid-subagent, or mid-multi-step task. Auto-compaction during flight kills in-flight state.
- **Clear context on task switch.** One task per chat. Don't say "while I'm here, also fix Y" — that's how one-task sessions become ten-task messes.
- **Model tier choice:** this session {{does | does not}} require an extended-context model variant. Default model is fine; opt into extended context only when truly needed (tighter rate limits, higher cost).

### Step 3 — Blocker questions (these change routing, not just tactics)

ASK before assuming any priority. Do not guess. If the user is async/offline, note the default assumption you'll proceed with and flag for confirmation at next interaction.

1. **{{BLOCKER_Q_1}}?** — {{what it unlocks · what default applies if unanswered}}.
2. **{{BLOCKER_Q_2}}?** — {{what it unlocks · dependencies · why it matters}}.
3. **Anything new since {{DATE}}?** — live incidents, stakeholder requests, regulatory changes, or new priorities that override the ranked list below?

### Step 4 — Ranked conditional work

After the answers above, pick from this list — don't multi-task.

- **A. If {{BLOCKER_1}} answered** → {{task A}} (~{{time}}). {{what this unblocks downstream}}.
- **B. If {{BLOCKER_1}} AND {{BLOCKER_2}} both answered** → {{task B}}. {{why this is the gateway to the next milestone}}.
- **C. {{INDEPENDENT_TASK}}** — cleared by {{prior checkpoint/audit}}. Independent of blockers. ~{{time}}.
  - **Carryover caveats (do NOT re-litigate):** {{previously-decided acceptable tradeoffs — naming collisions, dual models, legacy code coexistence, approved tech debt, etc.}}
  - **Reuse:** {{shipped component / prior pattern}} — do NOT write parallel logic.
- **D. {{LOWER_PRIORITY_TASK}}** — ~{{time}}. {{any prerequisite or coordination}}.
- **E. {{INVESTIGATION_ITEM}}** — P{{N}}, scope unknown until investigated.
- **F. {{REMAINING_BACKLOG}}** — run the pre-flight check on EACH before starting. {{prior incident if any}} was the cautionary tale.

### Step 5 — Working protocol (non-negotiable)

**Project-specific** (from `Implement.md`):

- **{{TASK_TRACKER}} is the only place work items live** — never inline markdown TODOs, never scratch lists in chat
- **{{TOOL_QUIRK_1}}** — {{e.g., framework-specific API that diverges from defaults, test harness quirk, deployment constraint}}
- **{{TEST_QUIRK_1}}** — {{mocking pattern, test ordering requirement, environment dependency}}
- **After editing {{artifact class}}:** run `{{sync or validate command}}` — must stay green ({{expected counts/output}})
- **After adding {{artifact type}}:** update `{{registry or manifest path}}` or `{{downstream test}}` will break
- **{{CLI_QUIRK_1}}** — {{flag ordering, argument format, dependency resolution quirk}}
- **{{RUNTIME_QUIRK_1}}** — {{environment setup, auth flag, build mode, production-vs-dev difference}}
- **{{DOMAIN_PREFLIGHT}}** — classify any {{shared external system / production data store / integration endpoint}} the change writes to BEFORE writing code
- **Session close:** `{{commit/push/sync sequence}}` (mandatory)

**Universal** (applies to every session, every project):

- **Level-of-effort routing:** 1-2 files → execute · 3-4 → task-list first · 5+ → plan first
- **Check local knowledge before web search** on any topic you've researched before
- **Destructive operations ALWAYS ask** — deleting files / tables / branches / integrations / data requires explicit user confirmation every time
- **Rewrite >50% or modify <20%** — avoid the middle zone (confusing diffs, partial refactors)
- **Don't delegate verbatim content porting to subagents** — they regenerate from prompt rather than copying; do ports yourself
- **New skills / plugins require session restart** before they're loaded — don't assume mid-session creation worked
- **Before bulk git add -A** — scan for nested `.git/` directories in the tree; bulk-add with nested repos corrupts state
- **Never bypass hooks, signing, or CI gates** (`--no-verify`, `--force`, etc.) — fix the underlying issue or explicitly relax the check
- **Dead-output code → delete, don't refactor**

### Step 5.5 — Compounding checkpoint ritual (run at EVERY meaningful checkpoint, not only at session end)

After each major task completion, pause and ask: *did this session produce insight, a tool, research, or a workflow that will help future sessions?* If yes, route per this table:

| Learning type | Destination | Frequency threshold |
|---|---|---|
| Reusable workflow across projects | Shared skill / plugin / snippet library | Fires 3+ times |
| Domain fact / external research | Knowledge base / wiki entry | Fires 2+ times |
| Active work context for this project | Project's `Documentation.md` | Fires 1+ time |
| Project-local quirk / gotcha | Project's `Implement.md` rules section | Fires 1+ time |
| Cross-project universal behavior rule | Global agent config / CLAUDE.md / AGENTS.md | User approval required |

**Promotion heuristic:** 1× → project file · 2× → KB / team doc · 3+× → reusable skill or system rule.

**Also update durable state at every checkpoint:**

- Append to `Documentation.md` with date, decision, rationale.
- Update `Plan.md` milestone status inline.
- If the runbook changed, update `Implement.md`.

> **Why at every checkpoint, not just at session end:** end-of-session summaries are lossy — you've already forgotten half of what you learned. Capturing at checkpoints preserves insight while it's still fresh.

### Step 6 — Hard gate before any code-writing / artifact-writing tool call

Before your first write operation (code edit, artifact generation, destructive command, external API call that mutates state), print **exactly** this:

```
BLOCKERS_ANSWERED: [Y/N]
STATE_VERIFIED: [Y/N]
SCOPE_CONFIRMED: [Y/N — matches declared session scope from top of this prompt]
DURABLE_STATE_READ: [Y/N — Prompt + Plan + Implement + Documentation all read]
PRIOR_SESSION_CHECKED: [Y/N — no unaddressed past attempt on this exact task]
```

If any field is **N**, stop and ask the user. Do not proceed on autopilot.

> **Why a printed contract, not advisory prose:** advisory instructions get skipped when the agent gets "excited" about a task. A required printed output block is a hard gate that must be passed.

---

## Appendix A — Why each step exists

| Step | Failure mode prevented |
|---|---|
| Scope declaration | Topic drift, ~40% performance loss from mixing tasks |
| 0 — Durable-state stack | "AI Alzheimer's"; relying on compactable context window for state |
| 0.5 — Prior-session lookup | Re-proposing approaches that past sessions tried and rejected |
| 1 — Ordered reading | Skipping load-bearing docs ("critical mental model"), reading in wrong order |
| 2 — Disk verification | Acting on stale memory or drifted handoff claims |
| 2.5 — Context hygiene | Auto-compaction mid-flight killing state; running out of budget mid-task |
| 3 — Blocker questions | Guessing priority when an unknown answer could route the whole session |
| 4 — Ranked conditional work | Picking the wrong task; re-litigating decided tradeoffs |
| 5 — Working protocol | Rediscovering quirks every session; violating non-negotiables |
| 5.5 — Compounding checkpoint | Losing learnings because they weren't captured in time |
| 6 — Hard gate | Autopiloting into writes without verifying state |

## Appendix B — Minimum-viable resumption (for small projects, sessions 2-10)

Keep:
- Scope declaration
- Step 0 (durable-state read)
- Step 2 (state verification — even if lightweight)
- Step 3 (blocker questions)
- Step 6 (hard gate)

Skip:
- Step 0.5 (prior-session lookup) — short history doesn't need it
- Step 1 order strictness — just read what's relevant
- Step 2.5 (context hygiene) — use defaults
- Step 5.5 (compounding ritual) — do at session end only

## Appendix C — Filled-in examples (three diverse project types)

### Example 1: Code project resumption
- PROJECT_NAME: "Checkout latency reduction"
- Scope: "Finish Redis-cache rollout on /checkout; no unrelated refactors"
- Blockers: "Did ops finish the cache-fleet provisioning?" · "Did CFO approve the Redis spend ticket?"
- Carryover: "Dual-cache layer during migration is acceptable — do not simplify until rollout complete"

### Example 2: Marketing operations resumption
- PROJECT_NAME: "MTA → MMM migration"
- Scope: "Ship Q3 CMO dashboard with MMM view; no MTA changes this session"
- Blockers: "Did CMO sign off on channel grouping?" · "Did agency supply YoY baseline data?"
- Carryover: "MTA stays live in parallel dashboards for 90 days — don't remove until 2026-07-01"

### Example 3: Research project resumption
- PROJECT_NAME: "Agent platforms quarterly brief"
- Scope: "Update pricing intelligence section only; other sections reviewed last week"
- Blockers: "Did analyst subscription renew?" · "Do we have the Q1 earnings transcripts from the three target competitors?"
- Carryover: "Methodology section cites a16z Marketplace as substitute for Gartner — approved last brief; do not change"
