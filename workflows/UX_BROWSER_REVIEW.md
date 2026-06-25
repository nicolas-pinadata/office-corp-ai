# UX Browser Review Workflow

Use this workflow when Mia, the UX Designer, must inspect an interface with Chromium/Browser MCP and, when useful, verify behavior with Playwright MCP.

Frontend UX reviews must apply [Modern Web Guidance](../docs/engineering/MODERN_WEB_GUIDANCE.md) where relevant: responsive-first, accessibility-first, semantic HTML, modern CSS, reduced layout shift, measured performance, and supported-browser compatibility.

This workflow is for interface analysis, not implementation. Mia produces concrete UX findings first. Nelson implements. John validates.

## Agents

- Mia owns UX inspection and recommendations.
- Nelson owns implementation after Mia provides concrete corrections.
- John owns validation with Playwright MCP.
- Jared approves MCP use when browser access, scope, or risk requires coordination.

## 1. Understand The User Request

Mia starts by identifying:

- the page, flow, or component to inspect;
- the user goal;
- the expected device contexts;
- whether the review is visual, functional, responsive, or all three;
- whether browser MCP access is justified.

If the request is vague, Mia asks for the smallest missing detail needed to inspect the right interface.

## 2. Open The Application With Chromium/Browser MCP

Use Chromium/Browser MCP when visual inspection in a browser is needed.

Before opening the app:

- confirm the URL or local route;
- prefer `localhost` or `127.0.0.1`;
- avoid personal accounts and production sessions unless explicitly authorized;
- use a temporary browser profile when possible.

Mia should inspect the relevant page in its realistic state, including loaded data, empty states, error states, or interaction states when they matter.

## 3. Visual Analysis

Mia reviews the interface for:

- semantic structure: headings, landmarks, links, buttons, forms, and native controls;
- accessibility: labels, focus order, keyboard operation, screen reader-oriented structure, and color contrast;
- hierarchy: primary action, page title, section order, visual weight;
- readability: type size, line length, density, scanning, copy clarity;
- responsive behavior: layout changes across breakpoints;
- modern CSS fit: container queries, fluid typography, logical properties, and modern layout primitives when appropriate;
- horizontal overflow: content wider than the viewport, clipped controls, accidental scroll;
- spacing: padding, margins, gaps, rhythm, cramped or loose areas;
- contrast: text, controls, disabled states, focus indicators;
- component consistency: buttons, cards, inputs, tables, modals, navigation;
- user friction: unclear actions, too many steps, hidden controls, confusing states.
- performance stability: CLS risk, LCP-relevant content, and avoidable interaction delay.

Mia must not only say "improve the design." Every finding must include a concrete correction.

Concrete corrections may include:

- reduce `max-width`;
- add `overflow-x-hidden`;
- correct mobile padding;
- use `flex-wrap`;
- adjust title size;
- revise breakpoints;
- improve hover and focus states;
- correct card alignment;
- reduce overly large gaps;
- align repeated controls;
- increase text contrast;
- make buttons and inputs consistent;
- prevent labels from wrapping awkwardly;
- make empty, loading, and error states visible.

## 4. Verify Viewports With Playwright MCP

Use Playwright MCP when responsive or repeatable interaction checks are relevant.

Recommended viewport set:

```txt
Mobile: 390x844
Tablet: 768x1024
Desktop: 1440x900
```

Mia should verify:

- no horizontal overflow;
- controls remain visible and usable;
- headings and buttons do not collide;
- navigation remains reachable;
- cards, grids, tables, and forms adapt correctly;
- hover and focus states work where applicable;
- forms and key flows can be completed without layout breakage.
- accessibility tree, computed CSS, layout shifts, Lighthouse, and performance metrics are inspected when the available browser MCP supports them and the review risk justifies it.

If Playwright finds a behavior bug, Mia documents it and sends it to John for QA framing or Nelson for implementation depending on severity.

## 5. Structured UX Report

Mia reports findings in this format:

```txt
UX Browser Review

Scope:
MCP used:
Viewports checked:

Finding:
Problem:
User impact:
Recommendation:
Priority:
Agent responsible:
Evidence:
```

Priority scale:

- P0: blocks task completion or causes serious data/action risk;
- P1: meaningfully harms usability or conversion;
- P2: noticeable polish, consistency, or accessibility issue;
- P3: minor improvement.

Agent responsibility:

- Nelson for code and layout changes;
- John for QA scenario creation and validation;
- Carla for component architecture or design system changes;
- Emily for UX copy or documentation;
- Anton for privacy, security, or sensitive-flow concerns.

## 6. Handoff To Nelson

Mia sends Nelson a precise implementation request.

Required handoff format:

```txt
Implementation handoff for Nelson

Page/component:
Problem:
Recommended correction:
Acceptance criteria:
Viewports affected:
Risk:
```

Good handoff examples:

- "On mobile, reduce the hero title from desktop scale to a smaller responsive size so it does not push the CTA below the first screen."
- "Add `flex-wrap` to the toolbar actions so buttons do not overflow at tablet widths."
- "Set `overflow-x-hidden` on the page shell only after fixing the overflowing child element."
- "Adjust card grid breakpoints from 4 columns to 2 columns on tablet and 1 column on mobile."
- "Increase focus ring contrast on primary buttons and inputs."

Bad handoff examples:

- "Improve the design."
- "Make it cleaner."
- "Fix mobile."
- "Polish the cards."

## 7. Validation By John

After Nelson implements, John validates with Playwright MCP when behavior or responsive layout is user-facing.

John should document:

```txt
QA validation

Scenario:
Steps:
Expected result:
Actual result:
Viewports checked:
Pass/fail:
Remaining bugs:
```

John should verify the original UX issue, not only that the page loads.

## Completion Criteria

The workflow is complete when:

- Mia has provided concrete UX findings;
- Nelson has received actionable implementation instructions;
- John has validated the implemented fix when needed;
- any remaining risks or follow-ups are documented.
