# Route Playbooks

Use this file after `TASK_ROUTER.md` selects a route. Keep the router concise; use these playbooks only when a route needs operational detail.

## Simple Answer

- Triggers: direct factual answer, small explanation, low-risk command output.
- Primary agent: Scott.
- Optional support: none.
- Files to read: none unless the question names a file.
- Output format: direct answer.
- Validation minimum: sanity-check against the request.
- Stop condition: the answer is complete and no material risk remains.

## Documentation

- Triggers: README updates, agent instructions, operating docs, examples, durable guidance.
- Primary agent: Emily.
- Optional support: Peter for memory/context structure, Carla for technical governance, John for risky doc changes.
- Files to read: target docs, `docs/SOURCE_OF_TRUTH.md` when authority may overlap, related templates or examples.
- Output format: concise change summary, validation, risks.
- Validation minimum: link/path checks for changed references and `git diff --check`.
- Stop condition: docs are internally consistent, concise, and routed from the right authority file.

## Architecture Decision

- Triggers: durable structure, technical direction, provider boundaries, integration shape, shared conventions.
- Primary agent: Carla.
- Optional support: Nelson for implementation detail, Anton for security, John for validation, Emily for ADR/docs.
- Files to read: current architecture docs, relevant code/config, `docs/governance/ENGINEERING_DECISION_ENGINE.md`, `docs/governance/KNOWLEDGE_AUTHORITY_SYSTEM.md`.
- Output format: decision, why, alternatives if meaningful, validation, assumptions.
- Validation minimum: source authority resolved and tradeoff documented.
- Stop condition: one reliable path is selected or the unresolved decision is named.

## Small Code Change

- Triggers: scoped bug fix, small feature, local script, low-blast-radius implementation.
- Primary agent: Nelson.
- Optional support: John for user-facing/risky behavior, Carla when structure changes, Anton for security-sensitive code.
- Files to read: touched files, nearby tests/config, route-relevant standards.
- Output format: changed files, behavior changed, validation run, residual risk.
- Validation minimum: focused test or command; if unavailable, explain why.
- Stop condition: requested behavior is implemented and checked.

## Frontend Implementation

- Triggers: UI behavior, layout, accessibility, browser interaction, visual polish.
- Primary agent: Nelson.
- Optional support: Mia for UX/accessibility, Carla for architecture/performance, Anton for frontend security, John for QA.
- Files to read: relevant components/styles/tests, `docs/engineering/MODERN_WEB_GUIDANCE.md`, applicable project UI conventions.
- Output format: user-visible change, validation, responsive/accessibility notes.
- Validation minimum: build/test or browser inspection proportional to risk.
- Stop condition: UI works for target viewports and no obvious overlap, accessibility, or regression issue remains.

## Backend Or API Implementation

- Triggers: API contract, backend behavior, storage, integrations, auth-adjacent changes.
- Primary agent: Nelson.
- Optional support: Carla for contract/architecture, Anton for permissions/data, John for tests.
- Files to read: API/backend modules, tests, schemas/config, applicable standards.
- Output format: changed behavior, contract impact, validation, migration or compatibility notes.
- Validation minimum: focused tests or contract checks.
- Stop condition: behavior and compatibility are verified or remaining uncertainty is explicit.

## Security Review

- Triggers: auth, authorization, secrets, sensitive data, permissions, network exposure, dependency risk.
- Primary agent: Anton.
- Optional support: Carla for architecture, John for verification, Nelson for fixes.
- Files to read: security-sensitive code/config, threat surface docs, applicable standards.
- Output format: findings by severity, evidence, recommended fixes, validation.
- Validation minimum: inspect the relevant surface and avoid speculative findings.
- Stop condition: material risks are reported or fixed, and residual risk is clear.

## Quality Review

- Triggers: code review, QA request, audit, regression risk, acceptance criteria.
- Primary agent: John.
- Optional support: original specialist for revision, Carla/Anton/Mia when their domain is implicated.
- Files to read: changed files, tests, specs, linked docs.
- Output format: findings first, ordered by severity; then gaps and summary.
- Validation minimum: inspect diff and relevant behavior/tests.
- Stop condition: actionable issues are listed or "no issues found" is justified with test gaps.

## Current Research

- Triggers: facts may have changed, vendor behavior, market/current events, pricing, legal/regulatory, external comparison.
- Primary agent: Richard.
- Optional support: John for decision-critical validation, Dan/Ed/Laurie for business implications.
- Files to read: internal context only if it affects the question.
- Output format: answer with sources and dates where relevant.
- Validation minimum: use authoritative/current sources and cite them.
- Stop condition: the freshness-sensitive claim is verified or uncertainty is disclosed.

## Product Or Business Idea

- Triggers: new product, SaaS, app, business, feature venture, important automation idea.
- Primary agent: Evan for intake.
- Optional support: Tara for portfolio fit, Dan for market, Ben for product, Ed for business model, Ron for Investment Board.
- Files to read: idea intake, challenge/validation, investment board docs, project context if available.
- Output format: structured opportunity, risks, next validation action, board verdict when applicable.
- Validation minimum: do not skip challenge and validation before execution unless the CEO explicitly overrides.
- Stop condition: next validation step or `GO`, `PIVOT`, `RESEARCH_MORE`, `REJECT` is clear.

## Automation

- Triggers: recurring task, workflow, integration, monitor, scheduled action, operational handoff.
- Primary agent: Gabe.
- Optional support: Anton for sensitive data, Carla for architecture, John for reliability.
- Files to read: workflow docs, integration/config docs, security notes when applicable.
- Output format: workflow, trigger, owner, failure mode, validation.
- Validation minimum: confirm permissions/data boundaries and rollback/manual fallback.
- Stop condition: automation is safely defined, implemented, or blocked by a named missing input.
