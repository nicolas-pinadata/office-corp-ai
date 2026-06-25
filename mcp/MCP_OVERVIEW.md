# MCP Overview

This directory documents the optional Model Context Protocol servers that can be attached to OfficeCorp AI during local project work.

MCP access is not required for normal OfficeCorp usage. Enable an MCP only when the active task needs that external capability, and disable it when the task is done.

## Available MCPs

| MCP | Role | Primary users | Use when |
| --- | --- | --- | --- |
| Filesystem | Read and write project files through an MCP client. | Carla, Nelson, Emily, John, Anton, Peter. | The agent needs project-local file inspection, documentation edits, code edits, or structured repository review. |
| Playwright | Browser automation through the official Microsoft Playwright MCP server. | John, Mia, Nelson, Carla, Anton. | The agent needs to inspect, test, or interact with a local web UI. |
| Chromium | Low-level Chromium or Chrome browser control through a local CDP endpoint. | John, Nelson, Carla, Anton. | The agent needs a persistent browser session, DevTools-level debugging, or browser state that Playwright's isolated browser does not provide. |

## Default Security Position

- Do not expose the whole filesystem.
- Do not store API keys, tokens, passwords, cookies, or production secrets in MCP config files.
- Keep filesystem access limited to this repository.
- Prefer local URLs such as `http://127.0.0.1:<port>` and `http://localhost:<port>`.
- Do not enable unrestricted `file://` access.
- Treat browser MCPs as potentially sensitive because they can see page content, form values, cookies, and local development data.
- Use Anton for permission review when adding or changing MCP access.

## Agent Access Policy

| Agent | Filesystem | Playwright | Chromium | Notes |
| --- | --- | --- | --- | --- |
| Carla | Allowed | Allowed | Allowed | Architecture, technical review, integration design. |
| Nelson | Allowed | Allowed | Allowed | Implementation, debugging, local verification. |
| John | Read-focused | Allowed | Allowed | QA, acceptance checks, regression testing. |
| Anton | Read-focused | Allowed | Allowed | Security review, permission audit, browser exposure review. |
| Emily | Allowed | Not default | Not default | Documentation work only unless docs require UI verification. |
| Mia | Read-focused | Allowed | Not default | UX review and local UI inspection. |
| Peter | Read-focused | Not default | Not default | Context and knowledge management. |
| Jared / Scott / Keith / Ben | Not default | Not default | Not default | Use only when routing, planning, or budget work requires direct project context. |

`Allowed` does not mean always-on. It means the agent may request the MCP when the task justifies it.

## Local Activation Flow

1. Pick the smallest MCP needed for the task.
2. Copy the relevant `config.example.json` into your MCP client's local configuration.
3. Replace `C:\\Users\\Colin\\Downloads\\office-corp` with your local absolute project path if needed.
4. Start or reload the MCP client.
5. Confirm the MCP can only see the intended project or local host.

Example Node.js checks:

```bash
node --version
npx -y @playwright/mcp@latest --help
npx -y @modelcontextprotocol/server-filesystem --help
```

Node.js 18 or newer is required for the official Playwright MCP server.

## Local Deactivation Flow

Use one of these options:

- Set `"disabled": true` for the MCP server if your client supports it.
- Remove the MCP server entry from the client config.
- Stop the MCP client process.
- Close any browser launched with remote debugging.
- Delete temporary browser profiles under `.mcp/` if they were created for debugging.

## Recommended Review Checklist

- The configured filesystem root is the project directory, not a home folder or drive root.
- No config file contains real secrets.
- Browser automation is limited to local development hosts unless the task explicitly needs external sites.
- Chromium remote debugging uses a temporary profile, not the user's everyday browser profile.
- The MCP is disabled after high-risk work is complete.
