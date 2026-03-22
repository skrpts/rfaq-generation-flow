---
type: workflow
id: rfaq-generation-flow
title: RFAQ Generation Flow
description: "Multi-stage pipeline that generates Amazon-style RFAQ documents for product decisions, press releases, and launches"
tags: [Production, Tested]
connections:
  - target: risk-identification
    type: uses
  - target: faq-anticipation
    type: uses
  - target: counter-argument-construction
    type: uses
  - target: rfaq-problem-framer
    type: uses
  - target: risk-catalogue-prompt
    type: uses
  - target: customer-faq-generator
    type: uses
  - target: internal-faq-generator
    type: uses
  - target: rfaq-assembler
    type: uses
  - target: llm-service
    type: runs_on
  - target: rfaq-methodology-reference
    type: references
  - target: rfaq-writing-guide
    type: references
  - target: rfaq-document-template
    type: references
  - target: risk-register-template
    type: references
metadata:
  estimated_duration: "20-30 minutes"
  avg_tokens: 14000
  trigger: manual
---

## RFAQ Generation Flow

This workflow generates structured RFAQ (Risks and Frequently Asked Questions) documents following Amazon's Working Backwards methodology. RFAQs are structured documents that force product teams to confront risks, anticipate questions, and prepare thoughtful responses before committing to a decision or launch.

### Prerequisites

Before running this workflow, prepare:

- A clear description of the product decision, feature launch, or announcement under consideration
- The target audience(s) — who will be affected by this decision
- Any existing documentation (PRD, one-pager, press release draft) that describes the initiative
- Known constraints, dependencies, or risks already identified
- Context on the competitive landscape and market conditions

### Pipeline Stages

#### Stage 1: Problem Framing

**Node:** `rfaq-problem-framer`

- Accept the raw decision description and supporting context
- Frame the decision clearly: what is being decided, what are the options, who is affected, and what is at stake
- Identify the decision type: reversible (two-way door) vs. irreversible (one-way door)
- Establish the scope of the RFAQ: is this a full product launch, a feature change, a pricing decision, a strategic pivot?
- Define the audience segments whose questions and concerns must be anticipated: customers, internal stakeholders, press, partners, regulators
- Output: a structured problem statement ready for risk and FAQ analysis

**Error handling:** If the problem description is too vague to analyse meaningfully, return a set of clarifying questions rather than proceeding with assumptions.

#### Stage 2: Risk Cataloguing

**Node:** `risk-catalogue-prompt`
**Skill:** `risk-identification`
**References:** `rfaq-methodology-reference`

- Systematically identify risks across multiple categories:
  - Customer experience risks (confusion, dissatisfaction, churn)
  - Technical risks (reliability, scalability, security, data integrity)
  - Business risks (revenue impact, competitive response, market timing)
  - Operational risks (support burden, training needs, process changes)
  - Reputational risks (brand perception, press reaction, social media response)
  - Legal and compliance risks (regulatory, contractual, privacy)
- For each risk, assess severity, likelihood, and reversibility
- Identify risk interdependencies — where one risk materialising triggers others
- Propose initial mitigation strategies for each significant risk
- Output: a structured risk catalogue with severity ratings and mitigations

#### Stage 3: FAQ Generation (Parallel)

Run customer and internal FAQ generation in parallel:

##### Stage 3a: Customer FAQ Generation

**Node:** `customer-faq-generator`
**Skill:** `faq-anticipation`

- Anticipate the questions customers will ask when this decision is announced or implemented
- Cover categories: what is changing, why, how it affects them, what they need to do, migration paths, pricing impact, timeline, support options
- For each question, draft a clear, honest answer that acknowledges concerns without being defensive
- Identify "hostile" questions — the hardest, most uncomfortable questions a sceptical customer might ask — and prepare responses for those too
- Order questions from most likely to least likely

##### Stage 3b: Internal FAQ Generation

**Node:** `internal-faq-generator`
**Skill:** `faq-anticipation`

- Anticipate questions from internal stakeholders: executives, board members, engineering, support, sales, marketing, legal
- Cover categories: strategic rationale, resource requirements, success metrics, rollback plan, competitive implications, timeline, team impact
- For each question, draft a response grounded in data and strategy
- Include "devil's advocate" questions — the ones someone will ask to challenge the decision — with thorough, evidence-based responses
- Ensure sales and support teams have answers for customer-facing scenarios

**Error handling:** If the problem framing does not provide enough context for meaningful FAQ generation, flag the specific information gaps rather than inventing answers.

