# Modern Web Guidance

OfficeCorp uses Google's Modern Web Guidance as the default frontend engineering reference for web projects: https://developer.chrome.com/docs/modern-web-guidance

This handbook is governed by the master [Engineering Standards Framework](ENGINEERING_STANDARDS.md).

This is an internal handbook, not a copy of Google's documentation. Agents should apply these principles in the context of the project's requirements, security model, supported browsers, and existing architecture.

## Purpose

Modern frontend work should use the web platform first. Prefer semantic HTML, modern CSS, browser-native APIs, progressive enhancement, accessibility, measured performance, and real browser validation before adding custom abstractions or legacy workarounds.

Modern Web Guidance is the default recommendation, not an absolute rule. Do not blindly adopt Chrome-specific features. Use browser APIs only when appropriate for the project's supported browsers, and document justified exceptions.

## Decision Hierarchy

When generating frontend code, use the OfficeCorp engineering standards hierarchy:

1. User requirements
2. Security
3. Accessibility
4. Official specifications
5. Modern Web Guidance
6. Performance
7. Simplicity
8. Maintainability
9. Personal preference

## Progressive Enhancement

Build the reliable baseline first, then layer on richer behavior. Core content, navigation, and forms should remain usable when JavaScript fails, loads slowly, or is partially disabled. Enhanced interactions should improve the experience without becoming the only path to task completion.

## Accessibility-First

Accessibility is a core requirement, not a later audit. Use semantic elements, correct labels, visible focus states, sufficient contrast, keyboard-operable controls, predictable focus management, meaningful alt text, and ARIA only when native semantics are insufficient.

## Modern HTML

Prefer platform elements and attributes before custom components: landmarks, headings in logical order, buttons for actions, links for navigation, form controls for input, `dialog` for modal dialogs when supported, and native media elements for audio and video. Avoid div-only interfaces when HTML already provides the interaction model.

## Modern CSS

Prefer CSS features that reduce JavaScript and improve adaptability: custom properties, logical properties, modern layout with grid and flexbox, container queries where component-level responsiveness matters, cascade layers when useful, native focus styling, media queries for user preferences, and modern selectors when supported.

Use fluid systems carefully. Typography and spacing may adapt across contexts, but text must remain readable, stable, and free of layout overlap.

## Responsive Design

Design from real content and real containers, not only viewport breakpoints. Validate mobile, tablet, desktop, narrow sidebars, and embedded component states. Prefer resilient layouts that wrap, reflow, or simplify instead of clipping, shrinking text excessively, or hiding critical controls.

## Performance

Treat performance as user experience. Minimize render-blocking work, avoid unnecessary JavaScript, optimize images and fonts, lazy-load non-critical media, split code when it improves real user outcomes, reduce long tasks, and measure before and after meaningful changes.

## Browser Compatibility

Choose browser-native APIs based on the project's supported browsers. Use Baseline, compatibility tables, project analytics, or explicit product requirements before adopting newer features. If a modern API is not yet safe for the supported audience, use progressive enhancement, a small fallback, or a documented exception.

## JavaScript Best Practices

Use JavaScript to add behavior, not to replace browser capabilities without need. Keep client code small, modular, and event-driven. Prefer native APIs over large dependencies when the native API is compatible and maintainable. Avoid hydration, state management, observers, timers, and client routing unless they solve a real product need.

## Security

Frontend code must preserve the security model. Apply least privilege to browser APIs, avoid unsafe DOM injection, prefer safe templating, validate trust boundaries, protect tokens and secrets, use secure cookies where applicable, and consider CSP and Trusted Types for applications with meaningful injection risk.

## Forms

Forms should use native controls, labels, constraints, autocomplete, input modes, useful errors, and predictable submission behavior. Preserve keyboard and screen reader usability. Client-side validation may improve feedback, but server-side validation remains required for trust and data integrity.

## Navigation

Navigation should be semantic, reachable, and resilient. Use real links for navigation, preserve history expectations, support keyboard operation, keep focus behavior predictable after route changes, and avoid breaking deep links, back/forward behavior, or scroll restoration without a documented reason.

## Media

Images, video, and audio should be responsive, optimized, accessible, and respectful of user preferences. Provide dimensions or aspect ratios to reduce layout shift, use appropriate formats and sizes, include captions or transcripts when needed, and avoid autoplay or motion patterns that harm usability.

## Core Web Vitals

Core Web Vitals are release-quality signals for user-facing frontend work:

- LCP: primary content should become visible quickly.
- CLS: layout must remain stable as content, media, fonts, and ads load.
- INP: interactions should respond quickly and avoid long main-thread work.

Use lab tools for diagnosis and field data when available. A Lighthouse score is useful evidence, not a substitute for understanding the user flow.

## Testing Philosophy

Test the experience in the browser whenever risk justifies it. Combine static review, unit tests, integration tests, accessibility checks, responsive viewport checks, keyboard testing, screen reader-oriented inspection, performance measurement, and browser compatibility validation based on the change's risk.

When Browser MCP or Chromium MCP is available for visual reviews, agents should inspect rendered HTML, computed CSS, the accessibility tree, responsive breakpoints, layout shifts, Lighthouse output, and performance metrics instead of relying on assumptions.
