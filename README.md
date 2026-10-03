# Urlbox plugin for Claude

Urlbox renders any web page the way a real browser sees it. This plugin
connects Claude to Urlbox's remote MCP server (`https://api.urlbox.com/mcp`),
so Claude can take screenshots, save pages as PDFs, record scrolling videos,
turn pages into Markdown or clean text, and fetch fully rendered HTML, from a
URL or your own HTML. It can also manage your Urlbox account: projects and
their default render options, usage, recent renders, webhooks, and reporting a
render that does not look right.

It contains no code. It declares the MCP server and one skill that helps Claude
pick the right render tool and options.

## Sign in

The first time Claude calls Urlbox, it opens Urlbox in your browser. Sign in,
then choose an organisation, an access level (Full access, Render and read, or
Read only) and a default project. Only organisation owners and admins can
connect. Secret keys are never shared with Claude. You can see and revoke the
connection under Organisation settings, Connected assistants.

Every render uses your Urlbox plan's renders, so Claude asks before each one.

## Contents

```
.claude-plugin/plugin.json          manifest
.mcp.json                           the Urlbox MCP server (Streamable HTTP, OAuth)
skills/urlbox-web-capture/SKILL.md  choosing a render tool and options
LICENSE                             MIT
```

## Install

- **Claude.ai, Claude Desktop and mobile:** add Urlbox from the connector
  directory, or add `https://api.urlbox.com/mcp` as a custom connector.
- **Claude Code:** install this plugin, or run
  `claude mcp add --transport http urlbox https://api.urlbox.com/mcp`
  and then `/mcp` to sign in.

Documentation: https://urlbox.com/docs/agents/mcp
Support: support@urlbox.com
Privacy policy: https://urlbox.com/policies/privacy
