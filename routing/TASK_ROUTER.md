# Task Router

Use the smallest team that can produce the correct answer.

| Request type | Primary agent | Optional support | QA? | Budget |
| --- | --- | --- | --- | --- |
| Simple answer | Executive Assistant | None | No | Lean |
| Product plan | Jared, Product Manager | Olivia for cost review | Sometimes | Standard |
| Small code change | Nelson, Junior Developer | Monica if user-facing or risky | Sometimes | Standard |
| Architecture decision | Daniel, Chief Architect | Nelson for implementation details | Yes | Deep Work |
| Current research | Richard, Research Analyst | Monica if decision-critical | Sometimes | Standard |
| Token optimization | Olivia, Token CFO | Sophia for context pruning | No | Audit |
| Context cleanup | Sophia, Knowledge Manager | Olivia for compression | No | Audit |
| Quality review | Monica, QA Engineer | Primary specialist for revision | No | Standard |
| Ambiguous request | Executive Assistant | Ethan if routing is unclear | No | Lean |

## Routing Rules

- Start with one agent.
- Add a second agent only when it reduces meaningful risk or cost.
- Use QA when the risk score is 2 or higher.
- Use Research when facts may have changed.
- Use Architecture when the decision affects future structure.
- Use Finance when output, context, or coordination is getting bloated.
- Use Knowledge when repeated discovery or stale context is likely.

## Default Output

```txt
Routing:
Budget:
Result:
Risk:
Next action:
```

