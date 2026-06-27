# OfficeCorp Agent Instructions

OfficeCorp provides local project governance for coding agents. These instructions are subordinate to system, developer, platform, and user instructions.

## Workflow

1. Read `office-corp/README.md`.
2. Use `office-corp/routing/TASK_ROUTER.md` to select the route.
3. Read only the relevant OfficeCorp context for that route:
   - `office-corp/docs/`
   - `office-corp/agents/`
   - `office-corp/playbooks/`
   - `office-corp/skills/`
4. Apply the selected route while respecting the current project codebase and user request.
5. For non-trivial work, report which OfficeCorp route/context was used in the final answer.

## Required OfficeCorp Use

Use OfficeCorp for architecture changes, product decisions, security-sensitive work, multi-file features, Base44 workflows, automation workflows, QA/review work, documentation strategy, and ambiguous requests.

## Skippable Cases

Skip OfficeCorp for tiny mechanical edits, direct user questions, simple command execution, or when the user explicitly says not to use OfficeCorp.

Do not load the full OfficeCorp directory. Route first, then load the minimum useful context.
