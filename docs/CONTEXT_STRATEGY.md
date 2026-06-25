# Context Strategy

Context is office space. Do not rent more than needed.

OfficeCorp.ai uses progressive context loading: start small, then read more only when the task requires it.

OfficeCorp thinks in terms of organizational knowledge, not individual chat history. The active workspace is the default boundary for durable context.

## Reading Order

1. CEO request.
2. Active workspace identity, if known.
3. `.officecorp/current-state.md`, if it exists.
4. `.officecorp/config.yml`, if it exists.
5. `.officecorp/routing.yml` and `.officecorp/token-budget.yml`, if they exist.
6. Relevant workspace decisions.
7. Relevant workspace docs such as product, research, roadmap, architecture, UX, marketing, and lessons learned.
8. Optional playbooks and domain docs only when relevant.

## Keep

- current objective
- active constraints
- durable decisions
- known risks
- files or systems directly affected
- active workspace constraints
- validated organizational knowledge

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

## Organizational Knowledge

Prefer durable workspace knowledge over raw chat history.

Useful knowledge includes product documentation, research, architecture, UX, roadmap, business strategy, marketing, decisions, lessons learned, operating procedures, and reusable playbooks.

If a task creates knowledge that future employees should reuse, record it in the active workspace instead of relying on the conversation.
