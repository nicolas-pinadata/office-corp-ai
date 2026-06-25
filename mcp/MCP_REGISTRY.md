# MCP Registry

This registry lists the MCP servers recognized by OfficeCorp AI and their approved operating boundaries.

Status values:

- `planned`: documented or intended, not configured locally.
- `installed`: available in local MCP config, not currently in use.
- `active`: enabled for the current task.
- `disabled`: intentionally turned off.

| MCP name | Role | Authorized agents | Risk level | Required permissions | Main use cases | Prohibited actions | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Filesystem MCP | Read, create, and modify repository files. | Jared, Nelson, Carla, Emily, Peter. | High | Access limited to the current repo. | Project file inspection, scoped code edits, Markdown documentation, architecture discovery, knowledge organization. | Global disk access; reading or copying secrets; unapproved deletion; unapproved destructive edits; access to personal folders. | planned |
| Playwright MCP | Automate the browser for tests and validation. | John, Nelson, Mia, Carla, Anton, Jared. | Medium | Local browser access; dev/staging environment access. | QA checks, responsive validation, forms, navigation, accessibility snapshots, end-to-end tests, local regression checks. | Destructive tests in production; production form submission without explicit approval; use of production credentials by default. | planned |
| Chromium/Browser MCP | Inspect sites and applications in a browser. | Mia, John, Nelson, Carla, Anton, Richard, Ben, Laurie. | Medium | Local or sandboxed browser access. | UX inspection, visual review, rendered HTML, computed CSS, accessibility tree, layout shifts, Lighthouse, performance metrics, external documentation research, product or marketing page review. | Unauthorized sensitive login; aggressive scraping; financial actions; legal actions; sensitive form submission without explicit approval; treating Chrome-only behavior as cross-browser proof. | planned |

## Update Rules

- Jared owns status changes.
- Anton should review new MCP entries or permission expansions.
- Any `active` status should be temporary and tied to a specific task.
- Do not mark an MCP `installed` unless it exists in the local MCP client configuration.
- Do not mark an MCP `active` unless it is currently enabled for agent use.
- During frontend visual reviews, Browser MCP and Chromium MCP should be used for evidence when available: rendered HTML, computed CSS, accessibility tree, responsive breakpoints, layout shifts, Lighthouse, and performance metrics.
