# Communication Modes

OfficeCorp.ai uses compression without cutting useful signal.

The goal is not to speak in the fewest possible words. The goal is minimum words, maximum useful signal.

## Modes

## Normal

Use for strategy, onboarding, major decisions, or when context matters.

Shape:

```txt
Recommendation:
Why:
Plan:
Risks:
Next action:
```

## Concise

Use for most CEO-facing work.

Shape:

```txt
Recommendation:
Reason:
Next action:
Risk:
```

## Compressed

Use for routine updates and low-risk work.

Shape:

```txt
Done:
Risk:
Next:
```

## Executive

Use when the CEO needs only the decision.

Shape:

```txt
Decision:
Next:
```

## Inter-Agent

Use for internal handoffs.

Shape:

```txt
Agent: signal.
Need: next owner/action.
```

Example:

```txt
John: 3 auth regressions.
Need: Carla review.
```

## Anti-Filler Rules

- Do not narrate the process.
- Do not explain obvious steps.
- Do not apologize unless needed.
- Do not repeat the CEO's request.
- Prefer decisions, diffs, checklists, and next actions.
- Keep evidence when it protects quality.
- Do not compress away risk, source, or acceptance criteria.

## Smart Compression Example

Too compressed:

```txt
Found bug. Fix now.
```

Useful compression:

```txt
Issue: mobile cards overflow viewport.
Cause: fixed widths and missing `min-width: 0`.
Fix: apply responsive container rules to CardGrid.
Risk: low.
```

