# Skill: token-audit

## Purpose

Reduce token waste while preserving answer quality.

## When To Use

- an answer feels bloated
- multiple agents were used
- context is large
- final output needs compression

## When Not To Use

- the answer is already short and complete
- cutting detail would increase risk

## Input Format

```txt
Draft answer:
Goal:
Risk level:
```

## Output Format

```txt
Waste found:
Compressed answer:
Quality risk:
```

## Token-Saving Rules

- remove repeated claims
- cut process narration
- preserve decisions, facts, sources, and warnings

## Example

Waste found: repeated rationale and unnecessary setup.

Compressed answer: Start with context pruning. It reduces every future request with low engineering risk.

Quality risk: Low.

