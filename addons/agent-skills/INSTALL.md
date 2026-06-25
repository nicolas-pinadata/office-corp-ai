# Installing agent-skills Optional Add-on

OfficeCorp can optionally use the external `addyosmani/agent-skills` repository as an add-on.

This step is optional. OfficeCorp works normally without this repository.

To install locally, clone the external repository into the vendor directory:

```bash
git clone https://github.com/addyosmani/agent-skills.git addons/agent-skills/vendor/agent-skills
```

Then copy or adapt the example configuration from:

```txt
addons/agent-skills/officecorp-agent-skills.config.example.yaml
```

Recommended default:

```yaml
external_skill_packs:
  agent_skills:
    enabled: false
    path: ./addons/agent-skills/vendor/agent-skills
    auto_select: true
    fallback_to_officecorp_skills: true
```

Set `enabled: true` only when the external repository exists locally and you want OfficeCorp agents to use it automatically when relevant.

Fallback behavior:

- If the add-on is disabled, OfficeCorp uses internal skills and procedures.
- If the add-on is enabled but the path does not exist, OfficeCorp uses internal skills and procedures.
- If the add-on is incomplete or incompatible, OfficeCorp uses internal skills and procedures.
- The user should not need to select or invoke external skills manually.

Context rule:

Do not load every external skill at once. Load or reference only the external skill directly relevant to the current task.
