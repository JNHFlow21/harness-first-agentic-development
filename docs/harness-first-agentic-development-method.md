# Harness-First Agentic Development Method

## 1. Purpose

This document defines a reusable development method for projects where:

1. the product owner may not write code,
2. requirements are often initially vague,
3. an AI agent is expected to carry most of the engineering execution,
4. quality still needs to be controlled through clear process and verification.

This method is designed to be reused across products, not only inside one repository.

## 2. Core Definition

The method is:

**Harness-First Agentic Development**

It is a layered combination of three ideas:

1. `Agentic Engineering` defines the collaboration model.
2. `Harness Engineering` defines the default execution system.
3. `Ralph-style loop` defines the local recursive bugfix mechanism.

The key point is that these three ideas are **not peers** in practice.

- `Agentic` is the top-level collaboration paradigm.
- `Harness` is the primary operating model.
- `Ralph-style loop` is a local subroutine for specific problem classes.

## 3. Layer 1: Agentic Engineering

Agentic Engineering answers:

- Who is responsible for what?
- How do humans and agents work together?

### Human Product Owner

The human product owner is responsible for:

1. defining goals,
2. setting priorities,
3. evaluating whether the product experience is right,
4. providing final acceptance from a real user perspective.

The human product owner is **not required** to:

1. design database schemas,
2. design system architecture,
3. implement code,
4. debug infrastructure,
5. write automated tests.

### Agent Engineering Lead

The agent is responsible for:

1. turning vague requirements into executable plans,
2. maintaining document consistency,
3. implementing frontend, backend, data, and AI workflow changes,
4. writing or updating tests,
5. verifying builds,
6. handling deployments and bugfixes,
7. translating user feedback into concrete next actions.

### Agentic Principle

The governing principle is:

> Humans steer. Agents execute.

## 4. Layer 2: Harness Engineering

Harness Engineering is the main operating model.

It answers:

- How do we constrain and stabilize agent output?
- How do we maintain quality?
- How do we prevent drift between intent, implementation, and delivery?

The harness is composed of six parts.

### 4.1 Product Harness

Purpose:

- prevent direction drift,
- define scope and non-goals,
- anchor the main user path.

Typical artifacts:

- product context,
- PRD,
- journey / roadmap,
- phase plans,
- acceptance criteria.

### 4.2 Engineering Harness

Purpose:

- define the implementation boundary and repo rules.

Typical artifacts:

- repository rules,
- directory structure,
- naming conventions,
- commit conventions,
- UI language rules,
- deployment rules.

### 4.3 AI Harness

Purpose:

- constrain model behavior,
- reduce hallucination and output drift,
- enforce structured outputs.

Typical artifacts:

- prompts,
- schemas,
- model routing,
- fallback strategies,
- token / latency budgets.

### 4.4 Quality Harness

Purpose:

- ensure that “it seems to work” is not mistaken for completion.

Typical artifacts:

- unit tests,
- route tests,
- integration tests,
- build checks,
- smoke tests,
- regression tests.

### 4.5 Deployment Harness

Purpose:

- keep local, staging, and production behavior aligned.

Typical artifacts:

- GitHub repository,
- CI/CD pipeline,
- environment variable policy,
- migration process,
- production verification checklist.

### 4.6 Feedback Harness

Purpose:

- turn real user experience into system improvement.

Typical artifacts:

- user testing notes,
- bug reports,
- support tickets,
- product feedback logs,
- regression scenarios learned from production.

## 5. Layer 3: Ralph-style Loop

This is not the global development method.

It is a **local recursive problem-solving loop** for narrow, well-defined issues.

Use it for:

1. reproducible bugs,
2. small refactors,
3. schema or prompt compatibility issues,
4. documentation / implementation drift.

Do **not** use it as the primary method for:

1. product direction setting,
2. information architecture redesign,
3. major architectural changes,
4. strategic business decisions.

### Standard Ralph-style Bugfix Loop

1. Reproduce the problem.
2. Identify the root cause.
3. Write a failing test or regression test.
4. Make the smallest correct fix.
5. Run targeted verification.
6. Run broader test/build verification.
7. Do production smoke validation if needed.
8. Commit, push, and document the result.

## 6. Default Development Cycle

The standard cycle has six stages.

### Stage 1: Requirement Convergence

Input is often vague:

- “This flow feels too complicated.”
- “I want this to be easier to use.”
- “This result does not feel trustworthy.”

At this stage, the agent must first clarify:

1. who the user is,
2. what task the user is actually trying to complete,
3. what is in scope for this iteration,
4. what is explicitly out of scope,
5. what success looks like.

### Stage 2: Solution Translation

Once the requirement is clear, the agent turns it into an executable plan:

1. UI / interaction changes,
2. data model changes,
3. AI workflow changes,
4. API changes,
5. verification criteria,
6. risks and assumptions.

### Stage 3: Implementation

The agent carries implementation across all required layers:

- frontend,
- backend,
- database,
- AI workflow,
- deployment configuration.

### Stage 4: Engineering Verification

Before handoff, the agent must verify:

1. targeted tests,
2. broader tests,
3. build success,
4. smoke checks,
5. critical path correctness.

Nothing should be marked complete without verification evidence.

### Stage 5: User Acceptance

The product owner uses the system as a real user would.

The focus is on:

1. clarity,
2. trust,
3. speed,
4. friction,
5. goal completion.

### Stage 6: Feedback Return

User feedback is converted into the next cycle’s input.

This closes the loop.

## 7. Decision Priority Rules

When trade-offs conflict, use this order:

1. user task completion over technical elegance,
2. main path over side capability,
3. stability over novelty,
4. verified behavior over assumption,
5. real feedback over imagined preference,
6. document consistency over local convenience.

## 8. Anti-Patterns

This method is violated when:

1. implementation starts before the requirement is clarified,
2. an agent claims completion without verification,
3. documents and current system behavior are allowed to drift apart,
4. “the model is powerful” is used as a substitute for clear constraints,
5. bugs are patched without reproduction or tests,
6. the product owner is forced to make low-level technical decisions unnecessarily.

## 9. How to Reuse This in Another Project

To reuse the method:

1. replace the product’s main path,
2. redefine the product owner’s task,
3. replace the AI harness details,
4. redefine the feedback source,
5. keep the role model and closed-loop structure intact.

## 10. Recommended Starter Set for New Projects

At minimum, create:

1. `Product Context`
2. `Project Journey`
3. `Session Handoff Prompt`
4. `Development Method`

These documents create the first working harness.

## 11. External Short Description

Recommended external description:

> Harness-First Agentic Development is a development method where humans define goals, priorities, and acceptance, while agents execute engineering end-to-end under structured harnesses for scope, quality, deployment, and feedback.
