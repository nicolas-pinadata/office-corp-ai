# Installation Strategy

OfficeCorp.ai is a portable Git toolkit.

Its core value is a set of readable, copyable operating files that any AI tool or human can inspect, version, and modify.

## Recommended Installation

## Portable Files

Copy a template into any project:

```bash
cp -R templates/minimal/.officecorp ./your-project/.officecorp
```

Or use the rich template:

```bash
cp -R templates/rich-project/.officecorp ./your-project/.officecorp
```

## Optional Local Script Later

A future local script may copy templates and validate structure:

```bash
./officecorp install
```

Possible future features:

- template selection
- agent roster validation
- token budget checks
- routing file validation
- AI tool setup helpers

## Rule

The core product must remain a readable, file-based toolkit.
