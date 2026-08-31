# Knowledge Operations Demo

## Purpose

This demo demonstrates the Knowledge Operations lifecycle using the existing refund example established in the previous subprojects.

The scenario shows how a business policy change moves through:

```text
    Change Intake
          ↓
Impact Identification
          ↓
      Authoring
          ↓
       Review
          ↓
 Quality Evaluation
          ↓
      Approval
          ↓
     Publishing
          ↓
     Maintenance
          ↓
     Retirement
```

The demo reuses the existing:

* Refund Knowledge Unit
* Refund Execution Workflow
* Quality Assessment

No new knowledge representation is introduced.

---

## Scenario

The organization previously maintained the following refund policy:

```text
Customers may receive a refund within 30 days of purchase
if payment has been successfully captured and no shipment has occurred.
```

The policy is represented through the existing knowledge architecture.

```text
Refund Policy
     │
     ├── Refund Knowledge Unit
     ├── Refund Execution Workflow
     └── Quality Assessment
```

The business subsequently changes the refund eligibility period from **30 days to 60 days**.

This change triggers a Knowledge Operations lifecycle.

---

## Step 1: Change Intake

The policy change is registered as a knowledge operation.

```yaml
knowledge_operation:
  operation_id: "KO-REFUND-001"

  change:
    trigger: "policy_change"
    reason: "Refund eligibility period changed from 30 days to 60 days"
```

The operation identifies the business change that initiated the lifecycle.

### State

```text
Draft
```

---

## Step 2: Impact Identification

The organization identifies the assets potentially affected by the change.

```text
Policy Change
     │
     ├── KU-REFUND-001
     │   Refund Knowledge Unit
     │
     ├── WF-REFUND-001
     │   Refund Execution Workflow
     │
     └── Related supporting knowledge
```

This prevents the organization from updating only the primary policy while leaving dependent assets unchanged.

### State

```text
Draft
```

---

## Step 3: Authoring

The refund Knowledge Unit is updated.

### Previous Knowledge

```text
Refund eligibility period: 30 days
```

### Updated Knowledge

```text
Refund eligibility period: 60 days
```

The corresponding execution workflow is also reviewed and updated where the policy change affects its decision logic.

### State

```text
Draft
```

---

## Step 4: Review

The updated assets are submitted for review.

```yaml
ownership:
  owner: "Customer Operations"
  reviewer: "Support Operations"
```

The reviewer verifies that the updated knowledge reflects the new business policy.

### State

```text
In Review
```

---

## Step 5: Quality Evaluation

The updated Knowledge Unit and affected workflow are evaluated using the quality framework established in Subproject 03.

```yaml
quality:
  assessment_id: "QA-REFUND-001"
  status: "passed"
```

The quality evaluation confirms that the updated assets continue to meet the required quality and governance criteria.

### State

```text
Evaluated
```

If the evaluation fails, the assets return to authoring or review.

```text
Quality Evaluation
       │
       ├── Pass → Approval
       │
       └── Fail → Revision
```

---

## Step 6: Approval

The updated assets are approved by the authorized owner.

```yaml
ownership:
  approver: "Customer Operations Lead"
```

The approved version is:

```text
Version: 2.0
```

The previous version remains identifiable:

```text
Previous Version: 1.0
Current Version:  2.0
```

### State

```text
Approved
```

---

## Step 7: Publishing

The approved version becomes the active version.

```yaml
version:
  current: "2.0"
  previous: "1.0"

publication:
  status: "published"
```

The new policy is now:

```text
Customers may receive a refund within 60 days of purchase
if payment has been successfully captured and no shipment has occurred.
```

### State

```text
Published
```

The previous version is retained for traceability but is no longer the active version.

---

## Step 8: Maintenance

The knowledge asset remains under operational management after publication.

A future review date is recorded:

```yaml
review:
  next_review_date: "2027-01-15"
```

Future changes can re-enter the same lifecycle.

```text
          Published
              ↓
       Business Change
              ↓
       Change Intake
              ↓
Knowledge Operations Lifecycle
```

### State

```text
Maintenance
```

---

## Step 9: Retirement

When a knowledge asset is no longer valid, it can be retired.

For example, when Version 2.0 is eventually replaced:

```text
Version 2.0
    ↓
Retired
```

The historical record remains available for traceability while the retired version is removed from active use.

### State

```text
Retired
```

---

# Complete Lifecycle

The complete demonstration can be summarized as:

```text
     Policy Change
          │
          ▼
    Change Intake
          │
          ▼
Impact Identification
          │
          ▼
      Authoring
          │
          ▼
       Review
          │
          ▼
 Quality Evaluation
          │
          ▼
      Approval
          │
          ▼
     Publishing
          │
          ▼
     Maintenance
          │
          ▼
     Retirement
```

The operational record captures the lifecycle:

```yaml
knowledge_operation:
  operation_id: "KO-REFUND-001"

  asset:
    asset_id: "KU-REFUND-001"
    asset_type: "knowledge_unit"

  lifecycle:
    state: "published"
    previous_state: "approved"

  change:
    trigger: "policy_change"
    reason: "Refund eligibility period changed from 30 days to 60 days"

  ownership:
    owner: "Customer Operations"
    reviewer: "Support Operations"
    approver: "Customer Operations Lead"

  quality:
    assessment_id: "QA-REFUND-001"
    status: "passed"

  version:
    current: "2.0"
    previous: "1.0"

  publication:
    status: "published"

  review:
    next_review_date: "2027-01-15"
```

---

# What This Demonstrates

The demo shows that a business change does not require an isolated documentation update.

Instead, the change moves through a controlled operational lifecycle.

```text
 Business Change
        ↓
Affected Knowledge
        ↓
      Review
        ↓
     Quality
        ↓
     Approval
        ↓
 Published Version
        ↓
Ongoing Maintenance
```

This provides:

* Clear ownership
* Controlled changes
* Quality checkpoints
* Approval before publication
* Version traceability
* Maintenance planning
* Controlled retirement

---

# Relationship to Previous Subprojects

The demo demonstrates the cumulative architecture established by the repository.

```text
01 Agent-Ready Knowledge Base
              ↓
    Structured Knowledge

02 Agent Execution Workflows
              ↓
     Structured Behavior

03 Knowledge Quality Evaluator
              ↓
     Quality & Governance

04 Knowledge Operations Pipeline
              ↓
     Lifecycle Management
```

The same refund example is carried forward through each layer.

The Knowledge Operations layer does not replace the previous assets.

It provides the process required to keep them maintained and governed over time.

---

# Final Outcome

Subproject 04 demonstrates the transition from:

```text
Governed Knowledge Assets
```

to:

```text
A Repeatable Knowledge Operating Model
```

The operational lifecycle ensures that knowledge can evolve alongside the business while remaining:

* Structured
* Governed
* Traceable
* Evaluated
* Maintainable

This establishes the operational foundation required for the final architectural layer:

```text
Knowledge Platform
```

Subproject 05 will explore how these structured and governed knowledge assets can become part of a broader enterprise knowledge platform.
