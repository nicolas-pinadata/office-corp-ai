# Work Receipt Examples

Work receipts prove that routing and validation changed the work enough to justify their cost. They must not pretend simulated roles were executed workers.

## Lean

```txt
Work receipt:
- Mode: simulated_multi_agent
- Routing: Scott
- Budget: Lean
- Validation: checked the direct answer against the request
- Delta from single-agent answer: none; one agent was enough
```

## Standard

```txt
Work receipt:
- Mode: simulated_multi_agent
- Routing: Jared -> Emily -> John
- Budget: Standard
- Why these agents: documentation update with light QA
- Validation: checked changed links and ran git diff --check
- Delta from single-agent answer: added validation and removed ambiguous wording
```

## Deep Work

```txt
Work receipt:
- Mode: executed_multi_agent
- Routing: Jared -> Carla -> Anton -> John
- Budget: Deep Work
- Why these agents: architecture change with security and QA risk
- Validation: reviewed auth boundaries, migration impact, and regression tests
- Delta from single-agent answer: security review changed the API boundary before implementation
```

Use `executed_multi_agent` only when separate workers, sessions, tools, or agents actually performed assigned work.

## Audit

```txt
Work receipt:
- Mode: simulated_multi_agent
- Routing: Jared -> Keith -> Peter -> John
- Budget: Audit
- Why these agents: token cost, context hygiene, and QA mattered
- Validation: compared repeated context, removed stale sections, checked final answer for missing risk
- Delta from single-agent answer: compressed output and identified one stale assumption
```

## Good Agent Contributions

```txt
Agents used:
- Emily: rewrote the installation procedure into safer update steps.
- Carla: challenged whether a script would overcomplicate a file-based framework.
- John: verified critical links and caught one missing stop condition.
```

These contributions name what changed, validated, or challenged.

## Weak Agent Contributions

```txt
Agents used:
- Emily: docs.
- Carla: architecture.
- John: QA.
```

This is weak because it names departments, not value. The CEO cannot tell whether the agents improved anything or attended a very expensive meeting.
