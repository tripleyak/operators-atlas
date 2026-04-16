# The Operator's Atlas

> **77 opinionated prompt templates for growth marketers and ecommerce operators running multi-session AI-agent work. Across 23 workstreams. Free.**

🌐 **Landing page:** https://operators-atlas.vercel.app
📦 **Direct download:** https://operators-atlas.vercel.app/the-operators-atlas-v1.zip

## What this is

Not another listicle of ChatGPT prompts. These are structured multi-session templates with non-negotiable-by-default rules baked in from real programs. They prevent AI agents from drifting across 10+ sessions — the #1 failure mode of long-horizon AI-agent work.

Every template includes:

- **Opinionated defaults** from real operator programs
- **Inheritance hierarchy** — specialized templates inherit discipline from general-purpose masters
- **Milestone scaffolding** with concrete validation criteria
- **Mental-model framing** that reframes how the domain work gets done
- **Working-protocol guardrails** that keep programs on-rails

## What's inside

| Type | Count | What |
|---|---|---|
| General-purpose masters | 6 | Universal kickoff (session 1 + session N) + 4 deep-research archetypes |
| Specialized domain templates | 69 | 23 workstreams × 3 template types (bootstrap + resumption + deep-research) |
| Organizational indexes | 2 | Top-level library guide + growth-ecommerce decision tree |
| **Total** | **77** | In both markdown (.md) and Word (.docx) formats |

See [`LIBRARY_GUIDE.md`](LIBRARY_GUIDE.md) for the full library structure + decision trees.

## The 23 domains

### Tier 1 — Core (8)

Paid media · Lifecycle (email/SMS/push) · CRO · Attribution/MMM · Amazon · Retention/LTV · SEO/content · Launch/GTM

### Tier 2 — Specialized (6)

Influencer/creator · Subscription/loyalty · Brand positioning · Wholesale/retail · Geo expansion · Martech stack

### Tier 3 — Additional (9)

B2B lead generation · Event marketing · Community/ambassador · Offline media (DM/OOH/CTV/TV) · PR/earned media · Sustainability/ESG · Affiliate · UGC/reviews · Pricing/promotion

## Quick start

```bash
git clone https://github.com/tripleyak/operators-atlas.git
cd operators-atlas
```

Then:

1. **Pick your workstream.** Open [`growth-ecommerce/README.md`](growth-ecommerce/README.md) for the decision tree.
2. **Run the general master first.** In your AI agent session, paste the content from [`session-kickoff-bootstrap.md`](session-kickoff-bootstrap.md) (for session 1) or [`session-kickoff-prompt.md`](session-kickoff-prompt.md) (for session 2+).
3. **Apply the domain specialization.** Overlay the relevant `growth-ecommerce/{domain}/bootstrap.md` or `resumption.md`.

The agent inherits universal discipline from the master + domain-specific opinionated defaults automatically.

## Sample — what an opinionated default block looks like

From [`growth-ecommerce/paid-media/bootstrap.md`](growth-ecommerce/paid-media/bootstrap.md):

```
## Opinionated defaults

### Measurement
- Blended MER is primary; platform ROAS is diagnostic
- MTA + MMM shown side-by-side always
- Attribution: 7-day click / 1-day view for paid social

### Testing discipline
- Learning phase respect: ≥50 conversions in 7 days before trusting signals
- No stop-start within learning phase
- Creative test matrix: 4×4 minimum (4 audiences × 4 creatives)
- Kill losers: anything <0.5× target MER for 14 days → pause

### Scaling
- Scale ladder: ≤20% budget increase per 72 hours per campaign
- CAC payback: <90 days existing channel, <180 days new channel
- Channel expansion gate: 60+ days at target CAC before new channel
```

Every specialized template ships with 30-60 similar non-negotiable-by-default rules. Override with explicit reason — they're starting points, not gospel.

## Agent compatibility

Works with any AI agent that can read files or accept a pasted prompt:

- **Coding agents:** Claude Code · Cursor · Windsurf · Zed AI · Copilot · Codex CLI · Aider · Continue · Cline
- **Hosted agents:** Anthropic Managed Agents · OpenAI Operator · enterprise platforms
- **Web UIs:** ChatGPT · Claude.ai · Gemini

## File conventions

- `{{PLACEHOLDER}}` — variables you fill in per project (`{{PROJECT_NAME}}`, `{{BUDGET}}`, etc.)
- `{{KNOWLEDGE_BASE_ROOT}}` / `{{WORK_VAULT_ROOT}}` — optional references to personal infrastructure (Obsidian, Notion, wiki, etc.). Delete references if you don't maintain one; nothing downstream depends on it.

## License

Creative Commons Attribution 4.0 International (CC BY 4.0). See [`LICENSE.md`](LICENSE.md).

**TL;DR:** use, adapt, commercialize. Attribution appreciated but not required.

## Contributing / feedback

- **Issues:** spot something wrong or missing? [Open an issue](https://github.com/tripleyak/operators-atlas/issues).
- **PRs:** typo fixes, benchmark corrections, new opinionated defaults — welcome. Keep the operator-voice ("what actually works in practice"), not agency-speak.
- **New domains:** v2 will expand Tier 3 (partnerships/BD, direct-response copy, CX/support). Suggestions welcome via issues.

For direct feedback: DM on [LinkedIn](https://www.linkedin.com/in/jackatlasov).

## About

Built by [Jack Atlasov](https://www.linkedin.com/in/jackatlasov) — VP at BirdRock Home (acquired April 2026), multi-year operator at growth-stage DTC + consumer brands.

Every template comes from real programs, not theory. The Atlas is the playbook I wish I'd had when I took my first VP role.

## Version history

- **v1.0** (April 2026) — Initial release. 6 general-purpose masters + 23 specialized domains × 3 templates = 77 total.

## Related

- Landing page: https://operators-atlas.vercel.app
- Latest ZIP: https://operators-atlas.vercel.app/the-operators-atlas-v1.zip
- Library internals: [`LIBRARY_GUIDE.md`](LIBRARY_GUIDE.md)

---

⭐ **If this helps, star the repo** — it helps other operators find it.
