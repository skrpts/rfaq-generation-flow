---
type: asset
id: risk-register-template
title: Risk Register Template
description: "Template for cataloguing and tracking identified risks with severity, likelihood, and mitigation status"
tags: [Production, Customer-Facing]
connections: []
metadata:
  asset_type: "template"
  format: "markdown"
---

## Risk Register Template

### Register Metadata

- **Product/Decision:** {{product_or_decision_name}}
- **Owner:** {{risk_register_owner}}
- **Created:** {{creation_date}}
- **Last updated:** {{last_updated}}
- **Review cadence:** Weekly / Bi-weekly / Monthly

---

### Risk Summary Dashboard

| Severity | Count | Trend |
|----------|-------|-------|
| Critical | {{critical_count}} | Increasing / Stable / Decreasing |
| High | {{high_count}} | Increasing / Stable / Decreasing |
| Medium | {{medium_count}} | Increasing / Stable / Decreasing |
| Low | {{low_count}} | Increasing / Stable / Decreasing |
| **Total** | **{{total_count}}** | |

---

### Risk Register

| ID | Title | Category | Severity | Likelihood | Score | Owner | Status | Last Reviewed |
|----|-------|----------|----------|------------|-------|-------|--------|---------------|
| CX-1 | {{risk_title}} | Customer Experience | Critical / High / Medium / Low | Almost Certain / Likely / Possible / Unlikely | {{score}} | {{owner}} | Open / Mitigating / Monitoring / Closed | {{date}} |
| TECH-1 | {{risk_title}} | Technical | Critical / High / Medium / Low | Almost Certain / Likely / Possible / Unlikely | {{score}} | {{owner}} | Open / Mitigating / Monitoring / Closed | {{date}} |
| BUS-1 | {{risk_title}} | Business | Critical / High / Medium / Low | Almost Certain / Likely / Possible / Unlikely | {{score}} | {{owner}} | Open / Mitigating / Monitoring / Closed | {{date}} |
| OPS-1 | {{risk_title}} | Operational | Critical / High / Medium / Low | Almost Certain / Likely / Possible / Unlikely | {{score}} | {{owner}} | Open / Mitigating / Monitoring / Closed | {{date}} |
| REP-1 | {{risk_title}} | Reputational | Critical / High / Medium / Low | Almost Certain / Likely / Possible / Unlikely | {{score}} | {{owner}} | Open / Mitigating / Monitoring / Closed | {{date}} |
| LEG-1 | {{risk_title}} | Legal/Compliance | Critical / High / Medium / Low | Almost Certain / Likely / Possible / Unlikely | {{score}} | {{owner}} | Open / Mitigating / Monitoring / Closed | {{date}} |

---

### Risk Scoring Matrix

|  | **Almost Certain** | **Likely** | **Possible** | **Unlikely** |
|---|---|---|---|---|
| **Critical** | Extreme (20) | Very High (16) | High (12) | Medium (8) |
| **High** | Very High (15) | High (12) | Medium (9) | Low (6) |
| **Medium** | High (10) | Medium (8) | Medium (6) | Low (4) |
| **Low** | Medium (5) | Low (4) | Low (3) | Low (2) |

---

### Detailed Risk Cards

#### {{risk_id}}: {{risk_title}}

**Category:** {{category}}
**Date identified:** {{identified_date}}
**Identified by:** {{identified_by}}
**Owner:** {{risk_owner}}
**Status:** Open / Mitigating / Monitoring / Closed

**Description:**
{{risk_description}}

**Trigger conditions:**
{{what_would_cause_this_risk_to_materialise}}

**Impact if materialised:**
{{impact_description_with_quantification}}

**Severity:** Critical / High / Medium / Low
**Likelihood:** Almost Certain / Likely / Possible / Unlikely
**Risk score:** {{score}}

**Mitigation plan:**
1. {{mitigation_action_1}} — Owner: {{action_owner_1}} — Due: {{due_date_1}} — Status: Not started / In progress / Complete
2. {{mitigation_action_2}} — Owner: {{action_owner_2}} — Due: {{due_date_2}} — Status: Not started / In progress / Complete

**Residual risk after mitigation:**
{{residual_risk_description}}

**Monitoring indicators:**
- {{indicator_1}} — checked {{frequency}}
- {{indicator_2}} — checked {{frequency}}

**Interdependencies:**
- Triggers: {{risks_this_could_trigger}}
- Triggered by: {{risks_that_could_trigger_this}}

**Review history:**
| Date | Reviewer | Change | Notes |
|------|----------|--------|-------|
| {{date}} | {{reviewer}} | Severity changed from X to Y | {{notes}} |

---

### Risk Closure Log

| ID | Title | Closed Date | Reason | Outcome |
|----|-------|-------------|--------|---------|
| {{risk_id}} | {{risk_title}} | {{closure_date}} | Mitigated / Accepted / No longer relevant | {{outcome_notes}} |

---

### Risk Review Notes

**Review date:** {{review_date}}
**Attendees:** {{attendees}}

**New risks identified:**
- {{new_risk_summary}}

**Risks escalated:**
- {{escalated_risk}} — reason: {{escalation_reason}}

**Risks de-escalated or closed:**
- {{closed_risk}} — reason: {{closure_reason}}

**Actions from this review:**
1. {{action_1}} — Owner: {{owner}} — Due: {{date}}

**Next review:** {{next_review_date}}
