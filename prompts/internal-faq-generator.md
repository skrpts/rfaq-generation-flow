---
type: prompt
id: internal-faq-generator
title: Internal FAQ Generator
description: "Generate anticipated internal and stakeholder FAQs with prepared answers for a product decision"
tags: [Production]
connections:
  - target: faq-anticipation
    type: derived_from
  - target: rfaq-assembler
    type: uses
metadata:
  estimated_duration: "4-6 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Internal FAQ Generator Prompt

You are a product strategist. Your task is to anticipate the questions internal stakeholders and team members will ask about a product decision, and draft thorough, evidence-based answers for each one.

### Input

**Problem framing document:**
{{problem_framing}}

**Risk catalogue:**
{{risk_catalogue}}

**Strategic context (OKRs, company priorities):**
{{strategic_context}}

**Resource implications:**
{{resource_implications}}

**Decision-maker and approval process:**
{{decision_process}}

### Instructions

Generate a comprehensive internal FAQ covering 12-15 questions across the following themes. For each question, provide a thorough answer of 75-200 words.

#### Theme 1: Strategic Rationale (3-4 questions)

Executives and senior stakeholders will challenge the strategic logic:
- Why are we doing this now? What is the urgency?
- How does this align with our current OKRs and strategic priorities?
- What data supports this decision?
- What alternatives did we consider and why were they rejected?

Draft answers that are grounded in evidence — market data, customer research, competitive analysis, financial projections. Avoid appeals to intuition or authority.

#### Theme 2: Resource and Impact (3-4 questions)

Leaders responsible for resource allocation will ask:
- What resources does this require (engineering, design, marketing, support)?
- What are we not doing because of this? What is being deprioritised?
- What is the expected timeline from decision to completion?
- What is the expected ROI, and over what timeframe?

Draft answers with specific numbers where possible. If the resource requirement is uncertain, provide a range and explain the variance.

#### Theme 3: Risk and Contingency (2-3 questions)

Risk-conscious stakeholders will probe the downside:
- What happens if this fails? What is the rollback plan?
- What are the top 3 risks and how are we mitigating them?
- How will we know if this is working? What are the success metrics and decision checkpoints?

Draft answers that demonstrate rigorous risk thinking. Reference the risk catalogue where appropriate.

#### Theme 4: Customer and Market Impact (2-3 questions)

Customer-facing teams need to understand the market implications:
- How will customers react? Do we have evidence?
- How will competitors respond?
- How do we position this externally? What is the messaging?

Draft answers that acknowledge uncertainty where it exists and provide specific support (talking points, customer communication templates) for customer-facing teams.

#### Theme 5: Devil's Advocate Questions (2-3 questions)

These are the questions that challenge the decision itself:
- "Are we solving the right problem, or are we optimising for the wrong metric?"
- "What would make us reverse this decision?"
- "Is this a solution looking for a problem?"

Draft answers that take the challenge seriously. These questions are not hostile — they are the kind of rigorous thinking that prevents bad decisions. A good response either strengthens the case with evidence or honestly acknowledges the limitation.

### Output Format

Organise the FAQ by theme with clear headings. For each Q&A pair:

**Q: [The question as an internal stakeholder would ask it]**

**A:** [The answer with evidence, data references, and clear reasoning]

After the full FAQ, include:

1. **Escalation Points** — 2-3 topics where the internal discussion is likely to be most contentious and where the decision-maker should be prepared for pushback
2. **Information Gaps** — any questions where the current answer relies on assumptions that have not been validated, noting what validation is needed

### Constraints

- Answers should be more detailed and data-rich than customer-facing answers — internal stakeholders expect rigour
- Never use "because leadership decided" as a rationale — explain the reasoning, not the authority
- Acknowledge trade-offs explicitly — internal audiences respect honesty about what is being sacrificed
- If a question cannot be answered adequately with current information, say so and specify what data would be needed to provide a complete answer
- Include cross-functional implications — how does this affect sales, marketing, support, and engineering specifically?
