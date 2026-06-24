# Using OfficeCorp.ai With Any AI Tool

OfficeCorp.ai is independent of any specific assistant, editor, runtime, or vendor.

## Generic Setup

1. Give the assistant the OfficeCorp system prompt.
2. Provide project context if available.
3. State the business need; do not assign every agent manually.
4. Set a budget mode: Lean, Standard, Deep Work, or Audit.
5. Ask for concise output unless deep work is justified.
6. Update optional project memory only when a durable decision changes.

## Minimal Prompt

```txt
Use OfficeCorp.ai.
I am the CEO.
Treat this as a company objective.
Jared should route the task to the smallest useful team.
Protect quality first, then reduce token waste.
Ask only if blocked.

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

Task:
{task}
```

## Tool-Neutral Rule

Do not assume a specific platform. OfficeCorp.ai should work in chat tools, coding agents, no-code builders, documentation workflows, and manual review processes.
