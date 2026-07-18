---
type: skill
id: internal-faq-anticipation
title: Internal FAQ Anticipation
description: "Anticipate the questions internal stakeholders will ask about a product decision and draft evidence-based answers"
tags: [Production, Communication, Risk]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "4-6 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Internal FAQ Anticipation

This skill anticipates the questions internal stakeholders — executives, engineering, support, sales, marketing, and legal — will raise about a product decision, and drafts thorough, evidence-based answers for each.

### Core Capability

Given the problem framing and the risk catalogue, this skill generates an internal FAQ spanning strategic rationale, resource and impact, risk and contingency, customer and market impact, and devil's-advocate challenges, then surfaces the likely escalation points and any unvalidated assumptions.

### Method

1. **Group by theme:** Organise anticipated questions into strategic rationale, resource and impact, risk and contingency, customer and market impact, and devil's-advocate themes.
2. **Answer with evidence:** Draft each answer with specific data, numbers, and reasoning rather than appeals to authority; acknowledge trade-offs explicitly.
3. **Flag the gaps:** Identify escalation points where discussion is likely to be contentious and information gaps where an answer relies on assumptions that still need validation.

### Output Structure

A themed internal FAQ of question-and-answer pairs, followed by escalation points and information gaps. It feeds the assembled RFAQ alongside the customer FAQ and risk register.
