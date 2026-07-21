# Evaluation vs Validation

## Background

Subproject 01 introduced structured knowledge that AI agents can retrieve and reason over.

Subproject 02 introduced execution workflows that guide consistent agent behavior.

Subproject 03 introduces a quality evaluation framework for assessing whether these assets are suitable for reliable AI use.

When discussing quality, two terms are often used interchangeably:

- *Evaluation*
- *Validation*

Although related, they address different questions and serve different purposes within AI-first knowledge systems.

Understanding the distinction is important for designing effective governance processes.

---

## Evaluation Measures Quality

Evaluation assesses how well a knowledge asset satisfies predefined quality criteria.

It focuses on questions such as:

* Is the knowledge complete?
* Is the workflow consistent?
* Is the terminology unambiguous?
* Are important constraints documented?
* Is the asset suitable for AI consumption?

Evaluation determines the overall quality of an asset.

For example:

```text
Knowledge Asset
        ↓
Evaluate Completeness
Evaluate Consistency
Evaluate Clarity
Evaluate Governance Readiness
        ↓
Quality Score
```

Evaluation answers:

> "How good is this asset?"

---

## Validation Verifies Requirements

Validation determines whether an asset satisfies specific rules or requirements.

Rather than assessing overall quality, validation checks whether required conditions are met.

For example:

* Are all mandatory metadata fields present?
* Does the workflow include an exit condition?
* Does the schema conform to the specification?
* Are required sections populated?

Validation typically produces binary outcomes:

* Pass
* Fail

For example:

```text
Knowledge Asset
        ↓
Check Required Metadata
Check Schema Compliance
Check Mandatory Sections
        ↓
Pass / Fail
```

Validation answers:

> "Does this asset meet the required standard?"

---

## Example

Consider the following knowledge asset:

```text
Refunds are available within 30 days of purchase.
```

### Validation

A validator may confirm:

* Required metadata exists ✓
* Schema is valid ✓
* Mandatory sections are present ✓

Result:

```text
Validation: PASS
```

### Evaluation

An evaluator may identify:

* Missing exceptions
* Ambiguous eligibility criteria
* Incomplete business constraints

Result:

```text
Completeness: 3 / 5
Clarity: 4 / 5
Governance Readiness: 3 / 5
```

The asset passes validation but still requires quality improvements.

---

## Why Both Are Necessary

Validation alone cannot determine whether an asset is suitable for production.

An asset may satisfy every required field while still being:

* Incomplete
* Ambiguous
* Difficult for AI agents to interpret
* Missing important business rules

Similarly, a high-quality asset that has not been validated may fail to meet organizational standards.

Reliable AI-ready knowledge therefore requires both processes.

---

## How They Work Together

At a high level:

```text
       Knowledge Asset
             ↓
         Validation
(Meets Required Standards?)
             ↓
         Evaluation
     (How Good Is It?)
             ↓
 Governed Knowledge Asset
```

Validation ensures compliance.

Evaluation drives continuous improvement.

Both contribute to reliable knowledge governance.

---

## Responsibilities of Each Process

| Responsibility | Validation | Evaluation |
|----------------|------------|------------|
| Required metadata | ✓ | |
| Schema compliance | ✓ | |
| Mandatory sections | ✓ | |
| Completeness | | ✓ |
| Clarity | | ✓ |
| Consistency | | ✓ |
| Governance readiness | | ✓ |
| Quality scoring | | ✓ |
| Improvement recommendations | | ✓ |

---

## System Perspective

An AI-first knowledge system typically uses both processes throughout the content lifecycle.

### Validation

Provides:

* Compliance
* Structural correctness
* Standards enforcement

### Evaluation

Provides:

* Quality measurement
* Governance insight
* Continuous improvement

Together they help organizations maintain knowledge that is both compliant and trustworthy.

---

## Key Takeaway

Validation and evaluation solve different problems.

Validation determines whether an asset satisfies required standards.

Evaluation determines how effectively that asset supports reliable AI behavior.

Both are necessary for governing AI-ready knowledge systems at scale.

```text
Validation
        +
Evaluation
        ↓
Reliable AI-Ready Knowledge
```

---

## Next step within this subproject

The next step is to examine common evaluation patterns that organizations use to assess AI-ready knowledge assets consistently across large knowledge ecosystems.

That will live in:

`design/4_evaluation_patterns.md`
