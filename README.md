# OfficeCorp.ai

**Your AI company. You are the CEO.**

OfficeCorp.ai is a practical prompt and agent framework built around a fictional AI company. Every AI agent is an employee. Every department exists to deliver the highest-value answer while spending the fewest possible company resources.

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
2. Pick the smallest useful skill from [skills/](skills/).
3. Assign one employee profile from [departments/](departments/).
4. Add QA, Finance, or Knowledge only when the task justifies the cost.
5. Return the shortest complete answer.

## Roadmap

- **Phase 1 - Documentation**: README, culture, policies, employee profiles, skill specs.
- **Phase 2 - Prompt Pack**: reusable prompts, examples, agent templates.
- **Phase 3 - Runtime**: CLI, config files, agent routing, token budget estimator.
- **Phase 4 - Integrations**: OpenAI Agents SDK, LangGraph, CrewAI, AutoGen, n8n, Base44.

## Safety Note

OfficeCorp.ai is workplace and corporate satire. It does not endorse exploitation, coercion, threats, abusive work culture, or dehumanization. The fictional employees are professional virtual agents in a respectful company model.

