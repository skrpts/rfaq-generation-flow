---
type: skill
id: risk-identification
title: Risk Identification
description: "Systematic identification of risks, assumptions, and failure modes for product decisions"
tags: [Production, Tested]
connections:
  - target: llm-service
    type: runs_on
  - target: rfaq-methodology-reference
    type: references
metadata:
  estimated_duration: "5-8 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Risk Identification

This skill enables the systematic identification and categorisation of risks associated with product decisions, feature launches, and strategic initiatives. It goes beyond surface-level risk listing to uncover hidden assumptions, second-order effects, and failure mode cascades.

### Core Capabilities

#### Multi-Category Risk Scanning

When analysing a product decision, scan for risks across all relevant categories:

**Customer Experience Risks**
- Will customers understand the change? Is there a risk of confusion?
- Could this increase friction in existing workflows?
- Are there segments that will be negatively affected while others benefit?
- Could this trigger churn, especially among high-value accounts?
- What happens to customers mid-workflow when the change rolls out?

**Technical Risks**
- Are there scalability concerns at the expected load?
- Does this introduce new single points of failure?
- Are there data migration risks? What happens if migration fails partially?
- Does this depend on third-party services with their own reliability characteristics?
- Are there security or privacy implications?

**Business Risks**
- How will competitors likely respond? Could this trigger a competitive reaction?
- Is the timing right, or could market conditions make this irrelevant?
- What is the revenue impact if adoption is lower than expected?
- Are there contractual or partnership implications?
- Could this cannibalise existing revenue streams?

**Operational Risks**
- Will the support team be prepared? What is the expected ticket volume?
- Are there training requirements for internal teams?
- Does this create manual processes that should be automated?
- What is the rollback plan if things go wrong?

**Reputational Risks**
- How will this be perceived on social media and in the press?
- Could this be framed negatively by competitors or critics?
- Does this align with the company's stated values and brand positioning?

**Legal and Compliance Risks**
- Are there regulatory requirements that apply?
- Does this affect data handling in ways that require privacy review?
- Are there accessibility implications?

#### Assumption Surfacing

Every product decision rests on assumptions — explicit and implicit. This skill surfaces them:

1. **List all assumptions** underlying the decision ("We assume customers will adopt this within 30 days", "We assume the API can handle 10x current traffic")
2. **Rate each assumption's validity:** Validated (tested), Reasonable (supported by evidence), Untested (believed but not confirmed), Risky (plausible but could easily be wrong)
3. **Identify the riskiest assumptions** — those that are both untested and load-bearing (the decision fails if the assumption is wrong)

#### Failure Mode Analysis

For the decision under analysis:

1. **Pre-mortem:** Imagine it is six months in the future and the decision has failed. What went wrong? Work backwards from failure to identify the most likely failure paths.
2. **Cascade analysis:** For each significant risk, ask "and then what?" — if this risk materialises, what secondary risks does it trigger?
3. **Reversibility assessment:** Classify the decision as a one-way door (irreversible or very costly to reverse) or a two-way door (easily reversible). One-way door decisions require more rigorous risk analysis.

### Output Standards

Risk identification output must include:
- A categorised risk register with severity (Critical/High/Medium/Low) and likelihood (Almost Certain/Likely/Possible/Unlikely)
- An assumptions register with validity ratings
- A pre-mortem narrative describing the most likely failure scenario
- A reversibility assessment of the overall decision

### Constraints

- Err on the side of identifying more risks, not fewer — it is cheaper to dismiss a risk than to be surprised by one
- Distinguish between risks (things that might go wrong) and issues (things that are already wrong)
- Never dismiss a risk because "we will deal with it later" — if it is worth mentioning, it is worth proposing a mitigation
- Be specific — "technical risk" is not a risk; "the real-time sync service may exceed its 99.9% SLA target under the projected load increase" is a risk
