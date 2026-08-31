# Knowledge Operations Governance

## Purpose

Knowledge Operations governance defines the controls required to ensure that structured knowledge is created, changed, reviewed, published, maintained, and retired in a consistent and traceable manner.

The governance layer builds on the quality and governance principles established in Subproject 03.

Its purpose is not to introduce another quality framework.

Instead, it defines **how quality and governance requirements are applied during the knowledge lifecycle**.

---

## Governance Principles

### 1. Defined Ownership

Every operationally managed knowledge asset must have a clearly identified owner.

The owner is responsible for ensuring that the asset remains accurate and maintained throughout its lifecycle.

```text
Knowledge Asset
      ↓
Assigned Owner
      ↓
Lifecycle Management
```

Ownership should not depend on individual contributors remaining available.

---

### 2. Controlled Changes

Changes to published knowledge must enter the operational lifecycle rather than being applied directly to the active version.

```text
Change
  ↓
Intake
  ↓
Review
  ↓
Quality Evaluation
  ↓
Approval
  ↓
Publication
```

This provides a controlled path from a proposed change to a production knowledge asset.

---

### 3. Quality Gate Before Publication

Knowledge should satisfy the applicable quality requirements before publication.

The quality framework from Subproject 03 acts as the evaluation mechanism.

```text
Review
   ↓
Quality Evaluation
   ↓
Pass ─────→ Approval
   │
   └─ Fail → Revision
```

An asset that fails required quality checks should not proceed directly to publication.

---

### 4. Explicit Approval

Publication requires approval from an authorized owner or role.

The approval should identify:

* The asset being approved
* The version being approved
* The responsible approver
* The approval status

This establishes accountability for changes entering the active knowledge system.

---

### 5. Version Traceability

Published knowledge should have identifiable versions.

When an asset changes:

```text
Previous Version
      ↓
New Version
      ↓
Published Version
```

The operational record should preserve the relationship between the previous and current versions.

This makes it possible to understand what changed and when.

---

### 6. Change Traceability

Operational changes should retain sufficient information to reconstruct the lifecycle of an asset.

At minimum, the organization should be able to determine:

* What changed
* Why it changed
* Who changed it
* Who reviewed it
* Who approved it
* Which version was published

This provides an operational audit trail without requiring a complex auditing platform.

---

### 7. Impact Awareness

Changes should consider related knowledge assets before publication.

For example:

```text
Policy Change
     │
     ├── Knowledge Unit
     ├── Execution Workflow
     ├── Escalation Rules
     └── Supporting Knowledge
```

Affected assets should be identified and reviewed where necessary.

The objective is to reduce inconsistencies caused by updating only one part of a connected knowledge system.

---

### 8. Controlled Retirement

Obsolete knowledge should not remain active indefinitely.

When an asset is no longer valid:

```text
Published
    ↓
Maintenance
    ↓
Retired
```

Retirement should remove the asset from active use while preserving historical information required for traceability.

---

### 9. Scheduled Review

Knowledge should have an appropriate review expectation based on its business context.

The operational record may therefore contain a review date:

```yaml id="x8r6nm"
review:
  next_review_date: "2027-01-15"
```

The review date does not automatically mean that the asset is invalid after that date.

It indicates that the asset should be reassessed.

---

## Lifecycle Governance

The governance controls can be mapped to the operational lifecycle:

| Lifecycle Stage    | Governance Control                      |
| ------------------ | --------------------------------------- |
| Intake             | Change reason and ownership identified  |
| Authoring          | Existing assets reused where possible   |
| Review             | Responsible reviewer identified         |
| Quality Evaluation | Required quality checks completed       |
| Approval           | Authorized approval recorded            |
| Publishing         | Approved version becomes active         |
| Maintenance        | Changes remain traceable                |
| Retirement         | Obsolete assets removed from active use |

This keeps governance embedded within the operational process rather than treating it as a separate activity.

---

## Minimum Governance Requirements

A knowledge asset should not be considered operationally governed unless the following information is available:

```text
Owner
Lifecycle State
Change Reason
Reviewer
Approval
Quality Status
Version
Publication Status
Review Information
```

These requirements correspond directly to the operational schema defined in Subproject 04.

---

## Governance Example

For the refund policy change:

```yaml id="z8g6qk"
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

The record demonstrates that the change has:

* A defined owner
* A documented reason
* A reviewer
* A quality assessment
* An authorized approver
* A traceable version
* A publication state
* A future review expectation

---

## Relationship to Subproject 03

Subproject 03 established the quality and governance framework used to evaluate knowledge and workflow assets.

Subproject 04 operationalizes those requirements.

```text
03 Quality Architecture
        │
        │ Quality criteria
        ▼
04 Knowledge Operations
        │
        │ Lifecycle enforcement
        ▼
Governed Knowledge
```

The distinction is important:

**Subproject 03 asks:**

> Does the asset meet the required quality and governance criteria?

**Subproject 04 asks:**

> How are those requirements incorporated into the asset's lifecycle?

This prevents the two subprojects from overlapping.

---

## Governance Boundary

This governance model intentionally does not define:

* Enterprise access-control policies
* Identity management
* Legal or regulatory compliance frameworks
* Organization-wide risk policies
* Technical publishing infrastructure
* Workflow orchestration technology

Those concerns may exist in a production implementation but are outside the scope of this repository.

The focus is on the operational governance required to manage structured knowledge consistently.

---

## Governance Outcome

Knowledge Operations governance ensures that knowledge changes follow a controlled lifecycle:

```text
Change
  ↓
Ownership
  ↓
Review
  ↓
Quality
  ↓
Approval
  ↓
Publication
  ↓
Maintenance
  ↓
Retirement
```

This provides the operational controls required to keep structured knowledge **accurate, traceable, governed, and maintainable over time**.

---

## Next Step

The next step is to define how the effectiveness of the Knowledge Operations layer can be evaluated.

That will live in:

`6. Evaluation/knowledge_operations_evaluation.md`
