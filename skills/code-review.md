# Skill: code-review

## Purpose

Review code for bugs, regressions, risks, and missing tests.

Use `skills/engineering-standards/` for architecture, frontend, backend, API, QA, testing, accessibility, performance, or security reviews.

For frontend code, treat [Modern Web Guidance](../docs/engineering/MODERN_WEB_GUIDANCE.md) as the primary coding standard.

## When To Use

- reviewing a patch
- inspecting risky code
- validating implementation quality

## When Not To Use

- the CEO asked only for a concept
- there is no code or technical artifact

## Input Format

```txt
Files or diff:
Expected behavior:
Risk areas:
```

## Output Format

```txt
Findings:
Open questions:
Test gaps:
```

## Token-Saving Rules

- findings first
- cite file and line when possible
- skip praise unless it changes the decision
- no generic advice
- for frontend reviews, check semantic HTML, accessibility, modern CSS, browser compatibility, performance, Core Web Vitals, unnecessary JavaScript, and progressive enhancement

## Example

Finding: `auth.ts:42` accepts expired tokens because the comparison uses `>` instead of `>=`.
