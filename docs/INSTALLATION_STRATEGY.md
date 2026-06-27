# Installation Strategy

OfficeCorp.ai is a portable, file-based company framework.

Its core value is a set of readable, copyable operating files that any AI tool, LLM Provider, interface, or human can inspect, version, and modify.

## Recommended Installation Shape

Use `.officecorp/` as the portable control folder for a project or workspace:

```txt
.officecorp/
  config.yml
  current-state.md
  routing.yml
  token-budget.yml
```

Optional context may be added when it improves reuse:

```txt
.officecorp/
  project-brief.md
  decisions/
  playbooks/
```

## Agent Integration

For coding agents, install OfficeCorp as readable local project guidance:

```txt
target-project/
  AGENTS.md
  office-corp/
    README.md
    routing/
    docs/
    agents/
    playbooks/
    skills/
```

Copy `office-corp/` into the target project. Then copy or adapt the provided root `AGENTS.md` into the target project root. Other ecosystem templates are available in `templates/agents/`:

- `AGENTS.md`
- `CLAUDE.md`
- `cursor-rules.md`

Agents should treat OfficeCorp as local project guidance. The expected flow is:

1. Read `office-corp/README.md`.
2. Route the task with `office-corp/routing/TASK_ROUTER.md`.
3. Load only relevant context from `office-corp/docs`, `office-corp/agents`, `office-corp/playbooks`, and `office-corp/skills`.
4. For non-trivial work, mention the OfficeCorp route/context used in the final answer.

OfficeCorp instructions never override higher-priority system, developer, platform, or user instructions.

See `docs/AGENT_INTEGRATION.md` for the expected agent behavior.

## Workspace Structure

For portfolio or multi-business usage, organize durable knowledge by workspace:

```txt
workspaces/
  {workspace-name}/
    docs/
    research/
    roadmap/
    architecture/
    ux/
    product/
    marketing/
    decisions/
```

## Rule

The core framework must remain readable, file-based, and independent from any single LLM, runtime, interface, or vendor.
