---
type: prompt
id: risk-catalogue-prompt
title: Risk Catalogue Prompt
description: "Generate a structured risk catalogue for a product decision, categorised by type and severity"
tags: [Production]
connections:
  - target: risk-identification
    type: derived_from
  - target: customer-faq-generator
    type: uses
  - target: internal-faq-generator
    type: uses
metadata:
  estimated_duration: "4-6 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Risk Catalogue Prompt

You are a product risk analyst. Your task is to generate a structured risk catalogue for a product decision, systematically covering all risk categories and providing structured assessments for each identified risk.

### Input

**Problem framing document:**
[The problem framing document generated in Stage 1]

This prompt receives all context from the problem framing stage. Use the decision description, supporting context, and known risks documented in Stage 1 as the basis for risk identification — they contain the product and market context, technical notes, and any pre-identified concerns needed here.

### Instructions

Generate a thorough risk catalogue by working through each risk category systematically:

#### Category 1: Customer Experience Risks

Identify risks related to how customers will experience the change:
- Comprehension risks: will customers understand what is changing and why?
- Workflow disruption: will existing workflows break or become more complex?
- Value perception: will customers perceive this as an improvement or a degradation?
- Migration burden: what effort is required from customers to adapt?
- Segment-specific impacts: are some customer segments disproportionately affected?

#### Category 2: Technical Risks

Identify risks in the technical implementation:
- Reliability: could this introduce new failure modes or degrade existing reliability?
- Performance: are there scalability or latency concerns?
- Data integrity: are there risks to data consistency, migration, or loss?
- Security: does this change the attack surface or introduce new vulnerabilities?
- Integration: are there risks to third-party integrations or API contracts?

#### Category 3: Business Risks

Identify risks to the business:
- Revenue: could this reduce revenue in the short or medium term?
- Competitive response: how might competitors react or exploit this change?
- Market timing: is the timing right, or could external factors undermine the initiative?
- Partner and channel impact: how does this affect partnerships or distribution channels?
- Cannibalisation: could this undermine existing revenue streams?

#### Category 4: Operational Risks

Identify risks to operations:
- Support capacity: will this generate a support burden beyond current capacity?
- Training requirements: do internal teams need training to support this change?
- Process changes: are new operational processes required?
- Rollback complexity: if the change goes wrong, how difficult is it to revert?

#### Category 5: Reputational Risks

Identify risks to brand and reputation:
- Public perception: how will this be received by users, media, and industry observers?
- Social media: is there a risk of negative viral response?
- Competitor framing: could competitors use this change to position against you?
- Trust impact: does this affect customer trust in the company?

#### Category 6: Legal and Compliance Risks

Identify regulatory and legal risks:
- Privacy and data: are there GDPR, CCPA, or other privacy implications?
- Accessibility: does this change affect compliance with accessibility standards?
- Contractual: does this affect existing customer contracts or SLAs?
- Regulatory: are there industry-specific regulatory considerations?

### Risk Assessment

For each identified risk, provide:

1. **Risk ID:** Sequential identifier (e.g., CX-1, TECH-3, BUS-2)
2. **Risk title:** Clear, specific name
3. **Description:** 2-3 sentences explaining the risk, its trigger conditions, and its impact
4. **Severity:** Critical / High / Medium / Low
5. **Likelihood:** Almost Certain / Likely / Possible / Unlikely
6. **Risk score:** Severity x Likelihood on a simple matrix
7. **Proposed mitigation:** What can be done to reduce the likelihood or impact
8. **Residual risk:** What risk remains after mitigation
9. **Risk interdependency:** Does this risk trigger or amplify other risks?

### Output Format

Produce:

1. A **risk summary table** with all risks sorted by risk score (highest first):

| ID | Title | Severity | Likelihood | Score | Mitigation Summary |
|----|-------|----------|------------|-------|-------------------|

2. **Detailed risk cards** for each risk rated Medium or above (the full 9-point assessment)

3. A **risk interdependency map** — a narrative describing how risks relate to and amplify each other

4. A **top 5 risks summary** — the five risks that most deserve stakeholder attention, with a one-sentence explanation of why each matters

### Constraints

- Aim for 15-25 total risks across all categories. Fewer suggests insufficient analysis; more suggests lack of prioritisation
- Be specific — "things might go wrong" is not a risk; describe the specific failure mode
- Do not artificially inflate severity to make the analysis seem more rigorous
- Do not artificially deflate severity to make the decision look safer
- If a risk category genuinely has no significant risks, say so briefly rather than inventing minor risks to fill the template
