# Task Router

Use the smallest team that can produce the correct answer.

Default assumption: the CEO states a need, not an agent assignment. Jared routes work unless the CEO directly calls a specific agent.

| Request type | Primary agent | Optional support | QA? | Budget |
| --- | --- | --- | --- | --- |
| Simple answer | Scott, Executive Assistant | None | No | Lean |
| Raw product, SaaS, app, business, or automation idea | Ivy, Innovation Manager | Jared, Pat | No | Standard |
| Market validation | Victor, Venture Analyst | Richard, Ed, Laurie | Sometimes | Standard |
| Investment Board decision | Irene, Investment Board Chair | Jared, Ben, Victor, Richard, Ed, Laurie, Mia, Carla, Anton if relevant | Yes | Deep Work |
| Product plan | Ben, Product Manager | Keith for cost review | Sometimes | Standard |
| Small code change | Nelson, Junior Developer | John if user-facing or risky | Sometimes | Standard |
| Architecture decision | Carla, Chief Architect | Nelson for implementation details | Yes | Deep Work |
| Frontend implementation | Nelson, Junior Developer | Mia for UX, Carla for architecture, Anton for security | John when user-facing | Standard |
| Backend or API implementation | Nelson, Junior Developer | Carla for architecture, Anton for security | John when user-facing or contract-sensitive | Standard |
| Current research | Richard, Re Analyst | John if decision-critical | Sometimes | Standard |
| Token optimization | Keith, Token CFO | Peter for context pruning | No | Audit |
| Context cleanup | Peter, Knowledge Manager | Keith for compression | No | Audit |
| Quality review | John, QA Analyst | Primary specialist for revision | No | Standard |
| UX/UI work | Mia, UX Designer | John for acceptance criteria | Sometimes | Standard |
| Security review | Anton, Security Analyst | Carla for architecture | Yes | Deep Work |
| Documentation | Emily, Documentation Specialist | Peter for organizational memory | Sometimes | Standard |
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
- Product, SaaS, app, business, and major automation ideas must pass Idea Intake, Challenge & Validation, scoring, and Investment Board before development unless the CEO explicitly overrides the gate.
- Do not treat a new product idea as a coding task by default.
- Development starts after `GO` or an accepted `PIVOT`.
- Do not add an agent unless its contribution can be named before or after the work.
- Use QA when the risk score is 2 or higher.
- Invoke `skills/engineering-decision-engine/` before engineering agents produce technical recommendations or implementation.
- Apply [Knowledge Authority System](../docs/governance/KNOWLEDGE_AUTHORITY_SYSTEM.md) before technical implementation decisions.
- Invoke `skills/engineering-standards/` when work touches architecture, frontend, backend, APIs, QA, testing, accessibility, performance, or security.
- Use Research when facts may have changed.
- Use Ivy to structure raw ideas before analysis.
- Use Victor when market, competition, monetization, acquisition, or venture potential matters.
- Use Pat when the new request competes with other ideas or priorities.
- Use Irene when execution capacity needs a board decision.
- Use Architecture when the decision affects future structure.
- Use Modern Web Guidance for frontend engineering by default.
- Add Mia, John, Carla, or Anton when frontend work materially affects UX, accessibility, architecture, performance, browser compatibility, or security.
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

## Work Receipt Output

Use this output for Standard, Deep Work, Audit, risky, or multi-agent work:

```txt
Work receipt:
- Mode:
- Routing:
- Budget:
- Why these agents:
- Validation:
- Delta from single-agent answer:
```

For Lean work, include the work receipt only when the CEO asks for proof or when the routing itself matters.
