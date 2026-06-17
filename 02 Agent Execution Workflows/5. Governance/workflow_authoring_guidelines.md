# Workflow Authoring Guidelines

## Purpose

Execution workflows become operational knowledge assets that directly influence AI agent behavior.

Poorly designed workflows can lead to:

* Inconsistent agent decisions
* Missing information collection
* Incorrect actions
* Difficult-to-govern processes
* Unreliable evaluation results

To reduce these risks, workflows should follow a consistent authoring approach.

---

## Guiding Principles

### Make workflow goals explicit

Every workflow should clearly state:

* Why the workflow exists
* What business outcome it supports
* What successful completion looks like

Workflow goals should be understandable without reading implementation details.

---

### Define required information explicitly

Required inputs should always be documented.

For example:

* Order number
* Customer identifier
* Purchase date

Avoid relying on assumptions or hidden context.

Agents should know exactly which information is required before decisions are made.

---

### Represent decisions explicitly

Decision-making should never depend on interpretation.

Avoid:

```text
Verify eligibility.
```

Prefer:

```text
Check purchase date.
Determine whether the purchase occurred within 30 days.
Approve or deny the request.
```

Decision logic should be visible and testable.

---

### Use meaningful workflow states

Workflow states should describe business activities.

Examples:

* Collect Information
* Evaluate Eligibility
* Process Request
* Escalate
* Complete Workflow

Avoid vague state names such as:

* Step 1
* Process Data
* Continue

States should communicate business intent.

---

### Define completion conditions

Every workflow should have clearly defined outcomes.

Examples:

* Completed
* Denied
* Escalated
* Failed

Agents should always know when workflow execution has ended.

---

### Include exception paths

Real processes contain exceptions.

Examples:

* Missing information
* Policy exceptions
* System failures
* Human approval requirements

Exception handling should be designed intentionally rather than left to agent interpretation.

---

## Authoring Recommendations

Workflows should be:

* Explicit
* Modular
* Deterministic
* Reusable
* Governable
* Evaluable

Workflow definitions should prioritize clarity over complexity.

---

## Review Checklist

Before publishing a workflow, verify that:

* Workflow goals are defined
* Required inputs are documented
* Decision rules are explicit
* State transitions are clear
* Completion conditions exist
* Exception handling is represented
* Workflow terminology is consistent

Following these guidelines improves workflow quality and supports more reliable agent behavior.

---

## Next step within this subproject

The next step is to define how workflows should evolve while maintaining consistency and governance.

That will live in:

`governance/workflow_versioning.md`
