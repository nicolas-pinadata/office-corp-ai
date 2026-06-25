# agent-skills Optional Add-on

This directory documents optional compatibility with the external `addyosmani/agent-skills` repository.

The external repository is not bundled here by default. OfficeCorp remains fully functional with its internal agents, skills, routing, and governance when this add-on is not installed.

When installed and enabled, OfficeCorp agents may automatically select a relevant external skill based on the user's request. The user should not need to know which skill exists or manually invoke it.

Files:

- [INSTALL.md](INSTALL.md): optional local installation instructions.
- [SKILL_MAPPING.md](SKILL_MAPPING.md): OfficeCorp agent to external skill mapping.
- [officecorp-agent-skills.config.example.yaml](officecorp-agent-skills.config.example.yaml): example configuration.

Runtime expectations:

- `enabled` defaults to `false`.
- If enabled but the configured path is missing, OfficeCorp continues normally.
- External skills supplement internal OfficeCorp skills; they do not replace governance.
- Only the directly relevant external skill should be loaded or referenced for the current task.
