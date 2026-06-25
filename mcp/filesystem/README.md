# Filesystem MCP

## Role

The filesystem MCP lets an agent inspect and edit files inside the OfficeCorp AI project through an MCP client.

It is useful for repository-aware tasks, but it is also the highest-risk MCP because write access can alter project files.

## Agents That May Use It

| Agent | Access | Typical use |
| --- | --- | --- |
| Carla | Read/write | Architecture review, technical changes, project structure decisions. |
| Nelson | Read/write | Code edits, small fixes, config changes. |
| Emily | Read/write | Documentation creation and cleanup. |
| John | Read-focused | QA review, acceptance criteria checks, regression inspection. |
| Anton | Read-focused | Security and permission audit. |
| Peter | Read-focused | Context management and documentation discovery. |

Other agents should not use the filesystem MCP unless Jared routes the task and the permission is justified.

## Use When

- The task requires reading multiple project files.
- The task requires editing repository documentation or code.
- The task requires comparing implementation against OfficeCorp policies.
- The task requires project-local context that is too large to paste manually.

## Do Not Use When

- The request can be answered from the current prompt.
- The task only needs planning or summarization.
- The required files are outside the project root.
- The user has not approved a write-capable workflow.

## Permissions Required

- Read access to the project root.
- Write access only to the project root when edits are needed.
- No access to the full filesystem.
- No access to home directories, SSH folders, browser profiles, or credential stores.

## Example Config

See [config.example.json](config.example.json).

The example uses `@modelcontextprotocol/server-filesystem` and passes only the OfficeCorp AI project root as an allowed directory.

## Activate Locally

1. Copy the example server entry into your MCP client config.
2. Replace the project path if your checkout lives elsewhere.
3. Reload the MCP client.
4. Ask the client to list accessible roots and confirm only this project is exposed.

Useful commands:

```bash
node --version
npx -y @modelcontextprotocol/server-filesystem --help
```

## Disable Locally

- Set `"disabled": true` if your client supports it.
- Or remove the `officecorp-filesystem` entry from the MCP client config.
- Restart or reload the MCP client.

## Security Limits

- Do not add more root paths without Anton review.
- Do not point the MCP at `C:\`, `/`, `%USERPROFILE%`, `$HOME`, `Downloads`, or a cloud sync root.
- Do not store secrets in the MCP config.
- Keep generated config files out of commits if they contain user-specific paths or private settings.
