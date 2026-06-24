# Skill: context-pruning

## Purpose

Reduce context size while preserving information needed for the task.

## When To Use

- conversation history is long
- old facts are no longer relevant
- repeated discovery is happening

## When Not To Use

- all context is recent and essential
- pruning would remove required evidence

## Input Format

```txt
Current context:
Current goal:
Must preserve:
```

## Output Format

```txt
Keep:
Compress:
Drop:
Working summary:
```

## Token-Saving Rules

- preserve decisions and constraints
- compress history into durable facts
- drop stale debate after decisions are made

## Example

Keep: final project name, employee names, safety constraints.

Drop: rejected early concept.
