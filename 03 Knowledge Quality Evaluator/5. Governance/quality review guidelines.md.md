# Quality Review Guidelines

## Background

Subproject 03 introduced a structured framework for evaluating the quality of AI-ready knowledge and execution workflow assets.

However, even with clearly defined evaluation criteria, assessments can become inconsistent if different reviewers interpret quality dimensions differently.

In production AI-first systems, evaluation must be both **repeatable** and **governed**.

These guidelines establish a consistent approach for applying the evaluation framework throughout this project.

---

## Purpose

The purpose of these guidelines is to ensure that evaluations are:

- Consistent across reviewers
- Repeatable over time
- Based on observable evidence
- Independent of individual preferences
- Useful for continuous improvement

The objective is not simply to assign scores, but to produce reliable quality assessments that support governance and informed decision-making.

---

## General Evaluation Principles

When reviewing a knowledge or workflow asset, evaluators should:

- Assess the asset against the published evaluation dimensions
- Use objective evidence whenever possible
- Avoid making assumptions beyond the documented content
- Record findings that justify each score
- Recommend improvements for any identified weaknesses

Evaluations should focus on the quality of the asset itself rather than the performance of a specific AI model.

---

## Evidence-Based Assessment

Scores should always be supported by observable evidence.

For example:

| Quality Dimension | Evidence |
| ----------------- | -------- |
| Completeness | Required workflow inputs are documented. |
| Clarity | Decision criteria are explicitly defined. |
| Consistency | Business terminology is used uniformly. |
| Governance | Ownership and review metadata are present. |

Evidence makes evaluation outcomes easier to review, reproduce, and improve.

---

## Evaluating Knowledge Assets

When reviewing structured knowledge assets, evaluators should verify:

- The primary intent is clearly defined
- Required business rules are included
- Decision logic is explicit
- Constraints are documented
- Metadata supports retrieval
- Governance information is complete

The goal is to determine whether the knowledge asset can reliably support AI reasoning.

---

## Evaluating Workflow Assets

When reviewing execution workflows, evaluators should verify:

- Workflow objectives are clearly defined
- Required inputs are complete
- Workflow states are logical
- Decision rules are unambiguous
- State transitions are valid
- Exception handling is represented
- Terminal outcomes are clearly defined

The goal is to determine whether the workflow can guide consistent agent behavior.

---

## Assigning Scores

Evaluators should use the scoring methodology defined in this subproject.

Scores should reflect:

- Observable evidence
- Overall quality
- Operational readiness

Scores should never be adjusted to achieve a desired overall rating.

The purpose of scoring is to identify strengths and improvement opportunities rather than to produce perfect results.

---

## Documenting Findings

Each evaluation should include:

- Overall score
- Dimension-level scores
- Supporting observations
- Identified risks
- Recommended improvements

This creates a documented record that can be reviewed during future evaluation cycles.

---

## Review Frequency

Knowledge assets should be evaluated:

- Before initial publication
- After significant updates
- Following major policy changes
- During scheduled governance reviews

Regular evaluations help prevent gradual declines in knowledge quality as assets evolve.

---

## Continuous Improvement

Evaluation is not a one-time activity.

Each assessment should contribute to improving future versions of the asset.

Typical improvement activities include:

- Clarifying ambiguous language
- Adding missing business rules
- Improving workflow structure
- Updating governance metadata
- Strengthening exception handling

Repeated evaluation enables knowledge systems to become more reliable over time.

---

## Key Takeaway

Effective evaluation depends on more than a scoring framework.

It also requires consistent evaluation practices.

By applying common guidelines, organizations can ensure that quality assessments remain objective, repeatable, and useful for governing AI-ready knowledge systems.

---

## Next step within this subproject

The next step is to define how quality assessments evolve alongside the assets they evaluate through structured versioning and change management.

That will live in:

`governance/evaluation_versioning.md`
