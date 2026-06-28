# Source Of Truth

OfficeCorp is file-based, so authority must be obvious. When two files overlap, use the most specific authoritative file below. Higher-priority system, developer, platform, and user instructions still win over OfficeCorp.

| Area | Source of truth | Supporting files |
| --- | --- | --- |
| Immutable principles | `docs/governance/OFFICECORP_CONSTITUTION.md` | `docs/governance/COMPANY_OS.md`, `docs/COMPANY_POLICIES.md` |
| Company operating model | `docs/governance/COMPANY_OS.md` | `docs/OPERATING_MODEL.md` |
| Routing | `routing/TASK_ROUTER.md` | `routing/ROUTING_RULES.md`, `routing/ROUTE_PLAYBOOKS.md` |
| Final response standards | `docs/RESPONSE_STANDARDS.md` | `docs/OBSERVABILITY.md`, `prompts/system-prompt.md` |
| Execution mode and work receipts | `docs/OBSERVABILITY.md` | `docs/WORK_RECEIPT_EXAMPLES.md` |
| Agent integration | `docs/AGENT_INTEGRATION.md` | `AGENTS.md`, `templates/agents/AGENTS.md`, `templates/agents/CLAUDE.md`, `templates/agents/cursor-rules.md` |
| Agent roster and names | `agents/README.md` | `departments/README.md`, files under `departments/` |
| Technical decision process | `docs/governance/ENGINEERING_DECISION_ENGINE.md` | `skills/engineering-decision-engine/SKILL.md` |
| Technical source authority | `docs/governance/KNOWLEDGE_AUTHORITY_SYSTEM.md` | `docs/engineering/ENGINEERING_STANDARDS.md` |
| Engineering standards | `docs/engineering/ENGINEERING_STANDARDS.md` | `skills/engineering-standards/SKILL.md`, `docs/engineering/MODERN_WEB_GUIDANCE.md` |
| Observability | `docs/OBSERVABILITY.md` | `docs/RESPONSE_STANDARDS.md` |
| Installation and updates | `docs/INSTALLATION_STRATEGY.md` | `docs/INSTALLATION_CHECK.md` |
| Memory and context | `docs/ORGANIZATIONAL_MEMORY.md` | `docs/WORKSPACE_MODEL.md` |

## Conflict Rules

- The Constitution defines durable principles; operational docs explain how to apply them.
- `TASK_ROUTER.md` decides the smallest route; `ROUTE_PLAYBOOKS.md` adds route-level execution detail without bloating the router.
- `agents/README.md` is the naming canon. Department files are role profiles grouped for navigation.
- `OBSERVABILITY.md` defines execution modes. Never imply `executed_multi_agent` when one assistant only simulated roles.
- Installation docs explain downstream use; they do not override a downstream project's own higher-priority instructions.
