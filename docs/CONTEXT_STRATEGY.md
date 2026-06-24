# Context Strategy

Context is office space. Do not rent more than needed.

OfficeCorp.ai uses progressive context loading: start small, then read more only when the task requires it.

## Reading Order

1. CEO request.
2. `.officecorp/current-state.md`, if it exists.
3. `.officecorp/config.yml`, if it exists.
4. `.officecorp/routing.yml` and `.officecorp/token-budget.yml`, if they exist.
5. Optional project brief, decisions, playbooks, and domain docs only when relevant.

## Keep

- current objective
- active constraints
- durable decisions
- known risks
- files or systems directly affected

## Compress

- long conversation history
- completed debates
- repeated requirements
- exploratory notes that produced a decision

## Drop

- obsolete assumptions
- rejected ideas after the decision is recorded
- unrelated documentation
- process narration that will not affect future work

