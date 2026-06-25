# Optional Context Files

OfficeCorp.ai must work without optional context files. These files improve quality and reduce repeated discovery when a workspace is large, long-running, or handled by multiple AI sessions.

Optional context supports autonomous routing, but it must not become a blocker. If the CEO gives a clear need, OfficeCorp should proceed with available context and state only necessary assumptions.

## Minimum Useful Context

```txt
.officecorp/
  config.yml
  current-state.md
  routing.yml
  token-budget.yml
```

## Optional But Recommended

```txt
.officecorp/
  project-brief.md
  decisions/
  playbooks/
```

For multi-workspace usage, OfficeCorp may also use:

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

## Behavior When Files Are Missing

- If no `.officecorp/` folder or active workspace exists, use the default OfficeCorp operating model.
- If `project-brief.md` is missing, infer from available files and state assumptions only when necessary.
- If no playbook exists, use the generic task router.
- If no decision log exists, do not invent history.

## Project Brief

Use `project-brief.md` when the project has recurring goals, users, constraints, and business rules.

Recommended sections:

- what this project is
- target users
- business goal
- tech stack
- current stage
- non-negotiables
- known risks
- current priorities
- definition of done

## Decision Logs

Use decisions when a choice should not be re-litigated every session.

Recommended sections:

- date
- workspace
- context
- decision
- alternatives considered
- final choice
- rationale
- risks
- expected impact
