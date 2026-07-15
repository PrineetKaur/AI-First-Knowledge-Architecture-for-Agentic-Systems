# Demo & Walkthrough: Agent Execution Workflows

## Purpose of this demo

This document walks you through how structured knowledge is transformed into execution workflows that AI agents can follow consistently.

The goal is to show:

- Why structured knowledge alone is not sufficient
- How execution workflows guide agent behavior
- How workflows can be designed, governed, and evaluated as reusable knowledge assets

---

## Suggested demo flow (2–3 minutes)

### 1. Start with the problem (30–40 seconds)

Show:

`problem/knowledge_to_action_gap.md`

Explain:

- Structured knowledge tells an AI agent **what is true**
- It does not tell the agent **what should happen next**
- Without workflows, agents may perform the same task differently

Give a simple example:

Knowledge:

> Refunds are allowed within 30 days.

Possible agent behavior:

- One agent approves immediately
- Another asks unnecessary questions
- Another escalates every request

👉 **Key point to emphasise:**

> "Knowledge provides facts. Workflows provide the process for acting on those facts."

---

### 2. Explain workflow design (40–50 seconds)

Show:

`design/workflow_principles.md`

Explain:

Execution workflows are designed to make agent behavior:

- Explicit
- Consistent
- Reusable
- Governable

Highlight principles such as:

- Explicit decision rules
- Defined inputs
- Clear state transitions
- Exception handling

👉 **Key pointer:**

> "Instead of expecting the AI model to infer the process, we explicitly define the process."

---

### 3. Show the workflow schema (30–40 seconds)

Show:

`schemas/agent_execution_workflow_schema.yaml`

Explain:

- The schema provides a standard structure for authoring workflows
- Every workflow follows the same format
- Consistency makes workflows easier to review, reuse, and govern

👉 **Key pointer:**

> "Just as schemas standardize knowledge, they can also standardize agent behavior."

---

### 4. Walk through a workflow example (40–50 seconds)

Show:

`workflows/refund_workflow.yaml`

Explain how the workflow defines:

- Required inputs
- Workflow states
- Decision rules
- State transitions
- Possible outcomes

Highlight that:

- Business logic is represented explicitly
- Decision-making is no longer hidden inside prompts

👉 **Key pointer:**

> "The workflow becomes a reusable operational asset rather than prompt-specific logic."

---

### 5. Show governance and evaluation (30–40 seconds)

Show:

`governance/workflow_authoring_guidelines.md`

Then show:

`evaluation/sample_evaluation.json`

Explain:

- Workflows are reviewed using defined quality metrics
- Governance ensures consistency across authors and teams
- Evaluation helps identify opportunities for improvement before workflows are deployed

👉 **Key pointer:**

> "Execution workflows should be treated as governed knowledge assets, not one-off prompt instructions."

---

### 6. Close with impact (20–30 seconds)

Summarize:

We moved from:

- Structured knowledge

To:

- Structured agent behavior

The result is:

- More consistent decisions
- Reusable workflow definitions
- Better governance
- Easier evaluation
- Improved reliability across AI systems

👉 **Key pointer:**

> "Once knowledge and workflows are both structured, organizations can begin treating AI behavior as a system that can be designed, governed, and continuously improved."

---

## What this demo proves

This subproject demonstrates:

- Understanding of workflow-driven AI systems
- Ability to model business processes as structured workflow assets
- Knowledge architecture beyond static documentation
- Governance thinking for AI-first content systems
- Knowledge architecture applied to agent workflows
