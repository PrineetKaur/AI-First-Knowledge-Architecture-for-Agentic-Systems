# Evaluation Design Principles

## Background

A quality evaluation framework is only useful if different reviewers can apply it consistently.

Without shared evaluation principles, two reviewers may assess the same knowledge asset and produce completely different conclusions.

For example:

* One reviewer may prioritize completeness.
* Another may focus on clarity.
* A third may evaluate only technical accuracy.

While each assessment may be reasonable, inconsistent evaluation makes it difficult to compare quality across assets or measure improvements over time.

To support reliable governance, quality evaluation must follow a common set of design principles.

This document outlines the principles used throughout this project when evaluating AI-ready knowledge assets.

---

## Principle 1: Evaluate Against Explicit Criteria

Quality should never be assessed using vague impressions such as:

```text
This documentation looks good.
```

Instead, every evaluation should reference predefined criteria.

For example:

* Completeness
* Clarity
* Consistency
* Accuracy
* Governance Readiness

Explicit criteria improve repeatability and reduce subjective judgement.

---

## Principle 2: Evaluate the Asset, Not the Model

The purpose of this project is to assess the quality of knowledge assets themselves.

Evaluation should not depend on:

* Which LLM is used
* Prompt engineering techniques
* Agent implementation
* User interface

Instead, the evaluation should answer:

> "Is this knowledge asset suitable for reliable AI consumption?"

Keeping the focus on the asset makes evaluation reusable across different AI systems.

---

## Principle 3: Measure Multiple Quality Dimensions

Knowledge quality cannot be represented by a single score.

A document may be:

* Complete but ambiguous
* Accurate but inconsistent
* Well structured but missing important constraints

Evaluation should therefore consider multiple dimensions independently.

For example:

```text
Completeness
Consistency
Clarity
Accuracy
Governance Readiness
```

Breaking quality into dimensions helps identify specific improvement opportunities.

---

## Principle 4: Produce Repeatable Results

Different reviewers should reach similar conclusions when evaluating the same asset.

Evaluation methods should therefore:

* Use standardized criteria
* Apply consistent scoring scales
* Minimize personal interpretation

Repeatability improves trust in the evaluation process.

---

## Principle 5: Identify Improvement Opportunities

Evaluation should not simply determine whether an asset passes or fails.

Instead, it should explain:

* Which quality dimensions require improvement
* Why the score was assigned
* What changes would improve the asset

The goal is continuous improvement rather than one-time assessment.

---

## Principle 6: Support Governance

Evaluation should contribute to knowledge governance rather than existing as an isolated activity.

Evaluation results should support decisions such as:

* Publish
* Revise
* Reject
* Archive
* Re-evaluate

This allows organizations to manage knowledge assets throughout their lifecycle.

---

## Principle 7: Treat Evaluation as an Ongoing Process

Knowledge changes over time.

Business rules evolve.

Policies are updated.

Workflows are revised.

Evaluation should therefore be performed throughout the lifecycle of a knowledge asset rather than only before initial publication.

Continuous evaluation helps maintain quality as knowledge evolves.

---

## Principle 8: Design for Scalability

As organizations create hundreds or thousands of AI-ready knowledge assets, manual evaluation alone becomes difficult to sustain.

Evaluation frameworks should therefore be designed so they can support:

* Structured review checklists
* Rule-based validation
* Automated quality checks
* AI-assisted evaluation

Designing with scalability in mind prepares organizations for larger knowledge ecosystems.

---

## Summary

Within this project, quality evaluation is designed to be:

* Objective
* Repeatable
* Multi-dimensional
* Actionable
* Governable
* Lifecycle-oriented
* Scalable

These principles help transform quality evaluation from an informal review activity into a structured governance capability for AI-ready knowledge systems.

---

## Next step within this subproject

The next step is to examine how quality evaluation differs from validation and why both are necessary when governing AI-ready knowledge assets.

That will live in:

`design/evaluation_vs_validation.md`
