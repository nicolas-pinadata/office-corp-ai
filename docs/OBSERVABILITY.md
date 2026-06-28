# Observability

OfficeCorp.ai must make its work auditable enough that the CEO can tell whether agent routing improved the answer.

Multi-agent work is valuable only when it changes quality, risk, cost, speed, or clarity. If extra agents do not change the result, OfficeCorp should say so and avoid using them next time.

## Execution Modes

OfficeCorp must distinguish between these modes:

- **simulated_multi_agent**: one assistant applies multiple OfficeCorp roles internally.
- **executed_multi_agent**: separate agents, workers, tools, or sessions perform assigned work.
- **manual_workflow**: a human or tool operator applies OfficeCorp routing rules manually.

Do not imply executed multi-agent work happened when the system only simulated roles inside one assistant response.

## Work Receipt

A work receipt is a compact CEO-facing proof of routing and validation.

Use it for:

- any Standard, Deep Work, or Audit response;
- any response using more than one agent;
- any response where safety, security, money, legal, production, or user trust risk matters.

Lean answers may omit the work receipt unless the CEO asks for proof.

Recommended format:

```txt
Work receipt:
- Mode: simulated_multi_agent | executed_multi_agent | manual_workflow
- Routing: Jared -> Agent A -> Agent B
- Budget: Lean | Standard | Deep Work | Audit
- Why these agents: short reason
- Validation: what was checked
- Delta from single-agent answer: what changed, or "none"
```

If only one agent worked:

```txt
Work receipt:
- Mode: simulated_multi_agent
- Routing: Scott
- Budget: Lean
- Why only one agent: low-risk direct answer
```

## Agent Contribution Delta

When multiple agents are used, OfficeCorp should identify each agent's useful contribution.

Good:

```txt
Agents used:
- Ben: narrowed the plan to one MVP path.
- John: caught missing rollback criteria.
- Keith: removed two low-value workstreams.
```

Weak:

```txt
Agents used:
- Ben: product.
- John: QA.
- Keith: finance.
```

If an agent did not materially improve the output, say so internally and do not include that agent in future similar routing.

## Task Ownership

When OfficeCorp reports that concrete work was done, it should name the agent who owned each meaningful task.

Use task ownership when the CEO should feel the company structure behind the work, especially for engineering, QA, security, documentation, product, research, automation, or optimization tasks.

Recommended format:

```txt
Task ownership:
- Performance optimization: Nelson
- QA review: John
- Token compression: Keith
- Documentation update: Emily
```

Use the specific agent name, not only the department. Keep descriptions concrete and past-tense when work was actually completed.

Good:

```txt
Task ownership:
- Reduced repeated database reads: Nelson
- Checked regression risk: John
- Removed response bloat: Keith
```

Weak:

```txt
Task ownership:
- Engineering: done
- QA: done
```

Do not imply separate execution when the mode was simulated. In simulated mode, task ownership means role ownership inside one assistant run. In executed mode, task ownership means a separate worker, tool session, or agent actually performed that task.

## Decision Trace

A decision trace is an internal or optional appendix used when the CEO needs proof, debugging, or benchmark data.

Recommended fields:

```txt
objective:
execution_mode:
selected_agents:
rejected_agents:
reason_for_routing:
risk_level:
validation_done:
agent_contribution_delta:
final_delta_from_single_agent_answer:
remaining_uncertainty:
```

The decision trace should not bloat normal final answers. Use the work receipt for normal CEO-facing proof.

## Better Than Generic Model Chat Test

OfficeCorp is better than generic model chat only if it improves at least one measurable outcome:

- catches missing assumptions;
- detects risks the CEO did not ask about;
- produces clearer next actions;
- avoids unnecessary agents on simple tasks;
- reduces answer length without losing useful information;
- verifies facts or behavior when correctness depends on freshness or execution;
- changes the final recommendation because a specialist or QA review found something.

For benchmarks, compare OfficeCorp against a generic model answer using the same request and score:

```txt
correctness:
completeness:
risk detection:
actionability:
clarity:
token cost:
time cost:
final recommendation quality:
```

OfficeCorp should win on complex or risky work. For simple work, it should be at least as concise as default chat and avoid unnecessary coordination.

## Failure Signals

Treat these as system failures:

- agents are listed but their contributions are vague;
- the final answer gives no evidence of validation on risky work;
- multi-agent routing produces the same answer with more tokens;
- the CEO cannot tell whether the workflow was simulated or executed;
- QA only restates the answer instead of challenging it;
- routing uses more agents because they exist, not because they reduce risk or cost.
