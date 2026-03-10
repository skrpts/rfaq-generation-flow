---
type: skill
id: faq-anticipation
title: FAQ Anticipation
description: "Anticipating likely questions from customers, stakeholders, and internal teams about product decisions"
tags: [Production, Tested]
connections:
  - target: claude-service
    type: runs_on
metadata:
  estimated_duration: "5-8 minutes"
  avg_tokens: 2500
  trigger: manual
---

## FAQ Anticipation

This skill enables the systematic anticipation of questions that different audiences will ask about a product decision, feature change, or announcement. Effective FAQ anticipation goes beyond obvious questions to surface the uncomfortable, sceptical, and adversarial questions that catch teams off guard.

### Core Capabilities

#### Question Generation by Audience

Different audiences ask different questions from different motivations:

**Customers ask about impact:**
- "How does this affect me?" — the fundamental customer question
- "Do I need to do anything?" — action requirements
- "When does this happen?" — timeline and planning
- "How much does this cost?" — pricing and value impact
- "What if I don't like it?" — opt-out and alternatives
- "Why should I trust you?" — track record and commitment

**Executives ask about strategy:**
- "Why now?" — timing and opportunity cost
- "What's the expected return?" — business case and metrics
- "What are we not doing because of this?" — trade-offs and opportunity cost
- "How does this compare to what competitors are doing?" — competitive positioning
- "What's the rollback plan?" — risk management

**Engineering asks about feasibility:**
- "How will this scale?" — architecture and performance
- "What are the technical dependencies?" — implementation complexity
- "How will we test this?" — quality assurance
- "What's the migration path?" — transition mechanics
- "What happens to the existing system?" — deprecation and tech debt

**Sales and Customer Success ask about positioning:**
- "How do I explain this to prospects?" — messaging and value proposition
- "Will this affect my pipeline?" — deal impact
- "What do I tell customers who are upset?" — objection handling
- "Is there a competitive advantage here?" — differentiation
- "When will my customers see this?" — rollout timeline

**Legal and Compliance ask about risk:**
- "Does this change our data handling?" — privacy and security
- "Are there regulatory implications?" — compliance
- "Does this affect existing contracts?" — contractual obligations
- "What's our liability exposure?" — legal risk

#### The Hostile Question Technique

Beyond anticipated questions, deliberately generate hostile questions — the ones asked by sceptical journalists, angry customers, or adversarial board members:

1. **The "so what" question:** "You say this improves performance by 20%. Why should I care?"
2. **The "who loses" question:** "Who is worse off because of this decision?"
3. **The precedent question:** "Last time you made a change like this, it went badly. Why is this different?"
4. **The motive question:** "Is this really for customers, or is this for your revenue targets?"
5. **The comparison question:** "Competitor X does this better/cheaper/faster. Why should I stay?"
6. **The trust question:** "You promised X last year and didn't deliver. Why should I believe you now?"

These questions are uncomfortable but invaluable. A team that has prepared for hostile questions will handle real-world pushback with confidence.

#### Answer Crafting Principles

When drafting answers to anticipated questions:

- **Lead with empathy:** Acknowledge the concern before addressing it. "We understand this change affects your workflow" before "Here's why we're making it."
- **Be specific:** Vague answers erode trust. "We're working on it" is not an answer. "We expect to resolve this by 15 April, and in the meantime, here is a workaround" is an answer.
- **Be honest about limitations:** "We don't have a perfect solution for this yet, but here is what we're doing" is far more credible than "Don't worry, everything is fine."
- **Provide a next step:** Every answer should end with what the questioner should do, expect, or watch for.
- **Avoid corporate-speak:** Real questions deserve real answers, not jargon-laden deflections.

### Constraints

- Generate at least 10 customer-facing questions and 8 internal questions for any significant decision
- Always include at least 3 hostile questions per audience segment
- Never draft answers that contain falsehoods, even comfortable ones
- Flag any question where the honest answer is "we don't know yet" — this is valuable information for the team
- Distinguish between questions that need a public-facing answer and those that need an internal response only
