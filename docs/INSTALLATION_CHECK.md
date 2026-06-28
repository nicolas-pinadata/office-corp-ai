# Installation Check

Use this checklist after installing or updating OfficeCorp in a downstream project. It is intentionally lightweight: Markdown first, shell commands only when helpful.

## Checklist

- Root `AGENTS.md` exists.
- `office-corp/README.md` exists.
- `office-corp/routing/TASK_ROUTER.md` exists.
- Critical links point to real files.
- `office-corp/.git` is absent.
- Root `AGENTS.md` is consistent with `office-corp/AGENTS.md` or the installed template, with downstream-specific additions preserved.

## Windows PowerShell

Run from the downstream project root:

```powershell
Test-Path AGENTS.md
Test-Path office-corp\README.md
Test-Path office-corp\routing\TASK_ROUTER.md
Test-Path office-corp\.git
Test-Path office-corp\docs\INSTALLATION_STRATEGY.md
Test-Path office-corp\docs\AGENT_INTEGRATION.md
Test-Path office-corp\docs\OBSERVABILITY.md
Test-Path office-corp\docs\SOURCE_OF_TRUTH.md
Compare-Object (Get-Content AGENTS.md) (Get-Content office-corp\AGENTS.md)
```

Expected result:

- the first three commands return `True`;
- `Test-Path office-corp\.git` returns `False`;
- critical docs return `True`;
- `Compare-Object` is empty for an exact install, or shows only intentional downstream additions.

## macOS/Linux

Run from the downstream project root:

```sh
test -f AGENTS.md
test -f office-corp/README.md
test -f office-corp/routing/TASK_ROUTER.md
test ! -d office-corp/.git
test -f office-corp/docs/INSTALLATION_STRATEGY.md
test -f office-corp/docs/AGENT_INTEGRATION.md
test -f office-corp/docs/OBSERVABILITY.md
test -f office-corp/docs/SOURCE_OF_TRUTH.md
diff -u office-corp/AGENTS.md AGENTS.md
```

`diff` should be empty for an exact install. If the downstream project customizes `AGENTS.md`, keep the OfficeCorp discovery flow and review only the intentional differences.

## Critical Link Smoke Test

If `rg` is available:

```sh
rg -n "office-corp/README.md|office-corp/routing/TASK_ROUTER.md|docs/INSTALLATION_STRATEGY.md|docs/AGENT_INTEGRATION.md|docs/OBSERVABILITY.md|docs/SOURCE_OF_TRUTH.md" AGENTS.md office-corp
```

The goal is not a full documentation crawler. The goal is to catch broken install shape before the first agent tries to expense a context buffet.
