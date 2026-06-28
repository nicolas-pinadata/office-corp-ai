# Ready-To-Use Codex Prompts

These prompts assume OfficeCorp is installed in the target repository. They are short enough to paste directly into Codex.

## Audit OfficeCorp

```txt
Use OfficeCorp routing. Audit this OfficeCorp installation for clarity, broken internal links, routing drift, and places where simulated multi-agent work could be confused with executed work. Read README.md and routing/TASK_ROUTER.md first, then only relevant files. Return findings, fixes recommended, validation performed, and a compact work receipt.
```

## Update OfficeCorp In A Downstream Project

```txt
Use OfficeCorp routing. Update the local office-corp/ package from the upstream OfficeCorp source using a temporary clone, excluding .git. Preserve intentional downstream AGENTS.md additions. Review the diff before finalizing, run the installation check, and summarize changed files, validation, risks, and a compact work receipt.
```

## Code Review With OfficeCorp

```txt
Use OfficeCorp routing for a code review. Read README.md and routing/TASK_ROUTER.md first, then inspect the diff and only the files needed. Lead with findings by severity and file/line references. Include test gaps, residual risk, and a compact work receipt.
```

## Documentation Strategy

```txt
Use OfficeCorp routing as a documentation strategy task. Identify the source of truth, duplication risk, missing reader paths, and stale links. Keep recommendations concise and file-based. If you edit docs, run link/path smoke checks and git diff --check. End with a compact work receipt.
```

## Frontend Implementation

```txt
Use OfficeCorp routing for frontend implementation. Apply the Engineering Decision Engine and Modern Web Guidance. Read only the relevant components, styles, tests, and docs. Implement the smallest correct change, verify responsive/user-facing behavior, and report changed files, validation, risks, and a compact work receipt.
```

## Security Review

```txt
Use OfficeCorp routing as a security review. Route to Anton with Carla or John only if needed. Inspect auth, permissions, secrets, sensitive data, dependencies, and config relevant to the request. Return findings by severity, evidence, recommended fixes, validation, residual risk, and a compact work receipt.
```
