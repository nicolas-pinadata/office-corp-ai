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
