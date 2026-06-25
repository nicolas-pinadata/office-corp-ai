# Chromium MCP

## Role

The Chromium MCP pattern connects an MCP client to a local Chromium or Chrome browser through the Chrome DevTools Protocol (CDP).

Use it only when a task needs a persistent browser session or DevTools-level debugging that the standard Playwright MCP flow does not cover.

The recommended local implementation is still Microsoft's official `@playwright/mcp` server, configured with a local `--cdp-endpoint`.

## Agents That May Use It

| Agent | Typical use |
| --- | --- |
| John | Browser regression checks that need a persistent session. |
| Nelson | Debugging browser-only behavior, storage, or console state. |
| Carla | Integration review where browser runtime state matters. |
| Anton | Security review of browser state, storage, and exposed origins. |

Mia should use the standard Playwright MCP first unless persistent Chromium state is required.

## Use When

- The task needs an existing browser process controlled over CDP.
- You need to inspect storage, console behavior, or network behavior in a persistent context.
- A bug only appears in Chrome or Chromium.
- The agent must debug a local app across reloads without resetting all state.

## Do Not Use When

- The standard Playwright MCP can complete the task.
- The browser profile contains personal accounts, cookies, passwords, or production sessions.
- The task only needs project file access.
- Remote debugging would expose sensitive local browsing state.

## Permissions Required

- Permission to launch Chrome or Chromium with a local remote-debugging port.
- Permission to run `@playwright/mcp@latest`.
- A temporary browser profile inside the project, such as `.mcp/chromium-profile`.
- Localhost-only CDP access.

## Example Config

See [config.example.json](config.example.json).

The example connects to:

```txt
http://127.0.0.1:9222
```

Do not expose the CDP port on a public interface.

## Activate Locally

1. Create a temporary profile directory:

```bash
mkdir -p .mcp/chromium-profile
```

2. Start Chrome or Chromium with remote debugging.

Windows PowerShell example:

```powershell
Start-Process chrome -ArgumentList @(
  "--remote-debugging-address=127.0.0.1",
  "--remote-debugging-port=9222",
  "--user-data-dir=$PWD\.mcp\chromium-profile",
  "http://127.0.0.1:3000"
)
```

macOS example:

```bash
open -na "Google Chrome" --args \
  --remote-debugging-address=127.0.0.1 \
  --remote-debugging-port=9222 \
  --user-data-dir="$PWD/.mcp/chromium-profile" \
  "http://127.0.0.1:3000"
```

Linux example:

```bash
google-chrome \
  --remote-debugging-address=127.0.0.1 \
  --remote-debugging-port=9222 \
  --user-data-dir="$PWD/.mcp/chromium-profile" \
  "http://127.0.0.1:3000"
```

3. Copy the example MCP config into your client.
4. Reload the MCP client.

Useful command:

```bash
npx -y @playwright/mcp@latest --help
```

## Disable Locally

- Remove or disable the `officecorp-chromium` MCP entry.
- Close the Chrome or Chromium process launched with remote debugging.
- Delete `.mcp/chromium-profile` if it contains sensitive local state.

## Security Limits

- Bind remote debugging to `127.0.0.1` only.
- Use a temporary profile, never your daily browser profile.
- Do not browse personal accounts or production admin panels in the controlled profile.
- Do not leave the CDP port running after the task.
- Do not commit `.mcp/` browser profiles.
