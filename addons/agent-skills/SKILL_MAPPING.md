# OfficeCorp Agent to External Skill Mapping

This mapping documents which OfficeCorp agents may use relevant skills from the optional `addyosmani/agent-skills` add-on.

External skills are optional accelerators, not dependencies. OfficeCorp agents must continue with internal skills and procedures when this add-on is disabled, missing, incomplete, or incompatible.

The user should only express the business or technical need. OfficeCorp is responsible for selecting the right agents and skills automatically.

## Agent Mapping

### Carla / Chief Architect

May use external skills for:

- architecture
- API design
- technical planning
- ADRs

### Nelson / Junior Developer

May use external skills for:

- incremental implementation
- test-driven development
- debugging

### John / QA Analyst

May use external skills for:

- code review
- testing
- acceptance criteria
- regression testing

### Anton / Security Analyst

May use external skills for:

- security hardening
- threat modeling
- secure coding review

### Mia / UX Designer

May use external skills for:

- frontend UI engineering
- accessibility
- responsive design
- web performance

### Emily / Documentation Specialist

May use external skills for:

- documentation
- ADRs
- release notes

### Gabe / Automation Specialist

May use external skills for:

- CI/CD
- workflow automation
- deployment checks

## Auto-selection Triggers

These triggers guide OfficeCorp's orchestration layer when the optional add-on is installed and enabled.

```yaml
triggers:
  build_feature:
    when:
      - "create feature"
      - "build feature"
      - "implement functionality"
      - "add module"
    agents:
      - Ben
      - Carla
      - Nelson
      - John
    external_skills:
      - planning-and-task-breakdown
      - incremental-implementation
      - test-driven-development
      - code-review-and-quality

  fix_bug:
    when:
      - "fix bug"
      - "debug"
      - "error"
      - "not working"
    agents:
      - Nelson
      - John
      - Carla
    external_skills:
      - debugging
      - test-driven-development
      - code-review-and-quality

  improve_ui:
    when:
      - "improve UI"
      - "responsive"
      - "mobile layout"
      - "accessibility"
      - "visual polish"
    agents:
      - Mia
      - John
      - Nelson
    external_skills:
      - frontend-ui-engineering
      - accessibility
      - web-performance

  security_review:
    when:
      - "security"
      - "harden"
      - "vulnerability"
      - "auth"
      - "permissions"
    agents:
      - Anton
      - Carla
      - John
    external_skills:
      - security-and-hardening
      - code-review-and-quality

  documentation:
    when:
      - "document"
      - "README"
      - "ADR"
      - "technical decision"
      - "release notes"
    agents:
      - Emily
      - Carla
    external_skills:
      - documentation-and-adrs
```

## Loading Rules

- Do not require the user to know which skill to invoke.
- Select external skills only when the user's intent justifies them.
- Do not load every external skill at once.
- Load or reference only the external skill directly relevant to the current task.
- Prefer OfficeCorp governance when external skill guidance conflicts with OfficeCorp rules.
- Fall back to OfficeCorp internal skills and procedures without failing.
