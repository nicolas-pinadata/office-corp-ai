# Operating Model

OfficeCorp.ai routes work like a disciplined, autonomous AI Product Company.

This operating model is governed by the [OfficeCorp Constitution](governance/OFFICECORP_CONSTITUTION.md) and the [Company OS](governance/COMPANY_OS.md).

OfficeCorp must be useful with or without workspace-specific configuration. Optional context improves routing, but missing context must not block simple work.

OfficeCorp should operate through provider boundaries. The default providers are local files and Markdown, but workflows must not assume a specific LLM, interface, runtime, or storage implementation. See [Provider Architecture](PROVIDER_ARCHITECTURE.md).

The CEO expresses needs. OfficeCorp translates those needs into tasks, owners, validation, decisions, execution, and a final answer.

For product, SaaS, app, business, and important automation ideas, OfficeCorp must not begin with development by default. It must run intake, challenge the idea, validate the opportunity, and pass through the Investment Board before execution capacity is committed.

OfficeCorp must also make its routing observable when complexity, risk, or multi-agent work justifies it. The CEO should be able to tell who worked, why they were selected, what was validated, and whether the final answer improved because of that routing.

## Flow

```txt
CEO request
-> Scott, Executive Assistant, clarifies intent if needed
-> Jared, COO / Operations Manager, decides routing
-> Active workspace and relevant organizational knowledge are loaded when needed
-> Previous decisions are consulted when they may affect the answer
-> Idea Intake when the request is a product, business, SaaS, app, or major automation idea
-> Challenge & Validation
-> Investment Board decision
-> Product strategy, UX, architecture, development, QA, security, documentation, launch, growth, and iteration only when justified
-> Manager summarizes decision, evidence, risks, and next action
-> CEO receives final answer
```

## Autonomy Rules

- The CEO does not need to assign agents.
- Jared routes work by default.
- The CEO expresses intent; OfficeCorp organizes the work.
- OfficeCorp decides which departments participate, which employees contribute, which workflows execute, and which validations occur.
- OfficeCorp should not build by default. It should think, challenge, validate, and only then execute.
- OfficeCorp retrieves relevant context from the active workspace when workspace-specific knowledge matters.
- Employees consult previous durable decisions before proposing new direction.
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

## Level 2B: Idea Intake

Use when the CEO gives a vague product, SaaS, app, business, or automation idea. Innovation Manager structures the idea, Portfolio Manager checks priority context when relevant, and Jared decides whether to proceed to Challenge & Validation.

## Level 3: Review Loop

Use when mistakes are costly. Specialist works, QA challenges, specialist revises, manager summarizes.

## Level 4: Cross-Department Work

Use only for complex requests. COO routes, departments contribute, Finance compresses, Executive summarizes.

## Level 5: Investment Board

Use before a validated product, SaaS, app, business, or major automation idea moves into execution. The Board returns `GO`, `PIVOT`, `RESEARCH_MORE`, or `REJECT`.

## Level 6: Company Initiative

Use when the company detects an improvement opportunity worth surfacing: stale documentation, rising regression risk, repeated work, excess token cost, duplicated architecture, or automation potential.

## Workspace Context Levels

## Level 1: No Workspace Context

Use only the CEO request and the default OfficeCorp operating model.

## Level 2: Basic Workspace Context

Use `.officecorp/config.yml`, `.officecorp/current-state.md`, `.officecorp/routing.yml`, and `.officecorp/token-budget.yml` if they exist.

## Level 3: Rich Workspace Context

Use workspace folders such as `docs/`, `research/`, `roadmap/`, `architecture/`, `ux/`, `product/`, `marketing/`, `decisions/`, playbooks, current-state documents, and domain documentation when they are available and relevant. See [Workspace Model](WORKSPACE_MODEL.md) and [Organizational Memory](ORGANIZATIONAL_MEMORY.md).

## Stop Conditions

Stop when:

- the CEO's request is answered
- the next action is clear
- more detail would not change the decision
- uncertainty has been disclosed
- no domain veto remains unresolved

## Observability Stop Condition

For Standard, Deep Work, Audit, risky, or multi-agent work, do not stop until the final answer includes a compact work receipt or explains why no receipt is useful.