#### Stage 4: Counter-Argument Development

**Skill:** `counter-argument-construction`
**References:** `rfaq-writing-guide`

- Review the risk catalogue and FAQ responses for weaknesses
- For each high-severity risk, develop a rigorous counter-argument: why is the decision still correct despite this risk?
- For each hostile question, stress-test the drafted answer: would it survive a follow-up challenge?
- Identify any arguments that are weak — where the honest answer is "we do not have a good response to this yet" — and flag these for further work
- Output: strengthened arguments and a list of unresolved concerns

#### Stage 5: Document Assembly

**Node:** `rfaq-assembler`
**References:** `rfaq-document-template`

- Assemble all components into a complete RFAQ document following the standard template
- Structure: Problem Statement, Decision Overview, Risk Register (categorised), Customer FAQ, Internal FAQ, Counter-Arguments, Unresolved Concerns, Decision Recommendation
- Ensure internal consistency — risks mentioned in one section should be addressed in the FAQ, and FAQ answers should not contradict the risk assessments
- Include a decision recommendation: proceed, proceed with modifications, defer pending further research, or do not proceed
- Add an executive summary at the top: 3-5 sentences covering the decision, the key risks, and the recommendation

### Output

The final output is a complete RFAQ document containing:

1. **Executive summary** — decision, key risks, recommendation
2. **Problem statement** — what is being decided and why
3. **Risk register** — categorised risks with severity, likelihood, mitigations
4. **Customer FAQ** — 10-20 anticipated customer questions with prepared answers
5. **Internal FAQ** — 10-15 anticipated internal questions with prepared responses
6. **Counter-arguments** — rigorous responses to the strongest objections
7. **Unresolved concerns** — honest acknowledgement of remaining uncertainties
8. **Decision recommendation** — proceed / modify / defer / reject

### Error Handling

- **Insufficient context:** Return clarifying questions; do not generate an RFAQ from vague inputs
- **Overwhelming risks:** If the risk catalogue is extensive, prioritise the top 10 by severity x likelihood rather than listing everything
- **Contradictory information:** Surface contradictions in the input data explicitly rather than silently resolving them
- **Unresolvable concerns:** It is acceptable and valuable for an RFAQ to conclude "we cannot adequately mitigate this risk — the decision should be deferred until we can"

## Inputs

| Name | Required | Description | Example |
|------|----------|-------------|---------|
| `{{input.decision_description}}` | Yes | Description of the product decision, feature launch, or announcement under consideration | "We are considering replacing our per-seat pricing model with usage-based pricing, effective Q3 2026, affecting all customers." |
| `{{input.supporting_context}}` | No | Existing documentation — PRD, one-pager, press release draft, or any context that describes the initiative | "See attached PRD for the usage-based pricing proposal. Key driver: enterprise customers want to pay for what they use." |
| `{{input.audience_segments}}` | No | Target audiences affected by this decision — customers, internal teams, press, partners, regulators | "Enterprise customers (200+ seats), SMB customers (under 50 seats), sales team, support team, key partners." |
| `{{input.known_risks}}` | No | Constraints, dependencies, or risks already identified | "Legal has flagged that existing annual contracts cannot be changed mid-term. Three enterprise customers have expressed concern." |

## Outputs

| Name | Description |
|------|-------------|
| Workflow output | Final output generated by this workflow |

## Setup

Before running this workflow:

1. No external services required — paste your content directly and provide any supporting context as inputs or source nodes.
2. Review the included documents, assets, or source nodes and customise them to match your team, brand, or domain conventions where needed.
3. No specific AI provider or API key is required beyond your configured skrptiq LLM provider.

## Provider Notes

- Most stages work with any capable model; stronger models usually improve synthesis, judgement, and writing quality.
- Extraction, classification, and formatting steps generally run well on smaller or faster models.
- Because there are no vendor-specific integrations here, provider choice is mostly a trade-off between speed, quality, and cost.

## Example Input

To test this workflow immediately after import:

```
Decision Description: "We are considering replacing our current per-seat pricing model with a
usage-based pricing model, effective Q3 2026, affecting all new customers immediately and
existing customers at their next renewal date."

Supporting Context: "Enterprise customers have repeatedly asked for usage-based pricing.
Three of our top 10 accounts are currently over-provisioned and paying for seats they don't use.
Competitor X launched usage-based pricing last quarter."

Audience Segments: "Enterprise customers, SMB customers, sales team, support team, finance team."
```

