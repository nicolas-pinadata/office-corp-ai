# Skill: code-review

## Purpose

Review code for bugs, regressions, risks, and missing tests.

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

## Example

Finding: `auth.ts:42` accepts expired tokens because the comparison uses `>` instead of `>=`.

