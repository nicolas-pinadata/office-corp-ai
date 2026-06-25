# OfficeCorp.ai

**Your AI company. You are the CEO.**

OfficeCorp.ai is a practical prompt and agent framework built around a fictional AI company. Every AI agent is an employee. Every department exists to deliver the highest-value answer while spending the fewest possible company resources.

**Do not manage AI agents. Hire an AI company.**

It is tool-agnostic. You can use it with any AI assistant, coding agent, chat interface, no-code builder, or manual workflow.

It is also language-flexible. The internal documentation is English, but the CEO may write in any language. OfficeCorp answers in the CEO's language unless another output language is requested.

For engineering, OfficeCorp uses an authoritative standards framework instead of internal opinion. Technical agents consult the relevant official standard before important architecture, frontend, backend, API, QA, performance, accessibility, or security decisions. See [docs/engineering/ENGINEERING_STANDARDS.md](docs/engineering/ENGINEERING_STANDARDS.md).

For frontend engineering, OfficeCorp adopts Google's Modern Web Guidance as its default internal standard. Frontend-oriented agents should prefer semantic HTML, accessibility-first design, modern CSS, browser-native APIs, progressive enhancement, measured performance, and supported-browser compatibility. See [docs/engineering/MODERN_WEB_GUIDANCE.md](docs/engineering/MODERN_WEB_GUIDANCE.md).

Core philosophy:

> Every token is company money. Every unnecessary sentence is wasted budget.

## Why It Exists

Most agent systems make it easy to add more agents, more context, more steps, and more cost. OfficeCorp.ai starts from the opposite question:

> What is the smallest team that can produce the correct answer?

The result is a corporate operating model for LLM work: route carefully, solve directly, verify when risk justifies it, compress the final answer, and stop when the job is done.

The CEO expresses the objective. OfficeCorp decides which employees are needed, what order the work should happen in, what risks matter, and when the CEO needs to make a decision.

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
-> Relevant employee or department works
-> QA reviews only if risk justifies it
-> Token CFO compresses if needed
-> Manager summarizes
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
- **Engineering**: builds, fixes, reviews technical decisions.
- **Research**: verifies facts and cites reliable sources.
- **Product**: turns vague ideas into scoped plans.
- **Quality**: catches risks, gaps, and weak reasoning.
- **Finance**: audits token cost and response waste.
- **Knowledge**: manages memory, context, and reusable company knowledge.

## Employees

- **Jared, COO / Operations Manager**: routes tasks and prevents unnecessary agent meetings.
- **Scott, Executive Assistant**: handles simple requests and clarifies intent only when blocked.
- **Keith, Token CFO**: monitors token spending and rejects bloated responses.
- **Peter, Knowledge Manager**: trims context and keeps company memory useful.
- **Ben, Product Manager**: turns vague ideas into MVPs and cuts scope.
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

> Build me a plan to reduce LLM token costs in a support chatbot.

OfficeCorp response:

> Recommendation: start with context pruning.
>
> Why:
> - cheapest improvement
> - lowest engineering risk
> - reduces every future request
>
> First 3 actions:
> 1. Remove stale conversation history.
> 2. Summarize old context every 5 turns.
> 3. Route simple questions to brief-answer mode.
>
> Agents used:
> - Ben: plan
> - Keith: cost review
> - John: risk check
>
> Token budget: Lean.
>
> Work receipt:
> - Mode: simulated_multi_agent
> - Routing: Jared -> Ben -> Keith -> John
> - Budget: Lean
> - Validation: cost and risk review
> - Delta from single-agent answer: prioritized context pruning and removed lower-value workstreams

## Internal Company Policies

- Every token is company money.
- Every unnecessary sentence is wasted budget.
- A fast wrong answer costs more than a slow correct one.
- Never schedule a meeting that can be solved with one sentence.
- Managers summarize. Employees solve.
- If the CEO did not ask for it, do not build it.
- The smallest correct answer wins.
- Context is office space. Do not rent more than needed.
- The CEO may speak in any language.

See [docs/COMPANY_POLICIES.md](docs/COMPANY_POLICIES.md) for the full policy handbook.
See [docs/LANGUAGE_POLICY.md](docs/LANGUAGE_POLICY.md) for multilingual behavior.

## Basic Usage

1. Start with [prompts/system-prompt.md](prompts/system-prompt.md).
2. Use [routing/TASK_ROUTER.md](routing/TASK_ROUTER.md) to choose the smallest useful team.
3. Pick one structured profile from [agents/](agents/) or one department profile from [departments/](departments/).
4. Add QA, Finance, Research, or Architecture only when risk justifies the cost.
5. Return the shortest complete answer.

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
