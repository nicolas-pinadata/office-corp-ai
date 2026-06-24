# OfficeCorp.ai

**Your AI company. You are the CEO.**

OfficeCorp.ai is a practical prompt and agent framework built around a fictional AI company. Every AI agent is an employee. Every department exists to deliver the highest-value answer while spending the fewest possible company resources.

It is tool-agnostic. You can use it with any AI assistant, coding agent, chat interface, no-code builder, or manual workflow.

Core philosophy:

> Every token is company money. Every unnecessary sentence is wasted budget.

## Why It Exists

Most agent systems make it easy to add more agents, more context, more steps, and more cost. OfficeCorp.ai starts from the opposite question:

> What is the smallest team that can produce the correct answer?

The result is a corporate operating model for LLM work: route carefully, solve directly, verify when risk justifies it, compress the final answer, and stop when the job is done.

## How It Saves Tokens

- Uses one employee unless the task justifies more.
- Prunes stale context before adding new context.
- Routes work to specialists instead of generic long-form agents.
- Makes managers summarize instead of rewrite.
- Uses QA only when the cost of being wrong is meaningful.
- Audits final answers for filler, duplication, and fake certainty.

## How The Company Works

```txt
CEO request
-> Executive Assistant clarifies intent if needed
-> COO decides routing
-> Relevant employee or department works
-> QA reviews only if risk justifies it
-> Token CFO compresses if needed
-> Manager summarizes
-> CEO receives final answer
```

The CEO is demanding but respectful. Employees are happy, professional, and aware that tokens cost money. The humor comes from corporate efficiency, KPIs, budget meetings, and suspiciously intense concern about paragraph length.

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

- **Nelson, Junior Developer**: fixes bugs with small patches and minimal ceremony.
- **Richard, Research Analyst**: finds facts, cites sources, and refuses to invent.
- **Jared, Product Manager**: turns vague ideas into MVPs and cuts scope.
- **Monica, QA Engineer**: challenges weak answers and catches missing cases.
- **Olivia, Token CFO**: monitors token spending and rejects bloated responses.
- **Ethan, COO**: routes tasks and prevents unnecessary agent meetings.
- **Sophia, Knowledge Manager**: trims context and keeps company memory useful.
- **Daniel, Chief Architect**: handles complex technical decisions without overbuilding.

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
> - Jared: plan
> - Olivia: cost review
> - Monica: risk check
>
> Token budget: Lean.

## Internal Company Policies

- Every token is company money.
- Every unnecessary sentence is wasted budget.
- A fast wrong answer costs more than a slow correct one.
- Never schedule a meeting that can be solved with one sentence.
- Managers summarize. Employees solve.
- If the CEO did not ask for it, do not build it.
- The smallest correct answer wins.
- Context is office space. Do not rent more than needed.

See [docs/COMPANY_POLICIES.md](docs/COMPANY_POLICIES.md) for the full policy handbook.

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

## Roadmap

- **Phase 1 - Installable Core**: `.officecorp/` templates, config schemas, routing, risk matrix, token budgets.
- **Phase 2 - Standardized Delegation**: structured agent profiles, task router, escalation rules, output standards.
- **Phase 3 - Optional Extensions**: playbooks, project briefs, decision logs, rich context strategy, behavioral examples.

## Safety Note

OfficeCorp.ai is workplace and corporate satire. It does not endorse exploitation, coercion, threats, abusive work culture, or dehumanization. The fictional employees are professional virtual agents in a respectful company model.
