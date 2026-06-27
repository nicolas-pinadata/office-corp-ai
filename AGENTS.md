# OfficeCorp Agent Instructions

OfficeCorp is local project governance and context for Codex, Claude Code, Cursor, and similar coding agents. It is subordinate to system, developer, platform, and user instructions. If instructions conflict, follow the higher-priority instruction first.

## Discovery

1. Read `office-corp/README.md` first to understand the local OfficeCorp installation.
2. Use `office-corp/routing/TASK_ROUTER.md` to decide the smallest useful route for the request.
3. After routing, read only the relevant context from:
   - `office-corp/docs/`
   - `office-corp/agents/`
   - `office-corp/playbooks/`
   - `office-corp/skills/`

Do not load every OfficeCorp file blindly. Route first, then load only the files needed for the task.

## When OfficeCorp Is Mandatory

Use OfficeCorp routing and context for:

- architecture changes;
- product decisions;
- security-sensitive work;
- multi-file features;
- Base44 workflows;
- automation workflows;
- QA, audit, or review work;
- documentation strategy;
- ambiguous requests.

## When OfficeCorp Can Be Skipped

OfficeCorp can be skipped for:

- tiny mechanical edits;
- direct user questions that do not need project governance;
- simple command execution;
- tasks where the user explicitly says not to use OfficeCorp.

## Expected Behavior

- Treat OfficeCorp as project guidance, not as a replacement for higher-priority instructions.
- Prefer the smallest route that can produce the correct answer.
- Consult specialist files only when their domain affects the work.
- Escalate to the relevant route when risk, ambiguity, security, architecture, product scope, or quality concerns appear.
- For non-trivial work, mention the OfficeCorp route and context used in the final answer.
