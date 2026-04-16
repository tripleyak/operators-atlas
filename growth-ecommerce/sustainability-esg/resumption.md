# Sustainability / ESG — Resumption

> **Inherits from:** `~/.claude/templates/session-kickoff-prompt.md`

---

## Session scope examples

- "B-Corp recertification audit prep"
- "Scope 3 emissions inventory annual refresh"
- "Supply-chain tier 2 visibility project"
- "Sustainability report drafting"
- "FTC Green Guides compliance review"
- "Greenwashing-risk audit of current marketing claims"

## Blocker questions

1. **Any regulatory inquiry / legal notice active?** Priority — resolve before advancing program
2. **Any certification audit upcoming in next 60 days?**
3. **Any supply-chain incident** (violation, media coverage) requiring response?
4. **Any marketing claim pending publish** that needs legal + substantiation review?
5. **Any stakeholder deadline** (investor report, RFP response, retail-partner submission)?

## Ranked work patterns

### If greenwashing-risk audit
Systematic review:
1. Every public claim catalog
2. Substantiation documented per claim
3. Claims without substantiation — kill or substantiate
4. FTC Green Guides specifically — generic terms ("sustainable," "eco-friendly") need specifics
5. Packaging + website + marketing materials comprehensive sweep
6. Internal training so claims don't recur without substantiation

### If certification in flight
Standard audit prep:
1. BIA / framework gap analysis
2. Documentation collection
3. Operational improvements required
4. Timeline to submission
5. Post-certification improvement commitments

### If annual reporting due
Standard cycle:
1. Data collection — emissions, social, governance
2. Year-over-year comparison + narrative
3. Progress vs. SBTi / stated goals
4. Report drafting + design
5. Legal review
6. Publication + stakeholder distribution

### If supplier incident
Speed + discipline:
1. Incident scope + facts
2. Remediation plan with supplier
3. Public statement (if applicable)
4. Audit other suppliers for similar risk
5. Update supplier code of conduct

## Working protocol additions

- **Never publish claim without legal review**
- **Never skip third-party verification** on major claims
- **Never defer regulatory responses**
- **Always document substantiation**
- **Always coordinate legal + marketing + operations** for program decisions

## Verification commands

```
# Claim substantiation
{public claims audit with substantiation} # expect: 100% substantiated

# Certification status
{certification expiration + audit schedule} # expect: current, audits scheduled

# Scope 1/2/3 measurement
{emissions inventory freshness}             # expect: current-year data in progress

# Supply chain visibility
{tier 1 / 2 visibility %}                   # expect: 100% tier 1; >50% tier 2

# Report publication cadence
{last annual report date}                   # expect: within 12 months
```

## Common drift patterns

- **Marketing-operations disconnect** — marketing over-claims; operations can't support; greenwashing risk
- **Certification complacency** — certify once, drift; re-audit catches issues
- **Scope 3 avoidance** — tempting to claim "carbon neutral on scopes 1+2" but risk of criticism
- **Claim inflation** — each marketer adds stronger language; substantiation doesn't keep up
- **Supply-chain blind spots** — tier 2/3 incidents blindside brands without visibility
