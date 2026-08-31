# Knowledge Operations Overview

## Purpose

Subprojects 01, 02, and 03 established the foundational capabilities required for reliable AI-ready knowledge:

* **Knowledge Architecture** defines how knowledge is structured.
* **Behavior Architecture** defines how agents should apply knowledge.
* **Quality Architecture** defines how knowledge and workflows are evaluated and governed.

Subproject 04 introduces the **Operational layer**.

The purpose of this layer is to define how these assets are continuously created, reviewed, evaluated, published, maintained, and retired.

The focus is not on building a complex content management platform.

The focus is on establishing a **repeatable operating model for governed knowledge**.

---

## The Operational Model

Knowledge operations connects the outputs of the previous subprojects with the ongoing lifecycle of knowledge assets.

```text
Knowledge Architecture
        │
        ▼
Structured Knowledge
        │
        ▼
Behavior Architecture
        │
        ▼
Execution Workflows
        │
        ▼
Quality Architecture
        │
        ▼
Quality & Governance Checks
        │
        ▼
Knowledge Operations
        │
        ├── Intake
        ├── Authoring
        ├── Review
        ├── Approval
        ├── Publishing
        ├── Maintenance
        └── Retirement
```

The operational layer does not replace the previous layers.

It coordinates them.

---

## Design Principles

### 1. Lifecycle First

Knowledge should be managed throughout its lifecycle rather than only during creation.

The operational model therefore covers:

```text
Intake
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

Each stage represents a controlled transition rather than an informal activity.

---

### 2. Reuse Existing Knowledge Assets

Knowledge operations should operate on the structured assets already established by the repository.

The pipeline should not introduce a separate representation of knowledge.

For example:

```text
Knowledge Unit
      +
Execution Workflow
      +
Quality Assessment
      ↓
Operational Lifecycle
```

This keeps the operational layer connected to the existing architecture.

---

### 3. Quality Is Part of the Lifecycle

Quality evaluation should not be treated as a separate activity performed only after an asset is complete.

Instead, it becomes an operational checkpoint within the lifecycle.

```text
Author
  ↓
Review
  ↓
Quality Evaluation
  ↓
Approval
  ↓
Publish
```

An asset should not progress to publication unless it satisfies the required quality and governance conditions.

This connects Subproject 03 directly to Subproject 04.

---

### 4. Explicit Ownership

Every operationally managed asset should have a defined owner.

Ownership should make it possible to determine:

* Who is responsible for maintaining the asset?
* Who reviews changes?
* Who approves publication?
* Who initiates retirement?

Operational processes should not depend on implicit ownership.

---

### 5. Traceable Changes

Changes to knowledge should be traceable.

The operational model should capture enough information to understand:

* What changed
* Why it changed
* Who changed it
* Who reviewed it
* Which version was published
* When the change became effective

This becomes particularly important when business policies change and multiple knowledge assets are affected.

---

### 6. Controlled Publishing

Not every change should immediately become published knowledge.

The operational lifecycle separates:

```text
Draft
  ↓
Reviewed
  ↓
Evaluated
  ↓
Approved
  ↓
Published
```

This provides a controlled transition from working content to production knowledge.

---

### 7. Change Impact Awareness

Knowledge assets rarely exist in isolation.

A change to one asset may affect related:

* Knowledge Units
* Execution Workflows
* Policies
* Escalation rules
* Supporting documentation

The operational process should therefore identify potentially affected assets before changes are published.

This does not require a complex dependency engine.

The important principle is that **change impact should be considered as part of knowledge maintenance**.

---

## Knowledge Lifecycle

The lifecycle defined for this subproject is:

```text
1. Intake
      ↓
2. Authoring
      ↓
3. Review
      ↓
4. Quality Evaluation
      ↓
5. Approval
      ↓
6. Publishing
      ↓
7. Maintenance
      ↓
