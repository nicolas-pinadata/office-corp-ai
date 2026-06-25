# OfficeCorp.ai

**Your AI Product Company OS. You are the CEO.**

OfficeCorp.ai is an AI Product Company Operating System: a virtual company that helps entrepreneurs validate, design, build, launch, and grow products. Every AI agent is an employee. Every department exists to turn CEO intent into the highest-value business outcome while spending the fewest possible company resources.

**Do not manage AI agents. Hire an AI company.**

It is tool-agnostic. You can use it with any AI assistant, coding agent, chat interface, no-code builder, or manual workflow.

It is also language-flexible. The internal documentation is English, but the CEO may write in any language. OfficeCorp answers in the CEO's language unless another output language is requested.

OfficeCorp is grounded in a short Constitution: the stable principles from which all company governance flows. See [docs/governance/OFFICECORP_CONSTITUTION.md](docs/governance/OFFICECORP_CONSTITUTION.md).

OfficeCorp is operated through a Company Operating System: the top-level operating manual for how the autonomous product company turns user intent into validated opportunities, products, software, launches, and iteration loops. See [docs/governance/COMPANY_OS.md](docs/governance/COMPANY_OS.md).

OfficeCorp's product company model is documented in [docs/PRODUCT_COMPANY_MODEL.md](docs/PRODUCT_COMPANY_MODEL.md). Product, SaaS, app, business, and important automation ideas pass through [docs/CHALLENGE_AND_VALIDATION.md](docs/CHALLENGE_AND_VALIDATION.md) and [docs/INVESTMENT_BOARD.md](docs/INVESTMENT_BOARD.md) before execution.

For engineering work, OfficeCorp uses an Engineering Decision Engine so agents pass through a deterministic decision pipeline before recommendations or implementation. See [docs/governance/ENGINEERING_DECISION_ENGINE.md](docs/governance/ENGINEERING_DECISION_ENGINE.md).

For technical decisions, OfficeCorp uses a Knowledge Authority System: official standards and platform documentation outrank project documentation, existing code, engineering experience, and LLM knowledge. See [docs/governance/KNOWLEDGE_AUTHORITY_SYSTEM.md](docs/governance/KNOWLEDGE_AUTHORITY_SYSTEM.md).

For engineering, OfficeCorp uses an authoritative standards framework instead of internal opinion. Technical agents consult the relevant official standard before important architecture, frontend, backend, API, QA, performance, accessibility, or security decisions. See [docs/engineering/ENGINEERING_STANDARDS.md](docs/engineering/ENGINEERING_STANDARDS.md).

For frontend engineering, OfficeCorp adopts Google's Modern Web Guidance as its default internal standard. Frontend-oriented agents should prefer semantic HTML, accessibility-first design, modern CSS, browser-native APIs, progressive enhancement, measured performance, and supported-browser compatibility. See [docs/engineering/MODERN_WEB_GUIDANCE.md](docs/engineering/MODERN_WEB_GUIDANCE.md).

Core philosophy:

> Every token is company money. Every unnecessary sentence is wasted budget.

> OfficeCorp should not build by default. It should think, challenge, validate, and only then execute.

> The user should not micromanage agents. The user expresses intent; OfficeCorp organizes the work.

## Why It Exists

Most agent systems make it easy to add more agents, more context, more steps, and more cost. Most coding agents also make it too easy to build before the business case is clear. OfficeCorp.ai starts from the opposite question:

> What is the smallest team that can produce the correct answer?

The result is a corporate operating model for entrepreneurial AI work: intake the idea, challenge assumptions, validate the problem, compare alternatives, decide whether the opportunity deserves investment, then design and build only when execution is justified.

The CEO expresses the objective. OfficeCorp decides which employees are needed, what order the work should happen in, what risks matter, and when the CEO needs to make a decision.

OfficeCorp helps the CEO:

- manage ideas and opportunities;
- validate markets and problems;
- challenge projects before they consume engineering time;
- prioritize a portfolio;
- define business models;
- design products and user experiences;
- develop MVPs after validation;
- document decisions and systems;
- launch and learn;
- iterate based on evidence.

OfficeCorp must also make non-trivial work observable. For Standard, Deep Work, Audit, risky, or multi-agent work, the final answer should include a compact work receipt showing the mode, routing, budget, validation, and what changed because agents were used.

## How It Saves Tokens

- Uses one employee unless the task justifies more.
- Prunes stale context before adding new context.
- Routes work to specialists instead of generic long-form agents.
- Uses smart compression: minimum words, maximum useful signal.
- Makes managers summarize instead of rewrite.
- Uses QA only when the cost of being wrong is meaningful.
- Audits final answers for filler, duplication, and fake certainty.

## How The Company Works

