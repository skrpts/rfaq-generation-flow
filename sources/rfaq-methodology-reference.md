---
type: source
id: rfaq-methodology-reference
title: RFAQ Methodology Reference
description: "Reference guide to RFAQ methodology, Amazon's Working Backwards process, and structured risk-based decision-making"
tags: [Production, Customer-Facing]
connections: []
metadata:
  source_type: "reference-material"
  last_updated: "2026-03-10"
---

## RFAQ Methodology Reference

### Origins: Amazon's Working Backwards Process

The RFAQ (Risks and Frequently Asked Questions) document is a key artefact in Amazon's "Working Backwards" product development process. Working Backwards starts from the customer experience and works backwards to the technology, rather than starting with what is technically possible.

The process typically produces two documents:

1. **PR/FAQ (Press Release / Frequently Asked Questions):** A fictional press release announcing the product as if it were already launched, followed by anticipated customer and internal questions. The PR/FAQ forces teams to articulate the customer benefit clearly before investing in development.

2. **RFAQ (Risks and Frequently Asked Questions):** A companion document that systematically identifies risks, catalogues anticipated objections, and prepares counter-arguments. The RFAQ ensures teams confront potential failure modes before committing resources.

This skrpt focuses on the RFAQ component, as it is the more analytically rigorous of the two and is applicable to any significant product decision, not just new product launches.

### RFAQ Structure

A standard RFAQ document contains:

#### Problem Statement
- What decision is being considered
- Why now (urgency and context)
- Who is affected (stakeholder map)
- What is at stake (upside and downside scenarios)

#### Risk Register
A structured catalogue of risks, typically covering:
- Customer experience risks
- Technical risks
- Business and market risks
- Operational risks
- Reputational risks
- Legal and compliance risks

Each risk includes severity, likelihood, proposed mitigation, and residual risk.

#### Customer FAQ
10-20 anticipated questions from customers, covering:
- What is changing
- How it affects them
- What they need to do
- Alternatives if they disagree
- Hostile/sceptical questions with prepared responses

#### Internal FAQ
10-15 anticipated questions from internal stakeholders, covering:
- Strategic rationale
- Resource requirements
- Risk management
- Market implications
- Devil's advocate challenges

#### Counter-Arguments
For each significant risk or hostile question, a structured response:
- The objection (stated in its strongest form)
- The counter-argument (with evidence)
- The residual risk after mitigation

#### Unresolved Concerns
An honest accounting of risks that cannot be adequately mitigated and questions that cannot be satisfactorily answered with current information.

#### Decision Recommendation
A clear recommendation (proceed / proceed with modifications / defer / do not proceed) with supporting rationale.

### Key Principles

#### 1. Intellectual Honesty

The RFAQ is only valuable if it is honest. An RFAQ that minimises risks to make a decision look better is worse than no RFAQ at all. The most valuable section is often "Unresolved Concerns" — the risks and questions the team cannot yet address.

#### 2. Customer Obsession

FAQs should be written from the customer's perspective, not the company's. Customers do not care about your OKRs or your engineering constraints. They care about how the change affects their workflow, their costs, and their trust in your product.

#### 3. Disagree and Commit

The RFAQ process is designed to surface disagreement before a decision is made. Once the RFAQ has been reviewed and the decision taken, the team commits to execution regardless of whether they personally agreed with every element.

#### 4. One-Way vs. Two-Way Doors

Amazon distinguishes between Type 1 (irreversible) and Type 2 (reversible) decisions. Type 1 decisions warrant thorough RFAQ analysis. Type 2 decisions should be made quickly with lighter-weight analysis — over-analysing reversible decisions is as wasteful as under-analysing irreversible ones.

#### 5. Pre-Mortem Thinking

The RFAQ encourages pre-mortem thinking: imagining that the decision has already failed and working backwards to identify what went wrong. This surfaces risks that optimism bias would otherwise conceal.

### When to Write an RFAQ

Write a full RFAQ for:
- Product launches or significant feature releases
- Pricing model changes
- Platform migrations or architectural decisions
- Market entry or exit decisions
- Partnership or acquisition decisions
- Any Type 1 (irreversible) decision with significant financial or customer impact

Use a lightweight version (problem statement + top 5 risks + key FAQs only) for:
- Feature iterations within an established direction
- Type 2 (reversible) decisions
- Internal process changes with limited external impact

### Common RFAQ Pitfalls

| Pitfall | Description | Remedy |
|---------|-------------|--------|
| Confirmation bias | Writing the RFAQ to justify a decision already made | Write the risk register before forming the recommendation |
| Shallow risks | Listing risks without analysing their implications | Use "and then what?" analysis to explore second-order effects |
| Defensive FAQ | Answers that deflect rather than address the question | Apply the steel-man technique: strengthen the question before answering |
| Missing voices | FAQ that only anticipates questions from supporters | Include a hostile question section for every audience segment |
| Premature resolution | Marking unresolved concerns as "mitigated" without evidence | Maintain separate sections for mitigated risks and unresolved concerns |
