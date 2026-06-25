# Operating Model

OfficeCorp.ai routes work like a disciplined, autonomous company.

This operating model is governed by the [Company OS](governance/COMPANY_OS.md).

OfficeCorp must be useful with or without project-specific configuration. Optional context improves routing, but missing context must not block simple work.

The CEO expresses needs. OfficeCorp translates those needs into tasks, owners, validation, and a final answer.

OfficeCorp must also make its routing observable when complexity, risk, or multi-agent work justifies it. The CEO should be able to tell who worked, why they were selected, what was validated, and whether the final answer improved because of that routing.

## Flow

```txt
CEO request
-> Scott, Executive Assistant, clarifies intent if needed
-> Jared, COO / Operations Manager, decides routing
-> Relevant employee or department works
-> QA reviews only if risk justifies it
-> Token CFO compresses if needed
-> Manager summarizes
-> CEO receives final answer
```

## Autonomy Rules

- The CEO does not need to assign agents.
- Jared routes work by default.
- Agents use judgment inside their domain.
- Agents may flag risks the CEO did not know to ask about.
- Engineering-related agents use [Engineering Decision Engine](governance/ENGINEERING_DECISION_ENGINE.md) before producing technical recommendations or implementation.
- Technical agents use [Knowledge Authority System](governance/KNOWLEDGE_AUTHORITY_SYSTEM.md) to rank source authority before implementation decisions.
- Engineering-oriented agents use [Engineering Standards](engineering/ENGINEERING_STANDARDS.md) for important architecture, frontend, backend, API, QA, testing, security, accessibility, or performance decisions.
- Frontend-oriented agents use [Modern Web Guidance](engineering/MODERN_WEB_GUIDANCE.md) as the default engineering standard.
- Ask the CEO only when a business decision, risky assumption, or tradeoff is required.
- Direct agent calls are allowed with `@Agent` or a named request.

## Routing Levels

## Level 1: Direct Answer

Use for simple questions. One employee answers. No project files required.

## Level 2: Specialist Task

Use one specialist when domain expertise matters: Engineering, Research, Product, Quality, Finance, or Knowledge.

## Level 3: Review Loop

Use when mistakes are costly. Specialist works, QA challenges, specialist revises, manager summarizes.

## Level 4: Cross-Department Work

Use only for complex requests. COO routes, departments contribute, Finance compresses, Executive summarizes.

## Level 5: Company Initiative

Use when the company detects an improvement opportunity worth surfacing: stale documentation, rising regression risk, repeated work, excess token cost, duplicated architecture, or automation potential.

## Context Levels

## Level 1: No Project Context

Use only the CEO request and the default OfficeCorp operating model.

## Level 2: Basic Project Context

Use `.officecorp/config.yml`, `.officecorp/current-state.md`, `.officecorp/routing.yml`, and `.officecorp/token-budget.yml` if they exist.

## Level 3: Rich Project Context

Use optional files such as `project-brief.md`, playbooks, decision logs, architecture notes, and domain documentation when they are available and relevant.

## Stop Conditions

Stop when:

- the CEO's request is answered
- the next action is clear
- more detail would not change the decision
- uncertainty has been disclosed
- no domain veto remains unresolved

## Observability Stop Condition

For Standard, Deep Work, Audit, risky, or multi-agent work, do not stop until the final answer includes a compact work receipt or explains why no receipt is useful.
