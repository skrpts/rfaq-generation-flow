---
type: service
id: claude-service
title: Claude Service
description: "How this skrpt uses Claude for risk identification, FAQ generation, and counter-argument construction"
tags: [Production, Tested]
connections:
  - target: rfaq-generation-flow
    type: runs_on
metadata:
  provider: "anthropic"
  model: "claude-sonnet"
  estimated_tokens_per_run: 14000
---

## Claude Service — RFAQ Generation Flow

This skrpt uses Anthropic Claude as its primary AI service for all risk analysis and FAQ generation tasks.

### Usage Pattern

Claude is invoked at each stage of the RFAQ pipeline:

1. **Problem framing** — structuring the decision for analysis
2. **Risk cataloguing** — systematic multi-category risk identification
3. **Customer FAQ generation** — anticipating customer questions and drafting responses
4. **Internal FAQ generation** — anticipating stakeholder questions and drafting evidence-based responses
5. **Counter-argument construction** — stress-testing risk mitigations and hostile question responses
6. **Document assembly** — synthesising all components into a cohesive RFAQ document

### Model Requirements

- **Adversarial reasoning:** The risk identification and counter-argument stages require the model to argue against the proposed decision — it must be willing to identify and articulate genuine weaknesses
- **Audience modelling:** FAQ generation requires simulating how different audience segments (customers, executives, engineers) think and what they care about
- **Analytical rigour:** Risk assessment requires structured, systematic analysis across multiple categories without omitting uncomfortable findings
- **Tone control:** Customer FAQ answers require empathetic, professional tone; internal FAQ answers require evidence-based, rigorous tone

### Token Budget

- Typical full pipeline run: 12,000-16,000 tokens
- Problem framing: 1,500-2,000 tokens
- Risk catalogue: 2,500-3,500 tokens
- Customer FAQ: 2,500-3,000 tokens
- Internal FAQ: 2,500-3,000 tokens
- Counter-arguments: 2,000-2,500 tokens
- Document assembly: 2,500-3,500 tokens

### Configuration

- Temperature: 0.4 (moderate — allows creative question anticipation while maintaining analytical accuracy)
- System prompt should emphasise honesty, rigour, and willingness to identify genuine weaknesses
- For counter-argument stages, instruct the model to steel-man objections before responding
