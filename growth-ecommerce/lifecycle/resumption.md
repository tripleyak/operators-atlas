# Lifecycle Program — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`
>
> **Use when:** sessions 2+ of a lifecycle program bootstrapped with `lifecycle/bootstrap.md`.

---

## Session scope examples

- "Launch welcome flow v2"
- "Diagnose revenue/message decline"
- "Segment audit + RFM rebuild"
- "Deliverability incident response"
- "SMS program launch — consent + compliance setup"

## Blocker questions

1. **Is deliverability healthy?** If spam rate >0.3% or inbox placement <90%, pause all new sends; fix deliverability first. Nothing else matters if emails go to spam.
2. **Is the consent architecture intact?** Any recent changes to opt-in flow, double-opt-in, or SMS consent? If yes, verify before any send.
3. **Is there an active SMS / email campaign about to send?** Frequency-cap conflict risk. Check calendar before scheduling.
4. **Has the ESP pushed any platform changes / feature migrations?** Klaviyo / Attentive / Braze routinely sunset features; check release notes.
5. **Any compliance / legal request pending?** Data deletion requests, CAN-SPAM complaints, TCPA concerns — these take priority.

## Ranked work patterns

### If deliverability is in decline
Everything else pauses. Diagnostic sequence:
1. Volume spike? (sudden send-rate increase)
2. List hygiene? (inactive addresses not sunset)
3. Content signal? (spammy subject lines, unsubscribe-hiding, heavy image-to-text)
4. Authentication? (SPF / DKIM / DMARC — any recent DNS change?)
5. Complaint rate? (content resonance issue or list-quality issue)

Fix root cause, not symptom.

### If revenue/message is flat or declining with volume up
Segmentation is probably broken. Run RFM segment audit. Check: are we sending cart recovery to people who bought 10 seconds ago? Welcome to already-repeat customers? This is the #1 cause of the pattern.

### If a flow is converting but volume is low
List-growth problem, not lifecycle problem. Flag as cross-program learning; stay scoped.

### If new flow build is approved
Follow standard sequence:
1. Write hypothesis + KPIs in `Documentation.md`
2. Build in ESP as draft
3. Test-send every branch to team
4. Legal/brand review
5. Launch to 10% hold-back test (if possible) before full rollout

## Working protocol additions

- **Never skip test sends.** Every branch, every personalization token, every trigger condition.
- **Never change flow logic mid-test.** Let current data complete.
- **Never launch an SMS flow without legal sign-off** — TCPA risk is real
- **Always document frequency-cap state** before adding a new flow — how many touches does a subscriber now receive in worst-case?
- **Always check unsubscribe flow** after any consent architecture change

## Domain verification commands (Step 2)

```
# Deliverability health
{postmaster tools check}                 # expect: spam rate <0.3%, reputation High

# Inbox placement
{monthly 250ok or GlockApps check}       # expect: >95% primary inbox

# Suppression rate trend
{ESP suppression-rate query}             # expect: <20% email, <2% SMS of list

# Revenue/message trend
{dashboard 4-week rolling}               # expect: flat or up

# Flow health
{active-flow-list query}                 # expect: all flows fired in last 7d
```

## Common drift patterns

- **Adding channels to existing flows** — every added channel (SMS to email flow, push to SMS flow) changes frequency cap math. Don't add without recalculating total touches.
- **Personalization creep** — each dynamic field is another breakpoint. Use sparingly and test rigorously.
- **Compliance regression** — a platform update or migration can break consent logic silently. Re-test after any ESP upgrade.
