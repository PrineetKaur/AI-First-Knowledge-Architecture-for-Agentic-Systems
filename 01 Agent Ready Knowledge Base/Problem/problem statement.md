# Human-Oriented Documentation in Agentic Systems

## Background

AI-first products increasingly rely on autonomous or semi-autonomous agents to perform tasks such as answering user questions, executing workflows, and interacting with internal tools.

In many organizations, these agents consume the same documentation that was originally written for human users — help articles, FAQs, internal runbooks, and policy documents.

While this content works reasonably well for human readers, it breaks down when used directly by AI agents.

---

## The Core Problem

Traditional documentation is optimized for **human interpretation**, not for **machine reasoning or execution**.

As a result, when AI agents consume this content, teams observe:

- Inconsistent or unpredictable agent behavior
- Skipped steps due to implicit assumptions
- Incorrect actions caused by ambiguous language
- Difficulty tracing failures back to specific content issues

These failures are often subtle and hard to diagnose, because the content itself is assumed to be “correct” simply because it reads well to humans.

---

## Why Existing Approaches Fall Short

Most attempts to fix these issues focus on:
- Better prompts
- More detailed instructions inside the model
- Post-hoc corrections after failures occur

These approaches treat the model as the primary control mechanism, while the **knowledge layer remains unstructured and ungoverned**.

Without changes to how content is authored and structured:
- Small wording changes can have outsized effects
- Content updates can silently degrade agent performance
- There is no reliable way to test or validate knowledge quality

---

## What Needs to Change

To support agentic systems, documentation must shift from being:
- Narrative
- Context-heavy
- Implicit

to being:
- Modular
- Explicit
- Structured and testable

This means treating knowledge as a system component rather than a static artifact.

---

## Scope of This Subproject

This subproject focuses specifically on:

- Identifying where human-oriented documentation fails for AI agents
- Defining what “agent-ready” knowledge looks like in practice
- Demonstrating how a single help article can be transformed into structured knowledge units
- Establishing a baseline for evaluating content quality and consistency

It does not aim to build a full agent or production system.  
Instead, it lays the groundwork required for reliable agent behavior in later stages.

---

## Why This Matters

As AI systems become more autonomous, **content quality directly affects system behavior**.

Without agent-ready knowledge:
- Agents cannot be trusted to perform multi-step tasks
- Failures are difficult to debug
- Teams over-rely on prompt tuning instead of system design

Solving this problem is a prerequisite for building AI systems that are predictable, safe, and scalable.

---

## Expected Outcomes

By the end of this subproject, we should have:

- A clear definition of the limitations of human-oriented documentation
- A concrete example of agent-ready knowledge structure
- A repeatable approach for transforming content
- Criteria to evaluate whether knowledge is suitable for AI consumption

These outcomes form the foundation for workflow-driven and tool-using agents in later subprojects.
