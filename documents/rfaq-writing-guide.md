---
type: document
id: rfaq-writing-guide
title: RFAQ Writing Guide
description: "Detailed guide to writing effective RFAQ documents with best practices, examples, and quality criteria"
tags: [Production, Customer-Facing]
connections:
  - target: rfaq-methodology-reference
    type: references
metadata:
  document_type: "guide"
  last_updated: "2026-03-10"
---

## RFAQ Writing Guide

### Before You Start

#### Define the Decision Clearly

The most common failure in RFAQ writing is starting with a vague decision. "Should we improve our mobile app?" is not a decision — it is a general aspiration. "Should we invest 4 engineering months to rebuild the mobile checkout flow using native components, replacing the current WebView implementation, targeting a 30% reduction in checkout abandonment?" is a decision.

Before writing, answer these questions:
- What specifically are we deciding to do (or not do)?
- What are the alternatives we are choosing between?
- Who has the authority to make this decision?
- By when must the decision be made?
- What happens if we decide to do nothing?

#### Gather Your Inputs

A well-written RFAQ requires:
- Customer data (usage analytics, survey results, support ticket analysis, churn data)
- Market context (competitive landscape, market trends, regulatory environment)
- Technical assessment (feasibility, architecture implications, technical debt impact)
- Financial projections (cost, expected revenue impact, ROI timeline)
- Stakeholder perspectives (who has expressed views, what are their concerns)

Do not start writing until you have these inputs. An RFAQ built on assumptions rather than evidence is a work of fiction.

### Writing the Risk Register

#### How to Identify Risks

**Structured brainstorming:** Work through each risk category systematically (customer experience, technical, business, operational, reputational, legal). For each category, ask: "What could go wrong in this area? What are we assuming will go right?"

**Pre-mortem exercise:** Imagine it is 12 months from now and the decision has failed catastrophically. Write a paragraph describing what happened. Then extract the specific risks from that narrative.

**Stakeholder interviews:** Ask 3-5 stakeholders (ideally including sceptics) what concerns them about this decision. People who are nervous about a decision often have genuine insights about risks that supporters overlook.

**Historical analogy:** Has the company (or a competitor) made a similar decision before? What went wrong? What went right? What was unexpected?

#### How to Rate Risks

Use a consistent severity scale:
- **Critical:** Threatens the viability of the product, the company's reputation, or legal standing. Requires executive attention.
- **High:** Threatens key business outcomes (revenue targets, customer retention, market position). Requires a mitigation plan.
- **Medium:** Could delay timelines, increase costs, or reduce the impact of the initiative. Should be monitored.
- **Low:** Minor inconvenience or easily managed. Note and move on.

Use a consistent likelihood scale:
- **Almost Certain (>90%):** This will probably happen unless we actively prevent it
- **Likely (60-90%):** More likely than not to occur
- **Possible (30-60%):** Could go either way
- **Unlikely (<30%):** Possible but would require unusual circumstances

#### Common Risk-Writing Mistakes

- **Vague risks:** "Performance might be a problem" — what performance, under what conditions, with what impact?
- **Risks as facts:** "The migration will fail" is not a risk; it is a prediction. Reframe as "There is a risk that the data migration encounters schema incompatibilities that require manual intervention for approximately 15% of records."
- **Risks without impact:** Every risk should include what happens if it materialises. A risk without an impact statement is a concern without context.

### Writing FAQs

#### The Art of Question Anticipation

Good FAQ writers think like their audience, not like themselves. A product manager's instinct is to explain why the decision is correct. A customer's instinct is to ask how the decision affects them. Start with the audience's perspective.

**The "first five minutes" test:** Imagine a customer reads the announcement in a Slack channel, a newsletter, or a pop-up in the app. What do they think in the first five minutes? What questions form immediately?

**The "dinner table" test:** If you had to explain this decision to a non-technical friend at dinner, what questions would they ask? These are often the most fundamental and the easiest to overlook.

**The "angry customer" test:** Imagine your most vocal, most demanding customer reads the announcement. What do they say in the support ticket they file five minutes later?

#### Answer Quality Checklist

For each FAQ answer, verify:
- [ ] Does it actually answer the question asked (not a related but different question)?
- [ ] Is it specific enough to be useful (not vague corporate-speak)?
- [ ] Is it honest (not misleading, even by omission)?
- [ ] Does it acknowledge the concern before addressing it?
- [ ] Does it end with a clear next step or expectation?
- [ ] Would you feel respected if you received this answer?

### Writing Counter-Arguments

#### The Steel Man Rule

Before countering an objection, make it stronger. If someone says "this will confuse customers," do not start with "no it won't." Start with: "The strongest version of this concern is that we are fundamentally changing an interaction pattern that 80% of our users rely on daily, and the research on interface change resistance suggests a 15-30% temporary productivity loss during transition."

Then counter: "This concern is valid. However, our data shows that the current interface is the primary driver of new-user abandonment, which costs us 200 sign-ups per month. We are mitigating the transition cost with..."

This approach is more persuasive because it demonstrates that you have genuinely considered the objection rather than dismissing it.

#### When You Cannot Counter an Argument

Sometimes the counter-argument is simply not strong enough. When this happens:

- Say so explicitly: "We do not have an adequate response to this concern at present."
- Classify the concern as blocking or non-blocking
- Specify what would be needed to resolve it: "This concern could be addressed with a two-week customer research sprint to validate the assumption about user willingness to migrate."

An RFAQ that honestly identifies its own weaknesses is far more trustworthy than one that pretends to have all the answers.

### Quality Criteria

A complete RFAQ should satisfy:

| Criterion | Test |
|-----------|------|
| Completeness | Does it cover all six risk categories? Does the FAQ include hostile questions? |
| Honesty | Is the "Unresolved Concerns" section genuinely populated? |
| Evidence | Are risk assessments and counter-arguments backed by data, not just opinion? |
| Consistency | Do the risk register, FAQs, and recommendation tell a coherent story? |
| Actionability | Does the recommendation include clear next steps and conditions? |
| Audience awareness | Are customer FAQs written in the customer's voice? Are internal FAQs appropriately detailed? |
