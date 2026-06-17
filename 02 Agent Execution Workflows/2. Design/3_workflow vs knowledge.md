# Workflow vs. Knowledge

## Background

Subproject 01 focused on transforming human-oriented documentation into structured, agent-ready knowledge.

Subproject 02 introduces execution workflows that guide agent behavior.

At first glance, these concepts can appear similar.

Both contain information.
Both influence agent decisions.
Both help improve reliability.

However, they solve fundamentally different problems.

Understanding the distinction between knowledge and workflows is essential when designing AI-first systems.

---

## Knowledge Defines Facts

Knowledge represents information that an agent needs to understand.

Examples include:

* Business policies
* Product information
* Rules and constraints
* Definitions and procedures
* Eligibility requirements

Knowledge answers questions such as:

* What is true?
* What rules exist?
* What constraints apply?
* What information should be considered?

For example:

```text id="2t4r9o"
Orders may be cancelled within 30 minutes of placement.
```

This statement communicates a business rule.

It does not define how an agent should execute a cancellation request.

---

## Workflows Define Behavior

Execution workflows represent the actions and decisions an agent should follow while performing a task.

Workflows answer questions such as:

* What should happen first?
* What information is required?
* Which decision should be made next?
* What action should follow?
* When should the workflow end?
* When should escalation occur?

For example:

```text id="qfy0tm"
1. Request order number
2. Retrieve order details
3. Calculate elapsed time
4. Determine cancellation eligibility
5. If eligible, cancel the order
6. Otherwise, explain the policy
7. Escalate exceptions
```

This defines a process rather than a fact.

---

## Example

### Knowledge

```text id="f9vtlb"
Refunds are allowed within 30 days of purchase.
```

### Workflow

```text id="0m4qtk"
Collect purchase information.
Determine purchase date.
Calculate elapsed time.
Evaluate refund eligibility.
Approve, deny, or escalate.
```

The knowledge explains the rule.

The workflow explains what the agent should do.

---

## Why Knowledge Alone Is Not Enough

An agent may successfully retrieve information and still behave incorrectly.

For example:

Knowledge:

```text id="vcz9mz"
Refunds are allowed within 30 days of purchase.
```

Possible agent behaviors:

### Agent A

Approves the refund immediately.

### Agent B

Requests unnecessary information.

### Agent C

Refuses the refund without checking eligibility.

### Agent D

Escalates every request.

All agents had access to the same knowledge.

The inconsistency exists because the workflow was never defined.

---

## Why Workflows Alone Are Not Enough

Workflows also depend on knowledge.

Consider this instruction:

```text id="em86es"
Determine refund eligibility.
```

The workflow says what action should happen.

But it does not define:

* What makes a refund eligible
* Which policies apply
* What exceptions exist

The workflow still needs knowledge.

Without knowledge:

* Decisions become arbitrary
* Rules become hardcoded
* Processes become difficult to maintain

---

## How Knowledge and Workflows Work Together

At a high level:

```text id="v8mzlr"
Knowledge
    ↓
Provides facts and rules
    ↓
Execution Workflow
    ↓
Determines actions and decisions
    ↓
Agent Behavior
```

The relationship can be summarized as:

```text id="rbz07q"
Knowledge → What is true
Workflow → What should happen next
```

Both layers are required.

---

## Responsibilities of Each Layer

| Responsibility              | Knowledge | Workflow |
| --------------------------- | --------- | -------- |
| Business rules              | ✓         |          |
| Definitions and constraints | ✓         |          |
| Required actions            |           | ✓        |
| Decision sequence           |           | ✓        |
| Workflow states             |           | ✓        |
| Escalation paths            |           | ✓        |
| Eligibility criteria        | ✓         |          |
| Execution order             |           | ✓        |

---

## System Perspective

An AI-first system typically requires both layers.

### Knowledge Layer

Provides:

* Facts
* Policies
* Constraints
* Definitions

### Workflow Layer

Provides:

* Decisions
* State transitions
* Actions
* Process control
* Exception handling

Together, they enable agents to:

* Retrieve information correctly
* Follow approved processes
* Make consistent decisions
* Produce reliable outcomes

---

## Key Takeaway

Knowledge and execution workflows are complementary assets.

Knowledge helps agents understand.

Workflows help agents act.

Neither layer can fully replace the other.

Reliable AI systems require both:

```text id="0ezggr"
Knowledge
        +
Execution Workflows
        ↓
Governed Agent Behavior
```

---

## Next step within this subproject

The next step is to examine common workflow patterns that frequently appear in AI agent systems and how these patterns can be represented as reusable workflow structures.

That will live in:

`workflow_design/workflow_patterns.md`
