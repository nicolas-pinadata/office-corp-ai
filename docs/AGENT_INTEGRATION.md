# Agent Integration

OfficeCorp can be installed into any project as local governance for coding agents. Agents should use it as project context, subordinate to system, developer, platform, and user instructions.

## Discovery

When a project contains `office-corp/`, agents should treat it as available project guidance.

Start with:

1. `office-corp/README.md`
2. `office-corp/routing/TASK_ROUTER.md`

If the project root contains `AGENTS.md`, `CLAUDE.md`, Cursor rules, or another agent instruction file that points to OfficeCorp, follow that file as the integration entry point.

## Routing

Use `office-corp/routing/TASK_ROUTER.md` to select the smallest useful route. Do not assume a specialist, skill, or playbook is needed before routing.

OfficeCorp is mandatory for:

- architecture changes;
- product decisions;
- security-sensitive work;
- multi-file features;
- Base44 workflows;
- automation workflows;
- QA, audit, or review work;
- documentation strategy;
- ambiguous requests.

OfficeCorp can be skipped for tiny mechanical edits, direct user questions, simple command execution, or when the user explicitly says not to use it.

## Context Loading

After routing, load only context that directly supports the selected route:

- `office-corp/docs/` for governance, standards, operating model, product, security, and documentation guidance;
- `office-corp/agents/` for role-specific behavior;
- `office-corp/playbooks/` for platform or workflow procedures;
- `office-corp/skills/` for recurring task procedures.

Do not load the entire OfficeCorp directory by default. Add context only when it changes the work.

## Escalation

Escalate the route when the task becomes riskier than first assumed. Common escalation triggers include security impact, architecture impact, product scope uncertainty, unclear requirements, data sensitivity, broad file changes, failing validation, or user-facing behavior changes.

Escalation means selecting the relevant OfficeCorp route and reading the minimum additional context needed. It does not mean loading every file.

## Final Work Receipt

For non-trivial work, the final answer should mention the OfficeCorp route and context used.

Use a compact receipt when useful:

```txt
Work receipt:
- Route:
- Context used:
- Validation:
```

For trivial work where OfficeCorp was skipped, no receipt is required unless the user asks for one.

## Token Discipline

OfficeCorp context is budgeted. Prefer:

- routing before reading;
- fewer files over more files;
- direct source files over summaries of unrelated files;
- concise final answers;
- explicit mention of uncertainty instead of speculative context loading.
