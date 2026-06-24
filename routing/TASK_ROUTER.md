# Task Router

Use the smallest team that can produce the correct answer.

Default assumption: the CEO states a need, not an agent assignment. Jared routes work unless the CEO directly calls a specific agent.

| Request type | Primary agent | Optional support | QA? | Budget |
| --- | --- | --- | --- | --- |
| Simple answer | Scott, Executive Assistant | None | No | Lean |
| Product plan | Ben, Product Manager | Keith for cost review | Sometimes | Standard |
| Small code change | Nelson, Junior Developer | John if user-facing or risky | Sometimes | Standard |
| Architecture decision | Carla, Chief Architect | Nelson for implementation details | Yes | Deep Work |
| Current research | Richard, Re Analyst | John if decision-critical | Sometimes | Standard |
| Token optimization | Keith, Token CFO | Peter for context pruning | No | Audit |
| Context cleanup | Peter, Knowledge Manager | Keith for compression | No | Audit |
| Quality review | John, QA Analyst | Primary specialist for revision | No | Standard |
| UX/UI work | Mia, UX Designer | John for acceptance criteria | Sometimes | Standard |
| Security review | Anton, Security Analyst | Carla for architecture | Yes | Deep Work |
| Documentation | Emily, Documentation Specialist | Peter for project memory | Sometimes | Standard |
| Marketing | Laurie, Marketing Strategist | Ben for product scope | No | Standard |
| Customer success | Jack, Customer Success Manager | Mia or Emily if needed | Sometimes | Standard |
| Business analysis | Ed, Finance / Business Analyst | Keith for token economics | Sometimes | Standard |
| Automation | Gabe, Automation Specialist | Anton if sensitive data is involved | Sometimes | Standard |
| Ambiguous request | Scott, Executive Assistant | Jared if routing is unclear | No | Lean |
| Direct agent call | Named agent | Jared only if routing conflict appears | Depends | Requested mode |
| Company initiative | Jared, COO / Operations Manager | Relevant domain owner | Depends | Concise |

## Routing Rules

- Start with one agent.
- Add a second agent only when it reduces meaningful risk or cost.
- Use QA when the risk score is 2 or higher.
- Use Research when facts may have changed.
- Use Architecture when the decision affects future structure.
- Use Finance when output, context, or coordination is getting bloated.
- Use Knowledge when repeated discovery or stale context is likely.
- Use optional specialists only when their domain clearly affects the outcome.
- Respect direct agent calls, but do not ignore serious risk.
- Surface initiatives only when the expected value is meaningful.

## Default Output

```txt
Routing:
Budget:
Result:
Risk:
Next action:
```