8. Retirement
```

Each stage has a distinct purpose.

### 1. Intake

A knowledge change is identified and formally introduced into the operational process.

Typical triggers include:

* New business requirements
* Policy changes
* Product changes
* Identified knowledge gaps
* Quality issues
* Scheduled reviews

---

### 2. Authoring

The relevant knowledge assets are created or updated.

Where possible, existing structured assets should be modified rather than creating duplicate representations.

---

### 3. Review

The proposed change is reviewed by the appropriate owner or subject matter expert.

The purpose is to validate that the content accurately reflects the underlying business or product requirement.

---

### 4. Quality Evaluation

The updated assets are evaluated using the quality framework established in Subproject 03.

This determines whether the assets meet the required quality and governance criteria.

---

### 5. Approval

An authorized owner approves the assets for publication.

Approval represents the transition from evaluated content to publishable knowledge.

---

### 6. Publishing

The approved version becomes the active version consumed by downstream systems.

The published version should remain identifiable and traceable.

---

### 7. Maintenance

Published knowledge continues to be monitored and updated as the underlying business changes.

Maintenance may be triggered by:

* New business changes
* Quality findings
* Scheduled review dates
* Dependency changes
* Newly identified gaps

---

### 8. Retirement

Knowledge that is no longer valid or required is removed from active use.

The previous version should remain traceable where historical records are required.

Retirement prevents obsolete knowledge from continuing to appear as active guidance.

---

## Operational States

To keep the lifecycle simple, knowledge assets can move through a small set of operational states:

```text
Draft
  ↓
In Review
  ↓
Evaluated
  ↓
Approved
  ↓
Published
  ↓
Maintenance
  ↓
Retired
```

These states provide a common operational vocabulary without requiring a complex workflow engine.

The important distinction is between:

**Content state**

What condition is the asset currently in?

and

**Operational activity**

What action is being performed on the asset?

For example:

```text
Published
    │
    └── Maintenance triggered
              │
              ▼
           In Review
```

This allows the operational lifecycle to represent change without redefining the underlying knowledge asset.

---

## Example: Refund Policy Change

The operational model can be applied to the refund example introduced in the Problem Statement.

### Change Trigger

The refund policy changes from **30 days** to **60 days**.

```text
Business Policy Change
        ↓
Knowledge Change Intake
```

### Impact Identification

The organization identifies the affected assets:

```text
Refund Policy
     │
     ├── Refund Knowledge Unit
     ├── Refund Execution Workflow
     ├── Escalation Rules
     └── Related Documentation
```

### Update and Review

The relevant assets are updated and reviewed.

```text
Draft
  ↓
In Review
```

### Quality Check

The updated assets are evaluated using the quality framework from Subproject 03.

```text
In Review
    ↓
Quality Evaluation
    ↓
Evaluated
```

### Approval and Publication

Once the required criteria are satisfied:

```text
Evaluated
    ↓
Approved
    ↓
Published
```

The new 60-day policy is now the active version.

### Maintenance

The assets remain subject to future changes and review.

```text
Published
    ↓
Future Change
    ↓
Maintenance
```

### Retirement

When the knowledge is eventually replaced or becomes obsolete:

```text
Maintenance
    ↓
Retired
```

This demonstrates how a single business change can move through a controlled operational lifecycle rather than being handled as an isolated documentation update.

---

## Relationship to Previous Layers

Knowledge Operations depends directly on the capabilities established by the previous subprojects.

```text
01 Knowledge Architecture
        ↓
Defines the knowledge assets

02 Behavior Architecture
        ↓
Defines the workflows that use the knowledge

03 Quality Architecture
        ↓
Defines how those assets are evaluated

04 Knowledge Operations
        ↓
Defines how those assets are managed throughout their lifecycle
```

Each layer therefore has a distinct responsibility.

| Layer      | Responsibility             |
| ---------- | -------------------------- |
| Knowledge  | Structure knowledge        |
| Behavior   | Structure agent behavior   |
| Quality    | Measure and govern quality |
| Operations | Manage the lifecycle       |

Knowledge Operations is therefore the connective layer between **governed knowledge assets** and their continued use in a production environment.

---

## Operational Outcome

A successful knowledge operations model should provide:

* Repeatable lifecycle management
* Clear ownership
* Controlled review and approval
* Quality checkpoints
* Version traceability
* Governed publishing
* Change awareness
* Controlled retirement

The objective is not to automate every operational activity.

The objective is to make the process **explicit, repeatable, and governable**.

---

## Design Boundary

This subproject intentionally does not attempt to build:

* A full content management system
* A workflow orchestration platform
* An enterprise identity system
* A dependency graph engine
* An automated publishing infrastructure
* A replacement for the quality framework

Those capabilities may exist in a production implementation, but they are outside the scope of this repository.

The repository focuses on the **knowledge operating model** that defines how structured knowledge should move through its lifecycle.

---

## Next Step

With the operational lifecycle established, the next step is to define the minimal schema required to represent and manage an operational knowledge asset throughout that lifecycle.

That will live in:

`3. Schema/knowledge_operations_schema.md`
