---
type: asset
id: rfaq-document-template
title: RFAQ Document Template
description: "Template for the complete RFAQ document"
tags: [Production, Customer-Facing]
connections: []
metadata:
  asset_type: "template"
  format: "markdown"
---

## RFAQ Document Template

---

# RFAQ: {{decision_title}}

**Version:** {{version}}
**Date:** {{date}}
**Author:** {{author_name}}, {{author_role}}
**Decision-maker:** {{decision_maker}}
**Decision deadline:** {{decision_deadline}}
**Status:** Draft / Under Review / Final

---

## Table of Contents

1. Executive Summary
2. Problem Statement
3. Risk Register
4. Customer FAQ
5. Internal FAQ
6. Counter-Arguments
7. Unresolved Concerns
8. Decision Recommendation

---

## 1. Executive Summary

**Decision:** {{decision_statement_one_line}}

**Risk profile:** Low / Moderate / High / Critical

**Top risks:**
1. {{top_risk_1}}
2. {{top_risk_2}}
3. {{top_risk_3}}

**Recommendation:** Proceed / Proceed with modifications / Defer / Do not proceed

**Rationale:** {{recommendation_rationale}}

**Key conditions:** {{conditions_for_recommendation}}

---

## 2. Problem Statement

### Decision Statement
{{decision_statement_detailed}}

### Decision Type
One-way door (Type 1) / Two-way door (Type 2)

**Reasoning:** {{decision_type_reasoning}}

### Stakeholder Map

| Stakeholder Group | Role | Expected Reaction | Key Concerns |
|-------------------|------|-------------------|--------------|
| {{stakeholder_1}} | Primary / Secondary / Influencer | Positive / Neutral / Concerned / Opposed | {{concerns_1}} |
| {{stakeholder_2}} | Primary / Secondary / Influencer | Positive / Neutral / Concerned / Opposed | {{concerns_2}} |
| {{stakeholder_3}} | Primary / Secondary / Influencer | Positive / Neutral / Concerned / Opposed | {{concerns_3}} |

### What Is at Stake

**Upside scenario (6 months):** {{upside_scenario}}

**Downside scenario (6 months):** {{downside_scenario}}

**Status quo cost:** {{status_quo_cost}}

### Known Constraints
- {{constraint_1}}
- {{constraint_2}}
- {{constraint_3}}

---

## 3. Risk Register

### Summary Table

| ID | Title | Category | Severity | Likelihood | Score | Mitigation |
|----|-------|----------|----------|------------|-------|------------|
| {{risk_id}} | {{risk_title}} | CX / Tech / Business / Ops / Rep / Legal | Critical / High / Medium / Low | Almost Certain / Likely / Possible / Unlikely | {{score}} | {{mitigation_summary}} |

### Detailed Risk Cards

#### {{risk_id}}: {{risk_title}}

**Category:** {{risk_category}}
**Severity:** {{severity}} | **Likelihood:** {{likelihood}}
**Description:** {{risk_description}}
**Trigger conditions:** {{trigger_conditions}}
**Impact if materialised:** {{impact_description}}
**Proposed mitigation:** {{mitigation_detail}}
**Residual risk after mitigation:** {{residual_risk}}
**Interdependencies:** {{risk_interdependencies}}

---

## 4. Customer FAQ

*{{total_customer_questions}} questions across {{theme_count}} themes. Highest-pushback topics: {{high_pushback_topics}}.*

### Understanding the Change

**Q: {{customer_q1}}**
A: {{customer_a1}}

### Personal Impact

**Q: {{customer_q2}}**
A: {{customer_a2}}

### Transition and Support

**Q: {{customer_q3}}**
A: {{customer_a3}}

### Alternatives and Opt-Out

**Q: {{customer_q4}}**
A: {{customer_a4}}

### Tough Questions

**Q: {{customer_q5}}**
A: {{customer_a5}}

---

## 5. Internal FAQ

*{{total_internal_questions}} questions across {{internal_theme_count}} themes.*

### Strategic Rationale

**Q: {{internal_q1}}**
A: {{internal_a1}}

### Resource and Impact

**Q: {{internal_q2}}**
A: {{internal_a2}}

### Risk and Contingency

**Q: {{internal_q3}}**
A: {{internal_a3}}

### Customer and Market Impact

**Q: {{internal_q4}}**
A: {{internal_a4}}

### Devil's Advocate

**Q: {{internal_q5}}**
A: {{internal_a5}}

---

## 6. Counter-Arguments

### Risk Counter-Arguments

#### {{risk_title}}

**Objection (steel-manned):** {{steel_manned_objection}}

**Counter-argument:** {{counter_argument}}

**Evidence:** {{supporting_evidence}}

**Residual risk:** {{residual_risk_after_counter}}

**Confidence in this counter-argument:** High / Medium / Low

### Hostile Question Responses

#### "{{hostile_question}}"

**Stress-tested response:** {{stress_tested_response}}

**Follow-up risk:** {{likely_follow_up_and_response}}

---

## 7. Unresolved Concerns

| # | Concern | Classification | What Would Resolve It |
|---|---------|---------------|----------------------|
| 1 | {{concern_1}} | Blocking / Significant / Minor | {{resolution_path_1}} |
| 2 | {{concern_2}} | Blocking / Significant / Minor | {{resolution_path_2}} |
| 3 | {{concern_3}} | Blocking / Significant / Minor | {{resolution_path_3}} |

---

## 8. Decision Recommendation

**Recommendation:** Proceed / Proceed with modifications / Defer / Do not proceed

**Rationale:**
{{detailed_rationale}}

**Conditions (if recommending proceed):**
1. {{condition_1}}
2. {{condition_2}}

**Next steps:**
1. {{next_step_1}} — Owner: {{owner_1}} — By: {{deadline_1}}
2. {{next_step_2}} — Owner: {{owner_2}} — By: {{deadline_2}}

**Review date:** {{review_date}}

---

*This RFAQ was prepared by {{author_name}} on {{date}}. It should be reviewed and updated if material new information emerges before the decision deadline.*
