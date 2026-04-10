# Demo & Walkthrough: Agent-Ready Knowledge Base

## Purpose of this demo

This document walks you through the system for demos, stakeholder reviews, and a quick overview of how a traditional help article is structured into knowledge an AI agent can use reliably.

The goal is to show:
- Why human documentation fails for AI systems
- How restructuring content improves reliability
- How knowledge can be evaluated as a system component

---

## Suggested demo flow (2–3 minutes)

### 1. Start with the problem (30–40 seconds)

Show:
`content/human_docs/original_help_article.md`

Explain:

- This is a typical help center article
- Written for humans → assumes context and interpretation
- Works well for reading, but not for AI execution

Call out examples:
- “Only account owners can cancel” → not enforced
- Refund policy → buried in text
- Steps → lack validation or conditions

👉 Key point to emphasise:
> “This looks correct to a human, but an AI agent can easily misinterpret or skip critical logic.”

---

### 2. Show the transformed version (60–70 seconds)

Show:
`content/agent_ready/knowledge_units.json`

Explain how the same content is now:

- Structured into a **knowledge unit**
- Explicitly defines:
  - Preconditions
  - Steps
  - Decision rules
  - Constraints
  - Escalation

Highlight:

- Decision rules (trial vs paid)
- Constraints (refund policy)
- Risk + governance (not present before)

👉 Key pointer:
> “Instead of relying on the model to infer logic, we encode that logic directly into the content.”

---

### 3. Explain the schema briefly (30–40 seconds)

Show:
`schemas/knowledge_unit_schema.yaml`

Explain:

- This defines what “good knowledge” looks like
- Ensures consistency across all content
- Makes knowledge testable and reusable

👉 Key pointer:
> “This is similar to how APIs use schemas, just that here we’re doing it for content.”

---

### 4. Show evaluation (30–40 seconds)

Show:
`evaluation/sample_evaluation.json`

Explain:

- Content is evaluated regularly on various dimensions and scored on a scale of 1-5
- Each of the following dimensions are scored:
  - Accuracy
  - Completeness
  - Consistency
  - Clarity
  - Safety

👉 Key pointer:
> “In AI systems, content quality directly impacts system behavior, so it needs to be measurable.”

---

### 5. Close with impact (20–30 seconds)

Summarize:

- We moved from:
  - Static documentation
- To:
  - Structured, testable, agent-consumable knowledge

👉 Key pointer:
> “This is the foundation required before you can build reliable agent workflows or tool-using systems.”

---

## What this demo proves

This subproject demonstrates:

- Understanding of AI system behavior
- Ability to design structured knowledge
- Awareness of failure modes
- Product thinking applied to content systems

---
