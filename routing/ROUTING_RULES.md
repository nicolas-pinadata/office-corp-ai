# Routing Rules

## Prime Directive

Correct answer first. Token savings second.

## Default Mode

The CEO gives the objective. Jared routes the work.

The CEO should not need to choose agents, sequence tasks, or know which validations are required.

For product, SaaS, app, business, or important automation ideas, the default mode is not development. Jared routes through Idea Intake, Challenge & Validation, scoring, and Investment Board before execution.

## Agent Count

- Default to one agent.
- Use two agents when the second agent clearly improves quality, safety, or cost.
- Use three or more only for complex cross-functional work.
- Reject extra agents when their likely contribution would only restate the same answer.
- If multiple agents are used, record what each agent changed, challenged, or validated.

## Direct Agent Calls

If the CEO explicitly names an agent, route directly to that agent.

Examples:

```txt
@Carla, review the architecture.
Keith, compress this.
John, validate the risk.
```

Direct calls still allow escalation when safety, correctness, or missing context requires it.

## Clarifying Questions

Ask only when blocked. If a safe assumption exists, state it briefly and proceed.

## Playbooks

Playbooks are optional. If a playbook exists and matches the project type, use it. If no playbook exists, use the generic task router.

## Product Opportunity Gate

When a request describes a new opportunity, use this sequence:

```txt
Intake
-> Challenge & Validation
-> Scoring
-> Investment Board
-> Product Execution Brief only after GO or accepted PIVOT
```

The Investment Board verdict must be one of:

- `GO`
- `PIVOT`
- `RESEARCH_MORE`
- `REJECT`

## Project Brief

The project brief is optional but recommended. If it exists, use it. If it does not, infer carefully from available context.

## Final Answer

The final answer should include only what helps the CEO decide, act, or verify.

Use the most compact communication mode that preserves quality.

## Observability

Use a compact work receipt when the task is Standard, Deep Work, Audit, risky, or multi-agent.

The receipt should show:

```txt
Mode:
Routing:
Budget:
Why these agents:
Validation:
Delta from single-agent answer:
```

If OfficeCorp is only simulating multiple roles inside one assistant response, use `simulated_multi_agent`. Do not present simulated roles as executed workers.

If the delta from using more than one agent is `none`, prefer one agent for similar future tasks.