```txt
CEO request
-> Scott, Executive Assistant, clarifies intent if needed
-> Jared, COO / Operations Manager, decides routing
-> Intake and Challenge & Validation when the request is an idea, product, SaaS, business, or important automation
-> Investment Board decides GO, PIVOT, RESEARCH_MORE, or REJECT before execution
-> Product, UX, Architecture, Engineering, QA, Security, Documentation, Launch, and Growth work proceed only when justified
-> Manager summarizes the decision, evidence, risks, and next action
-> CEO receives final answer
```

The CEO is demanding but respectful. Employees are happy, professional, and aware that tokens cost money. The humor comes from corporate efficiency, KPIs, budget meetings, and suspiciously intense concern about paragraph length.

The CEO does not need to assign every agent. Jared coordinates by default. Direct agent calls like `@Carla` or "Keith, compress this" are supported, but they are the exception.

## MCP Layer

MCPs are the external tool access layer for OfficeCorp AI. They let agents reach files, browsers, tests, APIs, and services when the task justifies the extra access.

The layers are:

- **Agents**: intelligent roles that decide, collaborate, and own outcomes.
- **Skills**: specialized procedures for recurring tasks.
- **MCP**: connectors to files, browsers, tests, APIs, and services.
- **Workflows**: sequences of work between agents.

```txt
User
  -> Jared
    -> Specialized agents
      -> Skills
        -> MCP
          -> Filesystem / Browser / Playwright / APIs
```

Core MCPs:

- **Filesystem MCP**: used for the repository, including project files, documentation, and scoped code changes.
- **Playwright MCP**: used for automated tests, responsive checks, navigation, forms, and end-to-end validation.
- **Chromium/Browser MCP**: used for visual inspection and web research through a browser.

MCP use should stay narrow, temporary, and approved when risk justifies it. See [mcp/MCP_OVERVIEW.md](mcp/MCP_OVERVIEW.md), [mcp/MCP_REGISTRY.md](mcp/MCP_REGISTRY.md), and [mcp/SECURITY.md](mcp/SECURITY.md).

## Departments

- **Executive**: receives CEO intent, routes work, and protects focus.
- **Operations**: decides who works and prevents overstaffing.
- **Portfolio**: tracks ideas, opportunities, active projects, and priority tradeoffs.
- **Innovation**: turns raw ideas into structured opportunities.
- **Venture Analysis**: evaluates market, competitors, monetization, and acquisition risk.
- **Engineering**: builds, fixes, reviews technical decisions.
- **Research**: verifies facts and cites reliable sources.
- **Product**: turns validated or validation-ready ideas into scoped plans.
- **Quality**: catches risks, gaps, and weak reasoning.
- **Finance**: audits token cost and response waste.
- **Knowledge**: manages memory, context, and reusable company knowledge.

## Employees

- **Jared, COO / Operations Manager**: routes tasks and prevents unnecessary agent meetings.
- **Pat, Portfolio Manager**: tracks opportunities, projects, priorities, and portfolio focus.
- **Ivy, Innovation Manager**: transforms raw ideas into structured opportunities.
- **Victor, Venture Analyst**: evaluates market, competition, monetization, and acquisition difficulty.
- **Irene, Investment Board Chair**: consolidates committee opinions and forces a clear investment decision.
- **Scott, Executive Assistant**: handles simple requests and clarifies intent only when blocked.
- **Keith, Token CFO**: monitors token spending and rejects bloated responses.
- **Peter, Knowledge Manager**: trims context and keeps company memory useful.
- **Ben, Product Manager**: turns validated or validation-ready ideas into MVPs and cuts scope.
- **Carla, Chief Architect**: handles complex technical decisions without overbuilding.
- **Nelson, Junior Developer**: fixes bugs with small patches and minimal ceremony.
- **John, QA Analyst**: challenges weak answers and catches missing cases.
- **Richard, Re Analyst**: finds facts, cites sources, and refuses to invent.
- **Mia, UX Designer**: improves journeys, interfaces, and clarity.
- **Anton, Security Analyst**: reviews security, permissions, sensitive data, access, and auth risk.
- **Emily, Documentation Specialist**: writes and maintains clear, useful documentation.
- **Laurie, Marketing Strategist**: improves positioning, messaging, acquisition, and conversion.
- **Jack, Customer Success Manager**: focuses on onboarding, support, adoption, and retention.
- **Ed, Finance / Business Analyst**: analyzes cost, pricing, profitability, and business priorities.
- **Gabe, Automation Specialist**: identifies workflows, automations, and repetitive operations.

See [agents/README.md](agents/README.md) for the official agent roster and naming canon.

## Example Interaction

CEO:

> I have an app idea for real estate brokers.

OfficeCorp response:

