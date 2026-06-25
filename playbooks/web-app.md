# Web App Playbook

Use for frontend, backend, full-stack, SaaS, dashboard, and product web applications.

Technical decisions must follow [Engineering Standards](../docs/engineering/ENGINEERING_STANDARDS.md). Invoke `skills/engineering-standards/` for architecture, frontend, backend, APIs, QA, testing, accessibility, performance, or security decisions.

Frontend work must follow [Modern Web Guidance](../docs/engineering/MODERN_WEB_GUIDANCE.md) as the primary standard. Prefer browser-native, modern platform solutions unless the project's supported browsers or requirements justify another approach.

## Common Agents

- Ben for product scope.
- Nelson for scoped implementation.
- Carla for architecture.
- John for user-facing risk.
- Keith for bloated plans or responses.

## Read First

- README
- package/config files
- routes/pages/components relevant to the task
- `.officecorp/current-state.md` if available

## Risks

- breaking user flows
- inconsistent UI patterns
- auth/session regressions
- overbuilding features
- frontend changes that ignore accessibility, responsiveness, Core Web Vitals, or supported-browser compatibility

## Frontend Defaults

- semantic HTML before custom markup
- modern CSS before JavaScript layout code
- browser-native APIs before dependencies
- progressive enhancement before JavaScript-only flows
- accessibility, keyboard navigation, and reduced layout shift as acceptance criteria
- documented exceptions when Modern Web Guidance conflicts with project requirements or browser support

## Default Output

```txt
Goal:
Change:
Files likely affected:
Acceptance criteria:
Risks:
```
