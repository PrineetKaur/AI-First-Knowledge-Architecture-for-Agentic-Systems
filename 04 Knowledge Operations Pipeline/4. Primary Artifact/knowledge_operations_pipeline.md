Yes. We now move to the **Primary Artifact**. Since we agreed to keep Subproject 04 minimal, I would make the artifact a single concrete **Knowledge Operations Pipeline** using the existing refund Knowledge Unit, Execution Workflow, and Quality Assessment.

# Knowledge Operations Pipeline

## Purpose

The Knowledge Operations Pipeline demonstrates how structured knowledge assets move through a governed operational lifecycle.

It builds directly on the assets established in the previous subprojects:

```text
Knowledge Unit
      +
Execution Workflow
      +
Quality Assessment
      ↓
Knowledge Operations Pipeline
```

The pipeline does not create a new representation of knowledge.

Instead, it coordinates the activities required to move existing assets from change intake to a controlled published state.

---

## Pipeline Overview

The operational pipeline is:

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

Each stage represents an operational activity rather than a new knowledge type.

---

## 1. Change Intake

The lifecycle begins when a change to the underlying business, product, or policy is identified.

### Example

The refund policy changes:

```text
Previous:
Customers may receive a refund within 30 days.

New:
Customers may receive a refund within 60 days.
```

The change is recorded as:

```yaml
operation_id: "KO-REFUND-001"
trigger: "policy_change"
reason: "Refund eligibility period changed from 30 days to 60 days"
```

The change becomes the starting point for the operational lifecycle.

---

## 2. Impact Identification

The organization identifies the knowledge assets that may be affected by the change.

For the refund example:

```text
Refund Policy Change
        │
        ├── KU-REFUND-001
        │   Refund Knowledge Unit
        │
        ├── WF-REFUND-001
        │   Refund Execution Workflow
        │
        └── Related supporting knowledge
```

The purpose is to prevent a business change from being applied to only one representation while leaving related assets outdated.

---

## 3. Authoring

The identified assets are updated to reflect the new business requirement.

### Knowledge Unit

The existing refund Knowledge Unit is updated from:

```text
Refund eligibility period: 30 days
```

to:

```text
Refund eligibility period: 60 days
```

### Execution Workflow

The corresponding refund workflow is reviewed and updated where the previous rule affects workflow decisions.

The operational pipeline therefore manages changes across existing assets rather than creating duplicate content.

---

## 4. Review

The updated assets are reviewed by the appropriate subject matter expert or designated reviewer.

```text
Authoring
    ↓
In Review
```

The reviewer confirms that the proposed changes accurately represent the underlying business requirement.

The review outcome is recorded before the assets progress to quality evaluation.

---

## 5. Quality Evaluation

The updated assets are evaluated using the quality framework established in Subproject 03.

```text
In Review
    ↓
Quality Evaluation
    ↓
Evaluated
```

The evaluation verifies that the updated assets continue to satisfy the required quality and governance criteria.

For example:

```yaml
assessment_id: "QA-REFUND-001"
status: "passed"
```

If the assets do not meet the required criteria, they return to authoring or review rather than progressing to publication.

```text
Quality Check
      │
      ├── Pass → Approval
      │
      └── Fail → Authoring / Review
```

---

## 6. Approval

Once review and quality requirements are satisfied, an authorized owner approves the change.

```text
Evaluated
    ↓
Approved
```

Approval provides a controlled transition between evaluation and publication.

The approval record identifies the responsible approver and the version approved for publication.

---

## 7. Publishing

The approved version becomes the active version of the knowledge asset.

```text
Approved
    ↓
Published
```

For the refund example:

```text
KU-REFUND-001
Previous Version: 1.0
New Version:      2.0
Status:           Published
```

The published version becomes the version available to downstream consumers.

This may include:

* Human-facing documentation
* Automated systems
* AI agents
* Internal applications

The pipeline itself does not define the publishing technology.

It defines the governed transition into the published state.

---

## 8. Maintenance

Publishing does not end the lifecycle.

Knowledge remains subject to future changes and scheduled review.

```text
Published
    ↓
Maintenance
```

Maintenance may be triggered by:

* A new policy change
* A product change
* A quality issue
* A dependency change
* A scheduled review

For example:

```text
Published Refund Policy
        ↓
New Business Requirement
        ↓
Knowledge Operation Created
        ↓
Review Cycle Begins
```

This creates a continuous operating loop rather than a one-time publishing process.

---

## 9. Retirement

When an asset is no longer valid or required, it can be retired.

```text
Maintenance
    ↓
Retired
```

Retirement removes the obsolete asset from active use while preserving the historical record required for traceability.

For example:

```text
Refund Knowledge Unit
Version 1.0 → Retired
Version 2.0 → Published
```

The operational record therefore distinguishes historical versions from the currently active version.

---

# End-to-End Example

The complete refund policy change can be represented as:

```text
Business Policy Change
        │
        ▼
Change Intake
        │
        ▼
Impact Identification
        │
        ├── Knowledge Unit
        ├── Execution Workflow
        └── Related Assets
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
        ├── Failed ──────→ Authoring
        │
        └── Passed
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

---

# Operational Record

The lifecycle can be represented using the operational schema defined earlier:

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
    published_at: "2026-08-31"

  review:
    next_review_date: "2027-01-15"
```

This record provides the operational context around the underlying Knowledge Unit without duplicating its content.

---

# Relationship to Previous Subprojects

The pipeline demonstrates how the four architectural layers work together.

```text
01 Knowledge Architecture
        │
        │ Structured Knowledge
        ▼
02 Behavior Architecture
        │
        │ Execution Workflow
        ▼
03 Quality Architecture
        │
        │ Quality Assessment
        ▼
04 Knowledge Operations
        │
        │ Lifecycle Management
        ▼
Governed Published Knowledge
```

Each layer retains its own responsibility.

Knowledge Architecture defines the asset.

Behavior Architecture defines how the asset is used within an execution process.

Quality Architecture evaluates whether the asset meets defined standards.

Knowledge Operations manages the asset throughout its lifecycle.

---

# Operational Outcome

The Knowledge Operations Pipeline provides a repeatable process for:

* Capturing knowledge changes
* Identifying affected assets
* Coordinating updates
* Performing review
* Triggering quality evaluation
* Controlling approval
* Managing publication
* Supporting maintenance
* Retiring obsolete versions

The result is a knowledge system where changes are managed through an explicit lifecycle rather than through isolated documentation updates.

---

# Scope

This artifact intentionally demonstrates the **operating model**, not a production workflow orchestration system.

It does not attempt to implement:

* Automated workflow execution
* Enterprise publishing infrastructure
* Identity and access management
* Dependency graph automation
* Notification systems
* Full content management functionality

These capabilities may support a production implementation, but they are outside the scope of this repository.

The objective is to demonstrate the operational architecture required to keep structured knowledge accurate, governed, and maintainable over time.

---

# Primary Artifact Outcome

The Knowledge Operations Pipeline establishes the operational layer between governed knowledge assets and the future knowledge platform.

```text
Structured Knowledge
        ↓
Structured Behavior
        ↓
Measured Quality
        ↓
Operational Lifecycle
        ↓
Knowledge Platform
```

Subproject 04 therefore transforms the repository from a collection of governed knowledge assets into a **repeatable knowledge operating model**.
