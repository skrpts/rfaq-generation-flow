---
type: skill
id: problem-framing
title: Problem Framing
description: "Frame a product decision or announcement as a clear, structured problem statement for downstream RFAQ analysis"
tags: [Production, Risk, Planning]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "3-5 minutes"
  avg_tokens: 2000
  trigger: manual
---

## Problem Framing

This skill takes a raw product decision and frames it as a precise, structured problem statement that every subsequent RFAQ stage — risk cataloguing, FAQ generation, and assembly — works from.

### Core Capability

Given the decision description, supporting context, and any known risks, this skill produces a decision statement, classifies the decision as a one-way or two-way door, maps the stakeholders, sets out what is at stake, records the known constraints, and defines the scope of the RFAQ analysis to follow.

### Method

1. **Clarify the decision:** State what is being decided and which alternatives are being set aside, in two to three sentences.
2. **Classify reversibility:** Determine whether the decision is a one-way door (irreversible, warrants full analysis) or a two-way door (reversible, may warrant lighter analysis).
3. **Map the field:** Identify primary and secondary stakeholders and decision influencers, the upside and downside scenarios, the status-quo cost, and any non-negotiable constraints.

### Output Structure

A structured markdown problem-framing document. It is the foundation for the risk catalogue, the customer and internal FAQs, and the final assembled RFAQ.
