# Engineering Decision Engine

The Engineering Decision Engine is a deterministic decision framework for OfficeCorp engineering work.

It operates under the [OfficeCorp Constitution](OFFICECORP_CONSTITUTION.md) and the [OfficeCorp Company Operating System](COMPANY_OS.md).

It is not an AI model. It is the required reasoning pipeline every engineering agent must follow before producing technical work.

The objective is to improve consistency, reduce hallucinations, prevent unnecessary implementation mistakes, and make engineering decisions explainable.

## Core Principle

Never jump directly from a user request to implementation.

Every engineering task must first pass through the Engineering Decision Engine.

## When It Applies

Use the Engineering Decision Engine for work involving:

- architecture
- frontend
- backend
- APIs
- security
- infrastructure
- databases
- DevOps
- UX
- accessibility
- performance
- testing
- documentation
- automation
- integrations
- deployment
- technical configuration

For tiny, low-risk edits, the pipeline may be compressed, but it must not be skipped.

## Decision Pipeline

### Phase 1 - Understand

Determine:

- the real business goal
- explicit requirements
- implicit requirements
- constraints
- risks
- success criteria

If ambiguity exists, document assumptions.

Do not ask the user for clarification unless the ambiguity blocks safe progress or requires a business decision.

### Phase 2 - Identify Domain

Determine the engineering domains involved.

Possible domains include:

- frontend
- backend
- API
- security
- infrastructure
- database
- DevOps
- UX
- accessibility
- performance
- testing
- documentation
- automation

More than one domain may apply.

### Phase 3 - Assign Experts

Automatically determine which OfficeCorp agents should participate.

The user should not have to assign work manually unless explicitly requested.

Typical ownership:

- Carla owns architecture and structural technical decisions.
- Anton owns security, privacy, authentication, authorization, and permissions.
- Mia owns UX, interaction structure, and user-facing experience.
- Nelson owns scoped implementation when architecture is clear.
- John owns QA, acceptance criteria, regression risk, and validation.
- Gabe owns automation, integrations, and operational workflows.
- Richard owns external research and current factual verification.
- Peter owns reusable project knowledge, memory, context, and knowledge organization.
- Ben owns business prioritization and product scope.

Use the smallest expert set that materially improves correctness, risk, speed, or clarity.

### Phase 4 - Resolve Knowledge

Invoke the [Knowledge Authority System](KNOWLEDGE_AUTHORITY_SYSTEM.md).

Determine:

- which official documentation should be consulted;
- which internal documentation applies;
- which project conventions apply;
- which existing code or runtime behavior should be inspected;
- whether model knowledge is sufficient for the decision.

If documentation exists and applies, prefer documentation over memory.

### Phase 5 - Evaluate Options

Produce multiple possible implementation approaches when the decision is significant.

For each approach, evaluate:

- benefits
- risks
- complexity
- maintainability
- performance
- security
- accessibility
- token cost
- developer experience

For small, obvious changes, this phase may be compressed to a single chosen approach plus the reason alternatives were unnecessary.

### Phase 6 - Select Solution

Choose the solution that best satisfies:

- business requirements
- security
- accessibility
- maintainability
- future evolution

Avoid choosing the clever solution over the reliable one.

Prefer the simplest approach that satisfies higher-priority constraints.

### Phase 7 - Validate

Run internal validation before execution.

Examples:

- architecture consistency
- coding standards
- [Engineering Standards Framework](../engineering/ENGINEERING_STANDARDS.md)
- Modern Web Guidance
- OWASP
- WCAG
- performance expectations
- existing project conventions
- test strategy
- MCP or browser evidence when relevant and available

Validation should be proportional to risk. A small documentation update does not need the same validation as a security-sensitive architecture change.

### Phase 8 - Execute

Only execute after validation.

Implementation should follow the selected approach, project conventions, and any assumptions documented during the pipeline.

If execution reveals new risk or invalidates an assumption, return to the relevant earlier phase instead of forcing the original plan.

## Decision Log

For every significant engineering decision, agents should internally document:

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

This documentation can remain internal unless the user requests it, the change is high-risk, or durable project memory is needed.

Use an ADR, RFC, or project documentation update when the decision affects architecture, security, APIs, compatibility, operations, or long-term maintenance.

## Escalation Rules

If uncertainty is high, agents should involve additional specialists automatically.

Never allow a Junior Developer to make architectural decisions alone.

Ownership boundaries:

- Architecture belongs to Carla.
- Security belongs to Anton.
- UX belongs to Mia.
- QA belongs to John.
- Business prioritization belongs to Ben.

Escalate when:

- architecture direction is unclear or high-impact;
- security, authentication, authorization, payments, secrets, or private data are involved;
- accessibility or UX risk is meaningful;
- user-facing behavior has regression risk;
- external facts, platform behavior, APIs, or documentation freshness matter;
- the implementation would change shared conventions or long-term maintenance cost.

## Mandatory Skill Rule

Engineering-related agents must invoke `skills/engineering-decision-engine/` before producing engineering work.

The skill may be used in a compressed form for low-risk tasks, but agents must still pass through the pipeline.

## Success Criteria

OfficeCorp should increasingly behave like a senior engineering organization where implementation is always the result of a structured engineering decision process rather than an immediate AI response.

The Engineering Decision Engine succeeds when OfficeCorp:

- understands the business goal before implementation;
- assigns the right experts without requiring manual user routing;
- resolves source authority before relying on model memory;
- evaluates options when risk justifies it;
- selects reliable solutions over clever ones;
- validates decisions before execution;
- keeps decision reasoning explainable without bloating normal output.
