# Evaluation Patterns

## Background

As organizations create larger collections of AI-ready knowledge assets, evaluating every document from scratch becomes increasingly difficult.

Fortunately, most quality assessments follow a small number of recurring evaluation patterns.

For example:

* Reviewing a new knowledge asset before publication
* Comparing two versions of the same workflow
* Identifying quality regressions after an update
* Auditing governance compliance
* Measuring overall knowledge quality across a repository

Recognizing these patterns helps organizations standardize evaluation processes, improve consistency, and scale governance across growing knowledge ecosystems.

This document outlines several common evaluation patterns used throughout AI-first knowledge systems.

---

## Pattern 1: Quality Scorecard

### Purpose

Assess an individual knowledge asset against a predefined set of quality dimensions.

### Example

A product help article is evaluated for:

* Completeness
* Clarity
* Consistency
* Accuracy
* Governance Readiness

### Evaluation

```text
Knowledge Asset
        ↓
Evaluate Quality Dimensions
        ↓
Generate Scorecard
```

### Why It Matters

Quality scorecards provide a repeatable way to compare assets using consistent evaluation criteria.

---

## Pattern 2: Compliance Review

### Purpose

Verify that a knowledge asset satisfies organizational standards before publication.

### Example

Review whether an execution workflow:

* Includes required metadata
* Defines entry and exit conditions
* Documents escalation paths
* References the approved schema

### Evaluation

```text
Knowledge Asset
        ↓
Compliance Checklist
        ↓
Pass / Revise
```

### Why It Matters

Compliance reviews help ensure that published knowledge follows established governance practices.

---

## Pattern 3: Gap Analysis

### Purpose

Identify missing information that could affect AI agent performance.

### Example

During evaluation, reviewers discover that a refund workflow does not define policy exceptions.

### Evaluation

```text
Knowledge Asset
        ↓
Identify Missing Information
        ↓
Improvement Recommendations
```

### Why It Matters

Gap analysis helps teams improve knowledge completeness before deployment.

---

## Pattern 4: Consistency Review

### Purpose

Detect conflicting or inconsistent information across multiple knowledge assets.

### Example

Two workflow documents define different eligibility rules for the same business process.

### Evaluation

```text
Knowledge Repository
        ↓
Compare Related Assets
        ↓
Identify Conflicts
```

### Why It Matters

Consistency reviews prevent contradictory knowledge from producing inconsistent agent behavior.

---

## Pattern 5: Version Comparison

### Purpose

Evaluate how knowledge quality changes between revisions.

### Example

A workflow is updated after a policy change.

Reviewers compare the previous and current versions to determine whether quality has improved or declined.

### Evaluation

```text
Version A
        ↓
Compare Changes
        ↓
Version B
        ↓
Quality Impact
```

### Why It Matters

Version comparisons help organizations understand the impact of knowledge changes over time.

---

## Pattern 6: Repository Health Assessment

### Purpose

Measure the overall quality of a collection of AI-ready knowledge assets.

### Example

An organization evaluates:

* Average quality score
* Assets requiring review
* Assets missing governance approval
* Common quality issues

### Evaluation

```text
Knowledge Repository
        ↓
Aggregate Evaluation Results
        ↓
Repository Health Report
```

### Why It Matters

Repository-level evaluation helps Knowledge Operations teams prioritize improvement efforts.

---

## Pattern 7: Continuous Quality Monitoring

### Purpose

Treat evaluation as an ongoing operational process rather than a one-time review.

### Example

Knowledge assets are automatically re-evaluated after:

* Policy updates
* Workflow revisions
* Major content changes
* Scheduled governance reviews

### Evaluation

```text
Knowledge Changes
        ↓
Re-evaluate Assets
        ↓
Updated Quality Scores
```

### Why It Matters

Continuous monitoring ensures that knowledge quality evolves alongside the organization.

---

## Combining Patterns

Most governance processes combine several evaluation patterns.

### New Knowledge Asset

```text
Compliance Review
        ↓
Quality Scorecard
        ↓
Gap Analysis
        ↓
Publish
```

### Existing Repository

```text
Version Comparison
        ↓
Consistency Review
        ↓
Repository Health Assessment
        ↓
Continuous Monitoring
```

Large AI-first organizations typically use multiple evaluation patterns together rather than relying on a single review process.

---

## Why Evaluation Patterns Matter

Recognizing common evaluation patterns allows teams to:

* Standardize quality assessment
* Improve reviewer consistency
* Scale governance across larger repositories
* Identify recurring quality issues
* Support continuous improvement

Instead of designing every evaluation independently, organizations can build repeatable review processes from proven evaluation patterns.

---

## Key Takeaway

Quality evaluation is not a single activity.

It consists of several reusable patterns that support different governance objectives:

* Quality Scorecards
* Compliance Reviews
* Gap Analysis
* Consistency Reviews
* Version Comparisons
* Repository Health Assessments
* Continuous Quality Monitoring

Together, these patterns help organizations build reliable, measurable, and continuously improving AI-ready knowledge systems.

---

## Next step within this subproject

The next step is to define a machine-readable schema for representing evaluation criteria, quality dimensions, scoring results, and governance metadata in a consistent format.

That will live in:

`schemas/quality_evaluation_schema.yaml`
