# Installation Strategy

OfficeCorp.ai is a portable, file-based company framework. The recommended downstream setup is to vendor the full OfficeCorp package into the project and copy the root agent instruction file beside the project's normal source files.

## Recommended Project Structure

Install OfficeCorp as readable local project guidance:

```txt
target-project/
  AGENTS.md
  office-corp/
    README.md
    routing/
    docs/
    agents/
    playbooks/
    skills/
```

The root `AGENTS.md` is the discovery hook. It tells coding agents to:

1. Read `office-corp/README.md` first.
2. Route the request through `office-corp/routing/TASK_ROUTER.md`.
3. Load only relevant context from `office-corp/docs`, `office-corp/agents`, `office-corp/playbooks`, and `office-corp/skills`.
4. For non-trivial work, mention the OfficeCorp route/context used in the final answer.

OfficeCorp instructions never override higher-priority system, developer, platform, or user instructions. Do not copy the source repository's `.git` directory into the downstream `office-corp/` folder.

See `docs/AGENT_INTEGRATION.md` for the expected agent behavior.

## Installation Procedure

Run the install from the downstream project root. The same commands can be used later to refresh OfficeCorp.

Windows PowerShell:

```powershell
git clone https://github.com/nicolas-pinadata/office-corp-ai .tmp-office-corp-ai
robocopy .tmp-office-corp-ai office-corp /E /XD .git
Copy-Item .tmp-office-corp-ai\AGENTS.md AGENTS.md
Remove-Item -Recurse -Force .tmp-office-corp-ai
git add AGENTS.md office-corp
git commit -m "Update OfficeCorp agent integration"
```

`robocopy` may return `1` when files were copied successfully. Treat return codes below `8` as non-fatal.

macOS/Linux:

```sh
git clone https://github.com/nicolas-pinadata/office-corp-ai .tmp-office-corp-ai
rsync -a --delete --exclude .git .tmp-office-corp-ai/ office-corp/
cp .tmp-office-corp-ai/AGENTS.md AGENTS.md
rm -rf .tmp-office-corp-ai
git add AGENTS.md office-corp
git commit -m "Update OfficeCorp agent integration"
```

## Update Procedure

To update OfficeCorp in a downstream project:

1. Clone the current OfficeCorp source into a temporary folder.
2. Copy it over the downstream `office-corp/` folder while excluding `.git`.
3. Refresh or merge the downstream root `AGENTS.md` from the OfficeCorp source.
4. Compare the diff before deleting the temporary clone if you need to inspect upstream files.
5. Run the installation check.
6. Remove the temporary clone.
7. Commit `AGENTS.md` and `office-corp/`.

Safer Windows PowerShell update:

```powershell
git clone https://github.com/nicolas-pinadata/office-corp-ai .tmp-office-corp-ai
robocopy .tmp-office-corp-ai office-corp /E /XD .git
Copy-Item .tmp-office-corp-ai\AGENTS.md AGENTS.md
git diff -- AGENTS.md office-corp
Test-Path office-corp\.git
git diff --check
Remove-Item -Recurse -Force .tmp-office-corp-ai
git add AGENTS.md office-corp
git commit -m "Update OfficeCorp agent integration"
```

`robocopy` may return `1` when files were copied successfully. Treat return codes below `8` as non-fatal. `robocopy /E` preserves downstream files that are no longer present upstream. For an exact mirror update, use `/MIR` only if `office-corp/` contains no downstream-only files you need to keep.

Safer macOS/Linux update:

```sh
git clone https://github.com/nicolas-pinadata/office-corp-ai .tmp-office-corp-ai
rsync -a --delete --exclude .git .tmp-office-corp-ai/ office-corp/
cp .tmp-office-corp-ai/AGENTS.md AGENTS.md
git diff -- AGENTS.md office-corp
test ! -d office-corp/.git
git diff --check
rm -rf .tmp-office-corp-ai
git add AGENTS.md office-corp
git commit -m "Update OfficeCorp agent integration"
```

PowerShell and POSIX shells differ in copy and path syntax:

- PowerShell uses `robocopy`, backslashes, and `Remove-Item`.
- macOS/Linux uses `rsync`, forward slashes, and `rm -rf`.
- `robocopy` exit codes below `8` are normally acceptable; `rsync` uses conventional success/failure exit codes.
- Quote paths in either shell when project folders contain spaces.

If the downstream project has intentionally customized `AGENTS.md`, merge the new OfficeCorp instructions instead of overwriting local project-specific guidance.

Use [INSTALLATION_CHECK.md](INSTALLATION_CHECK.md) after updating.

## Expected Agent Behavior

After installation, ask the coding agent a normal project question. The expected behavior is:

1. Discover OfficeCorp through root `AGENTS.md`.
2. Read `office-corp/README.md`.
3. Route through `office-corp/routing/TASK_ROUTER.md`.
4. Load only the relevant files from `office-corp/docs`, `office-corp/agents`, `office-corp/playbooks`, and `office-corp/skills`.
5. Keep OfficeCorp subordinate to higher-priority system, developer, platform, and user instructions.
6. Mention the OfficeCorp route/context used in final answers for non-trivial work.

## Optional Project Context

Projects may add their own context outside `office-corp/`, such as `.officecorp/project-brief.md`, decision records, or workspace notes. These files are optional. OfficeCorp must still work from the request, root `AGENTS.md`, and the local `office-corp/` package when no extra project context exists.

## Workspace Structure

For portfolio or multi-business usage, organize durable knowledge by workspace:

```txt
workspaces/
  {workspace-name}/
    docs/
    research/
    roadmap/
    architecture/
    ux/
    product/
    marketing/
    decisions/
```

## Rule

The core framework must remain readable, file-based, and independent from any single LLM, runtime, interface, or vendor.
