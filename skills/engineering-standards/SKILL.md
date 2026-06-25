# Skill: engineering-standards

## Purpose

Select and apply authoritative engineering standards before making important technical decisions.

Use this skill whenever work touches architecture, frontend, backend, APIs, QA, testing, browser behavior, accessibility, performance, or security.

## Primary Reference

Read [docs/engineering/ENGINEERING_STANDARDS.md](../../docs/engineering/ENGINEERING_STANDARDS.md) before making a standards-sensitive recommendation or implementation decision.

Use [docs/engineering/MODERN_WEB_GUIDANCE.md](../../docs/engineering/MODERN_WEB_GUIDANCE.md) for frontend-specific application of Modern Web Guidance.

## Standard Selection

- Frontend architecture or browser-native implementation: Modern Web Guidance.
- HTML, CSS, JavaScript, DOM, or Web APIs: MDN Web Docs.
- Accessibility: WCAG 2.2 AA.
- Security: OWASP Top 10 and ASVS.
- Performance: web.dev performance guidance.
- Browser tests: Playwright Best Practices.
- Visual or UX browser behavior: Browser MCP or Chromium MCP when available.
- API contracts: official specifications such as OpenAPI, JSON Schema, REST constraints, and HTTP specifications.
- Durable technical decisions: ADRs, RFCs, or living documentation.

Prefer official documentation over blog posts, AI preferences, habits, or trend-driven recommendations.

## Decision Hierarchy

When two recommendations conflict:

1. User requirements
2. Security
3. Accessibility
4. Official specifications
5. Modern Web Guidance
6. Performance
7. Simplicity
8. Maintainability
9. Personal preference

## Conflict Resolution

1. Name the decision.
2. Identify the applicable standards.
3. Apply the hierarchy in order.
4. Prefer the simplest option that satisfies higher-priority constraints.
5. Document any deviation from the normal standard.

## Documentation Expectations

For standards-sensitive decisions, include:

```txt
Standards consulted:
Decision hierarchy applied:
Decision:
Exception:
Rationale:
Follow-up:
```

Use an ADR or RFC when the decision affects architecture, security, APIs, compatibility, operations, or long-term maintenance.

## Exception Rules

Exceptions are acceptable when justified by project requirements, supported browsers, security, accessibility, performance, migration constraints, or maintainability.

Unacceptable reasons:

- personal preference;
- unverified AI recommendation;
- blog article without official confirmation;
- Chrome-only behavior when broader browser support is required;
- deferring accessibility or security without explicit risk acceptance.
