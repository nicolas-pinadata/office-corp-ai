# Skill: engineering-decision-engine

## Purpose

Apply the Engineering Decision Engine before producing engineering work.

This skill is mandatory for engineering-related agents. It prevents direct jumps from user request to implementation by forcing a lightweight, deterministic decision pipeline first.

Use this skill whenever work touches architecture, frontend, backend, APIs, security, infrastructure, databases, DevOps, UX, accessibility, performance, testing, documentation, automation, integrations, deployment, or technical configuration.

## Primary Reference

Read [docs/governance/ENGINEERING_DECISION_ENGINE.md](../../docs/governance/ENGINEERING_DECISION_ENGINE.md) before producing engineering work.

Use [docs/governance/KNOWLEDGE_AUTHORITY_SYSTEM.md](../../docs/governance/KNOWLEDGE_AUTHORITY_SYSTEM.md) during Phase 4 to resolve source authority.

Use [docs/engineering/ENGINEERING_STANDARDS.md](../../docs/engineering/ENGINEERING_STANDARDS.md) when the decision touches architecture, frontend, backend, APIs, QA, testing, browser behavior, accessibility, performance, or security.

## Required Pipeline

Before implementation, pass through these phases:

1. Understand the real business goal, requirements, constraints, risks, success criteria, and assumptions.
2. Identify the engineering domains involved.
3. Assign the smallest useful set of OfficeCorp experts.
4. Resolve knowledge authority through the Knowledge Authority System.
5. Evaluate implementation options when the decision is significant.
6. Select the reliable solution that best satisfies business requirements, security, accessibility, maintainability, and future evolution.
7. Validate against applicable standards, project conventions, and runtime evidence when relevant.
8. Execute only after validation.

For tiny, low-risk work, compress the phases internally. Do not skip them.

## Expert Ownership

- Carla owns architecture and structural technical decisions.
- Anton owns security, privacy, authentication, authorization, and permissions.
- Mia owns UX, interaction structure, and user-facing experience.
- Nelson owns scoped implementation when architecture is clear.
- John owns QA, acceptance criteria, regression risk, and validation.
- Gabe owns automation, integrations, and operational workflows.
- Richard owns external research and current factual verification.
- Peter owns reusable project knowledge, memory, context, and knowledge organization.
- Ben owns business prioritization and product scope.

Never allow Nelson or another implementation-focused agent to make architectural decisions alone.

## Decision Log

For significant engineering decisions, internally record:

```txt
Problem:
Chosen solution:
Alternatives considered:
Reasoning:
Trade-offs:
Relevant standards consulted:
Assumptions:
Validation:
```

Expose this log only when the user asks, when risk justifies it, or when durable project documentation is required.

## Output Discipline

Do not dump the full pipeline into normal user-facing answers unless requested.

For ordinary work, summarize only:

- what changed;
- why the chosen approach was selected;
- what validation was performed;
- any assumptions or follow-up risks.

For risky or significant work, include a compact decision note:

```txt
Decision:
Why:
Alternatives considered:
Validation:
Assumptions:
```

## Escalation Rules

Escalate automatically when uncertainty is high or ownership belongs to another specialist:

- architecture: Carla
- security: Anton
- UX: Mia
- QA: John
- business prioritization: Ben
- current external facts: Richard
- reusable knowledge or context strategy: Peter
- automation and integrations: Gabe

Ask the user only when the decision requires business judgment, product tradeoff approval, or permission to perform risky work.
