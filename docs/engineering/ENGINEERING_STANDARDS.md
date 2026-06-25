# Engineering Standards Framework

OfficeCorp engineering decisions must be grounded in authoritative standards before internal preference. This framework applies the [Knowledge Authority System](../governance/KNOWLEDGE_AUTHORITY_SYSTEM.md) to engineering work by defining which references to use, when to consult them, who owns them, and how to resolve conflicts.

This framework operates under the [Company OS](../governance/COMPANY_OS.md).

Engineering agents must pass through the [Engineering Decision Engine](../governance/ENGINEERING_DECISION_ENGINE.md) before applying this framework to implementation decisions.

Do not copy external documentation into OfficeCorp. Link to the authoritative source, summarize the applicable principle, and explain the project-specific decision.

## Decision Priority

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

Personal preference is never enough to override a higher-priority standard. Exceptions are acceptable only when they are tied to project requirements, supported platforms, risk, cost, or maintainability, and the reason is documented.

## Standards Hierarchy

| Area | Standard | Purpose | Consult when | Responsible agents |
| --- | --- | --- | --- | --- |
| Modern frontend | Google Modern Web Guidance: https://developer.chrome.com/docs/modern-web-guidance | Default reference for modern frontend architecture and browser capabilities. | Building or reviewing frontend architecture, browser-native APIs, progressive enhancement, modern CSS, browser compatibility, or frontend agent behavior. | Carla, Mia, Nelson, John |
| Web platform | MDN Web Docs: https://developer.mozilla.org/ | Primary practical reference for HTML, CSS, JavaScript, DOM APIs, and Web APIs. | Implementation details are needed for web platform behavior, syntax, browser compatibility, or API usage. Prefer MDN over blog posts. | Carla, Mia, Nelson, John |
| Accessibility | W3C WCAG 2.2 AA: https://www.w3.org/TR/WCAG22/ | Minimum accessibility target for user-facing web work. | Designing, implementing, or testing UI, navigation, forms, contrast, focus, keyboard behavior, screen reader support, and motion reduction. | Mia, Nelson, John |
| Security | OWASP Top 10 and ASVS: https://owasp.org/www-project-top-ten/ and https://owasp.org/www-project-application-security-verification-standard/ | Primary application security references. | Architecture, authentication, authorization, XSS, CSRF, CSP, secure headers, input validation, secrets, storage, sessions, and release risk. | Anton, Carla |
| Performance | web.dev performance guidance: https://web.dev/performance | Official web performance recommendations. | Core Web Vitals, rendering, loading, lazy loading, caching, images, fonts, script loading, and measured performance work. | Carla, Nelson, John |
| Testing | Playwright Best Practices: https://playwright.dev/docs/best-practices | Frontend testing philosophy and reliability guidance. | Creating or reviewing browser tests, E2E flows, accessibility assertions, visual regression, and test reliability. | John |
| Browser inspection | Chromium MCP and Browser MCP | Evidence source for browser behavior. | Visual or UX validation is required. Inspect DOM, CSS, accessibility tree, layout, responsive states, console, network, Lighthouse, and performance. | Mia, John, Nelson, Carla, Anton |
| API design | Official specifications such as OpenAPI, JSON Schema, REST constraints, and HTTP specifications. | Contract-first, interoperable API design. | Defining APIs, request and response schemas, validation, status codes, versioning, pagination, errors, or external integrations. | Carla, Nelson, Anton, John |
| Git | Conventional engineering practices, including Conventional Commits where adopted. | Clear review history and low-risk collaboration. | Creating commits, PRs, branches, release notes, or reviewing change size. | Nelson, Carla, John |
| Documentation | ADRs, RFCs, and living documentation. | Durable decision records and maintainable project knowledge. | Decisions affect architecture, security, APIs, operations, long-term maintenance, or future teams. | Carla, Emily, Nelson, John, Anton |

## Agent Responsibilities

- Carla applies the framework to architecture, API design, frontend architecture, backend boundaries, performance tradeoffs, and standards conflict resolution.
- Nelson applies the framework to scoped implementation, platform APIs, browser-native choices, backend behavior, API contracts, tests, and justified deviations.
- Mia applies the framework to UX, accessibility, responsive behavior, forms, navigation, motion, semantic structure, and browser validation.
- John applies the framework to QA, acceptance criteria, Playwright strategy, accessibility assertions, performance checks, browser compatibility, and regression risk.
- Anton applies the framework to OWASP-based security review, authentication, authorization, CSP, CSRF, XSS, input validation, storage, secrets, and secure headers.
- Gabe applies the framework to automation, integrations, API use, operational reliability, and secure workflow design.
- Emily applies the framework to ADRs, RFCs, living documentation, and durable technical knowledge.

## Standard Selection

Use the narrowest authoritative standard that answers the decision:

- For frontend architecture, start with Modern Web Guidance, then confirm implementation details with MDN and compatibility data.
- For HTML, CSS, JavaScript, DOM, or Web API syntax and behavior, use MDN first.
- For accessibility, use WCAG 2.2 AA as the minimum target.
- For security, use OWASP Top 10 for risk awareness and ASVS for verification depth.
- For performance, use web.dev and real measurements where available.
- For browser testing, use Playwright Best Practices and project test conventions.
- For browser behavior, inspect the actual browser when Browser MCP or Chromium MCP is available.
- For APIs, prefer official specifications over blog posts or framework habits.
- For documentation, use ADRs or RFCs when a decision has lasting impact.

## Conflict Resolution

When standards disagree or appear to pull in different directions:

1. Identify the decision and affected users.
2. List the relevant standards and project constraints.
3. Apply the decision priority exactly.
4. Prefer the option that satisfies the highest-priority constraints with the least complexity.
5. Document the exception if a lower-priority concern overrides a normal default.

Examples:

- A modern browser API may be rejected if the project's supported browsers do not support it.
- A performance optimization may be rejected if it harms accessibility or security.
- A simpler implementation may be rejected if it violates a security requirement.
- A framework convention may be rejected if official platform documentation shows a safer native option.

## Exception Policy

Exceptions are valid when they are explicit and justified. A good exception records:

- the standard being deviated from;
- the project constraint or risk that requires the deviation;
- alternatives considered;
- expected impact;
- owner and review requirement;
- whether the exception should be revisited later.

Unacceptable exceptions:

- "The AI suggested it."
- "This is how I usually do it."
- "A blog post recommended it" without confirming against official references.
- "It works in Chrome" when the project supports more browsers.
- "We can fix accessibility later."

## Documentation Expectations

Important engineering decisions should include a short standards note:

```txt
Standards consulted:
Decision hierarchy applied:
Decision:
Exception:
Rationale:
Follow-up:
```

Use a full ADR or RFC when the decision affects architecture, security, APIs, compatibility, operations, or long-term maintenance.

## Agent Operating Rule

Technical agents must invoke `skills/engineering-standards/` whenever they work on architecture, frontend, backend, APIs, QA, or security. The skill tells the agent which standard to select, how to resolve conflicts, and how to document deviations.
