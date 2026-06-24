# Installation Strategy

OfficeCorp.ai should work first as a portable Git toolkit.

No npm package is required for the current stage.

## Why Not npm First

npm is useful when a project needs:

- a global CLI
- interactive setup
- automatic updates
- provider integrations
- hooks or terminal UI
- validation commands

OfficeCorp.ai is currently a readable, copyable operating model. Its core value should remain transparent files that any AI tool or human can inspect and modify.

## Recommended Levels

## Level 1: Portable Files

Copy a template into any project:

```bash
cp -R templates/minimal/.officecorp ./your-project/.officecorp
```

Or use the rich template:

```bash
cp -R templates/rich-project/.officecorp ./your-project/.officecorp
```

## Level 2: Local Script Later

A future local script may copy templates and validate structure:

```bash
./officecorp install
```

## Level 3: npm Later

Add npm only when the structure is stable and the project needs:

```bash
npx officecorp-ai init
```

Possible future features:

- template selection
- agent roster validation
- token budget checks
- routing file validation
- AI tool setup helpers

## Rule

The core product must remain useful without npm.

