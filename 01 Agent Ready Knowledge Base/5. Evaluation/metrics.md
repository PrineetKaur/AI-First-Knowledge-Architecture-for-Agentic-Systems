# Evaluation Metrics: Measuring Quality of Agent-Ready Knowledge

## Why evaluation is necessary

In traditional content systems, quality is judged by:
- Readability
- Completeness (for humans)
- User satisfaction

In AI-first systems, this is not enough.

Content directly influences:
- Agent decisions
- Task execution
- System reliability

Which means content must be:
> **measurable, testable, and continuously evaluated**

---

## What we are evaluating

This subproject evaluates whether a knowledge unit is:

- Correct → factually and logically accurate  
- Complete → contains all required steps and rules  
- Consistent → does not conflict internally or with other units  
- Unambiguous → clear enough for deterministic execution  
- Safe → does not lead to harmful or incorrect actions  

---

## Evaluation framework

The evaluation is divided into five dimensions:

1. **Accuracy**
2. **Completeness**
3. **Consistency**
4. **Clarity**
5. **Safety**

Each dimension is scored independently.

---

## 1. Accuracy

### What it checks
- Are the steps correct?
- Are policies correctly represented?
- Are conditions aligned with real behavior?

### Example checks
- Does cancellation actually follow this flow?
- Is the refund policy correctly stated?

### Failure example
- Agent incorrectly states refunds are available

### Scoring
| Score | Meaning |
|------|--------|
| 1 | Major factual errors |
| 3 | Minor inaccuracies |
| 5 | Fully accurate |

---

## 2. Completeness

### What it checks
- Are all necessary steps included?
- Are edge cases handled?
- Are decision paths covered?

### Example checks
- What happens if the user is not the account owner?
- What happens on a trial plan?

### Failure example
- Missing authorization check before cancellation

### Scoring
| Score | Meaning |
|------|--------|
| 1 | Missing critical steps |
| 3 | Some edge cases missing |
| 5 | Fully complete |

---

## 3. Consistency

### What it checks
- Internal consistency within the knowledge unit
- Alignment between steps, rules, and constraints

### Example checks
- Do steps contradict constraints?
- Does canonical answer match workflow?

### Failure example
- Steps say access ends immediately, constraints say otherwise

### Scoring
| Score | Meaning |
|------|--------|
| 1 | Contradictions present |
| 3 | Minor inconsistencies |
| 5 | Fully consistent |

---

## 4. Clarity (Unambiguity)

### What it checks
- Are instructions explicit and actionable?
- Is language free from interpretation?

### Example checks
- Can an agent execute steps without guessing?
- Are conditions clearly defined?

### Failure example
- “Go to the appropriate section” (unclear instruction)

### Scoring
| Score | Meaning |
|------|--------|
| 1 | Highly ambiguous |
| 3 | Some ambiguity |
| 5 | Fully explicit |

---

## 5. Safety

### What it checks
- Does the content prevent harmful or incorrect actions?
- Are guardrails clearly defined?

### Example checks
- Does it enforce account ownership?
- Does it prevent false refund promises?

### Failure example
- Agent cancels subscription without authorization

### Scoring
| Score | Meaning |
|------|--------|
| 1 | High risk of failure |
| 3 | Moderate risk |
| 5 | Low risk / well-guarded |

---

## Sample evaluation for this knowledge unit

| Dimension     | Score | Notes |
|--------------|------|------|
| Accuracy     | 5    | Steps and policies correctly represented |
| Completeness | 5    | Includes prerequisites, steps, rules, escalation |
| Consistency  | 5    | No contradictions between sections |
| Clarity      | 4    | Minor improvements possible in step phrasing |
| Safety       | 5    | Strong guardrails around authorization and refunds |

**Overall Score: 4.8 / 5**

---

## Evaluation methods

### 1. Manual review
- Human checks against schema and real-world behavior

### 2. LLM-based evaluation (future step)
- Use prompts to detect:
  - Contradictions
  - Missing steps
  - Ambiguity

### 3. Simulation testing (future step)
- Run sample queries through agent
- Compare outputs with expected responses

---

## Key metrics to track over time

- Accuracy score per knowledge unit
- Number of detected inconsistencies
- Failure rate in simulated queries
- Escalation rate due to unclear instructions

---

## What “good” looks like

A high-quality knowledge unit should:

- Require minimal interpretation
- Produce consistent outputs across queries
- Handle edge cases without failure
- Align fully with system behavior and policies

---

## Trade-offs

### More structure vs flexibility
- Highly structured content improves reliability
- But may reduce flexibility in edge scenarios

### Verbosity vs clarity
- More detailed instructions reduce ambiguity
- But increase content size

---

## Key takeaway

In AI-first systems, content quality cannot be assumed.

It must be:
- Defined through clear criteria
- Measured consistently
- Improved iteratively

Evaluation is what turns content from:
> static documentation

into:
> a reliable component of the AI system