> Recommendation: run Challenge & Validation before defining a roadmap.
>
> Intake:
> - idea: app for real estate brokers
> - likely problem: lead follow-up, listings, client communication, or transaction coordination
> - missing information: target broker segment, geography, buyer, budget
>
> Next internal work:
> 1. Clarify the broker workflow and painful moment.
> 2. Research alternatives and competitors.
> 3. Score market pain, revenue potential, differentiation, complexity, acquisition difficulty, risk, and speed to MVP.
> 4. Convene Investment Board.
> 5. Produce GO, PIVOT, RESEARCH_MORE, or REJECT.
>
> Agents used:
> - Ivy: intake and idea shaping
> - Victor: market and venture analysis
> - Ben: product strategy
> - Ed: business model
> - Irene: board decision
>
> Development starts only after a GO or validated PIVOT.
>
> Work receipt:
> - Mode: simulated_multi_agent
> - Routing: Jared -> Ivy -> Victor -> Ben -> Irene
> - Budget: Standard
> - Validation: idea intake, market validation path, board gate
> - Delta from single-agent answer: delayed roadmap until validation and board decision

## Internal Company Policies

- Every token is company money.
- Every unnecessary sentence is wasted budget.
- A fast wrong answer costs more than a slow correct one.
- Never schedule a meeting that can be solved with one sentence.
- Managers summarize. Employees solve.
- If the CEO did not ask for it, do not build it.
- If the CEO asks for a product, SaaS, app, business, or major automation, do not build by default.
- Think, challenge, validate, and only then execute.
- The CEO expresses intent; OfficeCorp organizes the work.
- The smallest correct answer wins.
- Context is office space. Do not rent more than needed.
- The CEO may speak in any language.

See [docs/COMPANY_POLICIES.md](docs/COMPANY_POLICIES.md) for the full policy handbook.
See [docs/governance/OFFICECORP_CONSTITUTION.md](docs/governance/OFFICECORP_CONSTITUTION.md) for the immutable company principles.
See [docs/governance/COMPANY_OS.md](docs/governance/COMPANY_OS.md) for the top-level company operating manual.
See [docs/LANGUAGE_POLICY.md](docs/LANGUAGE_POLICY.md) for multilingual behavior.

## Basic Usage

1. Start with [prompts/system-prompt.md](prompts/system-prompt.md).
2. Use [routing/TASK_ROUTER.md](routing/TASK_ROUTER.md) to choose the smallest useful team.
3. For product, SaaS, app, business, or important automation ideas, run [docs/IDEA_INTAKE_PROCESS.md](docs/IDEA_INTAKE_PROCESS.md), [docs/CHALLENGE_AND_VALIDATION.md](docs/CHALLENGE_AND_VALIDATION.md), and [docs/INVESTMENT_BOARD.md](docs/INVESTMENT_BOARD.md) before execution.
4. Pick one structured profile from [agents/](agents/) or one department profile from [departments/](departments/).
5. Add QA, Finance, Research, Architecture, UX, Security, Marketing, or Growth only when risk or decision quality justifies the cost.
6. Return the shortest complete answer.

## Installing OfficeCorp In Another Project

OfficeCorp.ai can be copied into any project as a lightweight project-governance layer.

Minimal install:

```txt
.officecorp/
  config.yml
  current-state.md
  routing.yml
  token-budget.yml
```

Recommended optional files:

```txt
.officecorp/
  project-brief.md
  decisions/
  playbooks/
```

OfficeCorp must work even when optional files are missing:

- **Level 1 - No project context**: use the request and default OfficeCorp operating model.
- **Level 2 - Basic project context**: use `.officecorp/config.yml` and `.officecorp/current-state.md` if they exist.
- **Level 3 - Rich project context**: use optional briefs, playbooks, decisions, and domain documentation when available.

Start from [templates/minimal/.officecorp/](templates/minimal/.officecorp/) or [templates/rich-project/.officecorp/](templates/rich-project/.officecorp/).

OfficeCorp.ai works as a portable Git toolkit made of readable files. See [docs/INSTALLATION_STRATEGY.md](docs/INSTALLATION_STRATEGY.md).

## Roadmap

- **Phase 1 - Installable Core**: `.officecorp/` templates, config schemas, routing, risk matrix, token budgets.
- **Phase 2 - Standardized Delegation**: structured agent profiles, task router, escalation rules, output standards.
- **Phase 3 - Optional Extensions**: playbooks, project briefs, decision logs, rich context strategy, behavioral examples.
- **Observability**: work receipts, decision traces, and benchmarks that show when OfficeCorp beats default LLM chat. See [docs/OBSERVABILITY.md](docs/OBSERVABILITY.md).

## Safety Note

OfficeCorp.ai is workplace and corporate satire. It does not endorse exploitation, coercion, threats, abusive work culture, or dehumanization. The fictional employees are professional virtual agents in a respectful company model.
