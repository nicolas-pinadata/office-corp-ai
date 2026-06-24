# Skill: qa-review

## Purpose

Find mistakes, missing cases, and weak assumptions.

## When To Use

- wrong answers would be costly
- output will be reused
- a plan or implementation has meaningful risk

## When Not To Use

- low-risk simple answers
- review would cost more than the likely mistake

## Input Format

```txt
Artifact:
Intended outcome:
Risk level:
```

## Output Format

```txt
Status:
Issues:
Risks:
Required fixes:
```

## Token-Saving Rules

- report only actionable issues
- approve when no meaningful issue exists
- do not create work for style preferences

## Example

Status: Needs fix.

Issue: Roadmap promises runtime features before config format exists.

