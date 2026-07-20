# The Knowledge-to-Action Gap

## Background

Subproject 01 demonstrated how human-oriented documentation can be transformed into structured, agent-ready knowledge.

The resulting knowledge is:

* Explicit
* Modular
* Consistent
* Machine-readable
* Independently evaluable

This significantly improves an agent's ability to retrieve information and reason about business rules.

However, another challenge remains.

**Knowing something is not the same as knowing what to do next.**

---

## The Gap

Consider the following knowledge:

```text
Orders may be cancelled within 30 minutes of placement.
```

An AI agent may successfully retrieve this information.

But successfully retrieving the information does not automatically tell the agent:

* What information should be collected
* Which checks must happen first
* How to determine eligibility
* What action should be taken next
* When the workflow should stop
* When escalation is required

The knowledge explains a rule.

It does not define a process.

---

## Why This Matters

Human employees naturally fill these gaps.

A customer support representative reading the same policy might instinctively:

1. Ask for the order number
2. Retrieve order details
3. Check order status
4. Calculate elapsed time
5. Verify cancellation eligibility
6. Process the cancellation
7. Explain the outcome to the customer

Years of experience and organizational context help humans infer these steps.

AI agents cannot reliably make these assumptions.

Without explicit guidance, different agents may interpret the same knowledge differently.

---

## Example

### Available Knowledge

```text
Orders can be cancelled within 30 minutes of placement.
```

### Agent A

* Asks for order number
* Checks timestamp
* Cancels order

### Agent B

* Immediately attempts cancellation

### Agent C

* Asks unnecessary questions
* Transfers to support

### Agent D

* Refuses cancellation because eligibility checks were skipped

Each agent had access to the same knowledge.

Each produced different behavior.

The problem is not knowledge retrieval.

The problem is the absence of an explicit execution workflow.

---

## Why Prompting Alone Is Not Enough

A common assumption is that prompts can solve this problem.

For example:

```text
Use the company's cancellation policy and assist the customer.
```

This approach often produces inconsistent behavior because:

* Prompts rely heavily on model interpretation
* Execution steps remain implicit
* Small wording changes can alter decisions
* Business rules become difficult to govern
* Workflow behavior becomes difficult to test

As systems grow more complex, relying solely on prompts introduces operational risk.

Organizations need behavior that is:

* Predictable
* Repeatable
* Governable
* Evaluable

Prompt improvisation alone cannot guarantee these properties.

---

## The Missing Layer

Between knowledge and execution, agents require an operational layer that explicitly defines:

* Required inputs
* Workflow states
* Decision points
* Actions
* Exit conditions
* Escalation paths
* Exception handling rules

At a high level:

```text
Knowledge
    ↓
Execution Workflow
    ↓
Agent Actions
```

Knowledge answers:

> What is true?

Execution workflows answer:

> What should happen next?

Both layers are necessary.

---

## Problem Statement

AI-first systems increasingly rely on structured knowledge to improve retrieval and reasoning.

However, structured knowledge alone does not guarantee reliable execution.

Without explicit workflow definitions:

* Agents may skip important steps
* Different agents may make different decisions
* Business processes become difficult to govern
* Operational behavior becomes difficult to evaluate
* Scaling agent-based systems becomes increasingly risky

The challenge addressed in this subproject is:

**How can business processes be represented as structured execution workflows that enable AI agents to consistently perform approved actions while remaining testable, measurable, and governed?**

---

## Objective of This Subproject

This subproject explores how to transform operational processes into structured execution workflows that:

* Guide agent decision-making
* Define explicit sequences of actions
* Capture business process logic
* Support exception handling
* Enable workflow evaluation and governance
* Produce reliable and repeatable agent behavior

The resulting workflows become an operational layer that bridges the gap between structured knowledge and real-world agent execution.

---

## Next step within this subproject

The next step is to define what an execution workflow is and identify the characteristics that make workflows reliably consumable by AI agents.

That will live in:

`workflow_design/what_is_an_execution_workflow.md`
