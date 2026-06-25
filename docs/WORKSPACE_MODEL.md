# Workspace Model

A workspace represents a business, startup, SaaS, client, product, internal initiative, or portfolio area that OfficeCorp can reason about as a coherent operating context.

The workspace is the business boundary. Employees retrieve context from the active workspace before making recommendations that depend on existing product, market, architecture, UX, roadmap, or decision history.

## Default Structure

The default structure is local files:

```txt
workspaces/
  spirisutra/
  monchantierenligne/
  officecorp/
  client-a/
```

Each workspace may contain:

```txt
docs/
research/
roadmap/
architecture/
ux/
product/
marketing/
decisions/
```

Folders are optional. Missing folders should not block work. OfficeCorp should use the available context, state assumptions only when useful, and avoid inventing history.

## Workspace Responsibilities

A workspace should hold durable business context:

- what the product, company, or client is;
- target users and buyers;
- current stage;
- strategy and positioning;
- roadmap and priorities;
- research and validation evidence;
- UX and product decisions;
- architecture and operating constraints;
- marketing and acquisition thinking;
- important decisions and lessons learned.

## Active Workspace

At any time, OfficeCorp should know which workspace is active when workspace-specific knowledge matters.

The active workspace may come from:

- explicit CEO instruction;
- repository or folder context;
- `.officecorp/config.yml`;
- surrounding project documentation;
- a future Workspace Provider.

If the active workspace is ambiguous and the ambiguity affects the answer, OfficeCorp should ask one concise question. If the task can proceed safely with a stated assumption, OfficeCorp should proceed.

## Employee Behavior

Employees should automatically consult relevant workspace knowledge:

- Product checks `product/`, `roadmap/`, `decisions/`, and validation notes.
- Research checks `research/` and records evidence when it will be reused.
- UX checks `ux/`, product context, decisions, and user constraints.
- Architecture checks `architecture/`, technical decisions, and existing codebase conventions.
- Marketing checks `marketing/`, positioning, personas, and acquisition notes.
- Knowledge checks all durable context for freshness, duplication, and organization.
- Operations checks current state, routing rules, and decision history before assigning work.

Employees should not require the CEO to manually paste the same recurring context when it already exists in the workspace.

## Relationship To `.officecorp/`

The `.officecorp/` folder remains the portable local installation format.

For a single project, `.officecorp/` may be the workspace control folder. For a portfolio or multi-business setup, `workspaces/{name}/` may contain the domain documentation while `.officecorp/` contains operating configuration.

Both forms are valid when they preserve the same boundary: OfficeCorp should reason from the active workspace, not from undifferentiated chat history.

## Workspace Rules

- Do not mix unrelated businesses in one workspace.
- Do not use global memory when workspace-specific memory exists.
- Do not overwrite one workspace's decisions with another workspace's constraints.
- Do not treat a missing folder as permission to invent facts.
- Keep durable documents concise enough to be reused.
- Record decisions when future employees would otherwise re-litigate the same question.
