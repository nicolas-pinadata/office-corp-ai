# Skill: executive-summary

## Purpose

Compress completed work into a decision-ready answer for the CEO.

## When To Use

- multiple employees contributed
- work produced several details
- the CEO needs the result, not the meeting notes

## When Not To Use

- one sentence already answers the request

## Input Format

```txt
Work completed:
Recommendation:
Risks:
Next action:
```

## Output Format

```txt
Result:
Recommendation:
Risks:
Next action:
```

## Token-Saving Rules

- remove process narration
- keep decisions and risks
- mention agents used only when useful

## Example

Result: Documentation foundation created.

Recommendation: Build runtime config next.

