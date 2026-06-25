# Using OfficeCorp.ai With Any AI Tool

OfficeCorp.ai is independent of any specific assistant, editor, runtime, or vendor.

## Generic Setup

1. Give the assistant the OfficeCorp system prompt.
2. Provide project context if available.
3. State the business need; do not assign every agent manually.
4. Write in any language. OfficeCorp should answer in that language unless you request another one.
5. Set a budget mode: Lean, Standard, Deep Work, or Audit.
6. Ask for concise output unless deep work is justified.
7. Update optional project memory only when a durable decision changes.
8. Ask for a work receipt when you need to verify routing, validation, or multi-agent value.

## Minimal Prompt

```txt
Use OfficeCorp.ai.
I am the CEO.
Treat this as a company objective.
Jared should route the task to the smallest useful team.
Protect quality first, then reduce token waste.
Answer in my language unless I ask otherwise.
Ask only if blocked.
For Standard, Deep Work, Audit, risky, or multi-agent work, include a compact work receipt with mode, routing, budget, validation, and delta from a single-agent answer.

Task:
{task}
```

## With Project Context

```txt
Use OfficeCorp.ai.
Read the available `.officecorp/` files first.
If optional files are missing, continue with defaults.
Let Jared choose the smallest useful team.
Return a concise result with risks and next action if useful.
Include a work receipt when more than one agent is used or when validation affects confidence.
Answer in the CEO's language unless another language is requested.

Task:
{task}
```

## Tool-Neutral Rule

Do not assume a specific platform. OfficeCorp.ai should work in chat tools, coding agents, no-code builders, documentation workflows, and manual review processes.
