# Knowledge Operations Schema

## Purpose

The Knowledge Operations layer requires a minimal representation of the operational information associated with a knowledge asset.

The schema should allow the organization to answer:

* What asset is being managed?
* Who owns it?
* What state is it in?
* What triggered the change?
* Who reviewed it?
* What quality assessment was performed?
* Which version is currently active?
* When should it be reviewed again?

The schema does not redefine the underlying knowledge asset.

Instead, it provides the operational metadata required to manage that asset throughout its lifecycle.

---

## Design Principle

The operational schema sits around the existing knowledge architecture.

```text
┌──────────────────────────────┐
│      Knowledge Asset         │
│                              │
│ Knowledge Unit               │
│ Execution Workflow           │
│ Quality Assessment           │
└──────────────┬───────────────┘
               │
               │ managed through
               ▼
┌──────────────────────────────┐
│    Operational Metadata      │
│                              │
│ Ownership                    │
│ Lifecycle State              │
│ Change Information           │
│ Review Information           │
│ Version Information          │
│ Publication Information      │
└──────────────────────────────┘
```

This separation prevents operational metadata from becoming another representation of the knowledge itself.

---

## Operational Entity

The primary entity introduced by this subproject is the **Knowledge Operation**.

A Knowledge Operation represents the lifecycle management information associated with a knowledge asset.

It can reference different asset types established by previous subprojects:

* Knowledge Unit
* Execution Workflow
* Quality Assessment

---

## Schema

```yaml
knowledge_operation:
  operation_id: "KO-REFUND-001"

  asset:
    asset_id: "KU-REFUND-001"
    asset_type: "knowledge_unit"

  lifecycle:
    state: "in_review"
    previous_state: "published"

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
    status: "pending"
    published_at: null

  review:
    next_review_date: "2027-01-15"

  history:
    created_at: "2026-08-31"
    updated_at: "2026-08-31"
```

---

## Field Definitions

| Field                      | Description                                   | Example                      |
| -------------------------- | --------------------------------------------- | ---------------------------- |
| `operation_id`             | Unique identifier for the operational record  | `KO-REFUND-001`              |
| `asset.asset_id`           | Identifier of the managed knowledge asset     | `KU-REFUND-001`              |
| `asset.asset_type`         | Type of asset being managed                   | `knowledge_unit`             |
| `lifecycle.state`          | Current lifecycle state                       | `in_review`                  |
| `lifecycle.previous_state` | Previous lifecycle state                      | `published`                  |
| `change.trigger`           | Event that initiated the operation            | `policy_change`              |
| `change.reason`            | Explanation for the change                    | `Refund eligibility changed` |
| `ownership.owner`          | Responsible owner                             | `Customer Operations`        |
| `ownership.reviewer`       | Person or team responsible for review         | `Support Operations`         |
| `ownership.approver`       | Authorized approval role                      | `Customer Operations Lead`   |
| `quality.assessment_id`    | Reference to Subproject 03 quality assessment | `QA-REFUND-001`              |
| `quality.status`           | Result of the required quality assessment     | `passed`                     |
| `version.current`          | Version being created or managed              | `2.0`                        |
| `version.previous`         | Previously active version                     | `1.0`                        |
| `publication.status`       | Current publication status                    | `pending`                    |
| `publication.published_at` | Publication timestamp                         | `null`                       |
| `review.next_review_date`  | Planned future review date                    | `2027-01-15`                 |
| `history.created_at`       | Date the operation was created                | `2026-08-31`                 |
| `history.updated_at`       | Date the operation was last updated           | `2026-08-31`                 |

---

## Lifecycle States

The `lifecycle.state` field uses the operational states defined in the Design layer:

```text
draft
  ↓
in_review
  ↓
evaluated
  ↓
approved
  ↓
published
  ↓
maintenance
  ↓
retired
```

These states describe the operational condition of the asset.

They do not replace the content or quality status of the underlying asset.

---

## Asset Types

The schema intentionally supports the existing asset types from previous subprojects.

### Knowledge Unit

```yaml
asset:
  asset_id: "KU-REFUND-001"
  asset_type: "knowledge_unit"
```

### Execution Workflow

```yaml
asset:
  asset_id: "WF-REFUND-001"
  asset_type: "execution_workflow"
```

### Quality Assessment

Quality assessments are primarily referenced rather than managed as knowledge assets:

```yaml
quality:
  assessment_id: "QA-REFUND-001"
  status: "passed"
```

This maintains the architectural boundary established by Subproject 03.

---

## Example: Refund Policy Change

The schema can represent the refund policy change introduced in the Problem Statement.

```yaml
knowledge_operation:
  operation_id: "KO-REFUND-001"

  asset:
    asset_id: "KU-REFUND-001"
    asset_type: "knowledge_unit"

  lifecycle:
    state: "in_review"
    previous_state: "published"

  change:
    trigger: "policy_change"
    reason: "Refund eligibility period changed from 30 days to 60 days"

  ownership:
    owner: "Customer Operations"
    reviewer: "Support Operations"
    approver: "Customer Operations Lead"

  quality:
    assessment_id: "QA-REFUND-001"
    status: "pending"

  version:
    current: "2.0"
    previous: "1.0"

  publication:
    status: "pending"
    published_at: null

  review:
    next_review_date: "2027-01-15"

  history:
    created_at: "2026-08-31"
    updated_at: "2026-08-31"
```

The operational record does not contain the refund policy itself.

The policy remains in the existing Knowledge Unit.

The operation records **how that Knowledge Unit is being managed**.

---

## Relationship Between Assets

A business change may affect multiple assets.

For example:

```text
Policy Change
     │
     ├── KU-REFUND-001
     │
     ├── WF-REFUND-001
     │
     └── QA-REFUND-001
```

Each asset can have its own operational record while maintaining references to the related assets.

This allows the organization to track the lifecycle of each asset without creating a new combined knowledge representation.

---

## Schema Boundaries

The operational schema intentionally does not define:

* Knowledge content structure
* Workflow execution logic
* Quality scoring methodology
* Agent reasoning
* Publishing infrastructure
* Identity or access management

Those responsibilities belong to other architectural layers.

```text
Knowledge Schema
      ↓
Knowledge Architecture

Workflow Schema
      ↓
Behavior Architecture

Quality Schema
      ↓
Quality Architecture

Operational Schema
      ↓
Knowledge Operations
```

This separation keeps each subproject focused on one architectural responsibility.

---

## Minimum Required Fields

For an operational record to be useful, the following information should be available:

```text
Asset Identity
Lifecycle State
Ownership
Change Reason
Version
Quality Status
Publication Status
Review Information
```

Additional metadata can be introduced by a production implementation when required, but it is not necessary for the operating model demonstrated in this repository.

---

## Design Outcome

The Knowledge Operations schema provides a lightweight operational wrapper around existing knowledge assets.

It enables the organization to track:

```text
What asset?
     ↓
Why changed?
     ↓
Who owns it?
     ↓
What state?
     ↓
Was it evaluated?
     ↓
Was it approved?
     ↓
What version is active?
     ↓
When should it be reviewed?
```

This creates the minimum structured information required to operate governed knowledge throughout its lifecycle without introducing another knowledge representation.

---

## Next Step

The next step is to create the primary artifact that demonstrates this operational model in practice.

That artifact will show how a knowledge change moves through the defined lifecycle from **intake to publication and maintenance**.
