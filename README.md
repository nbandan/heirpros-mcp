# HeirPros plugin for Hermes Agent and Claude Code

Estimate the research hours for a US probate heir search (finding missing and unknown heirs for an estate)
from your AI agent, using the free [HeirPros](https://heirpros.com) MCP server.

- Server: `https://heirpros.com/mcp` (Streamable HTTP)
- Sign-in: none, no API key
- Tools: `estimate_heir_search_hours`, `about_heirpros` (both read-only)
- Hours only, no pricing. Nothing you send is emailed or stored.

Docs: https://heirpros.com/developers/mcp/

## Install

| You use | Install |
| --- | --- |
| Hermes Agent | `hermes plugins install heirpros` then `hermes plugins enable heirpros` |
| Claude Code | `/plugin install heirpros --marketplace nbandan/heirpros-mcp` |
| Claude Code (server only) | `claude mcp add --transport http heirpros https://heirpros.com/mcp` |
| Claude, Cursor, Windsurf or any MCP client | Add `https://heirpros.com/mcp` as a remote server |

## Install in Hermes Agent

From the Hermes plugin catalog:

```bash
hermes plugins install heirpros
hermes plugins enable heirpros
```

Or straight from GitHub:

```bash
hermes plugins install nbandan/heirpros-mcp --no-enable
hermes plugins enable heirpros
```

Start a new session and ask, for example: "Estimate the hours for an heir search with 4 known heirs and about 3 unknown heirs."

## What's in this repo

Configuration only, no code: `plugin.json` and `mcp.json` (Hermes / Agent Plugins v1), `.claude-plugin/`
and `.mcp.json` (Claude Code), and one skill in [`skills/heir-search-estimate/`](./skills/heir-search-estimate).

## Disclosure

Every tool call goes to heirpros.com, run by HeirPros. The server needs no sign-in, stores nothing and only
returns an hours estimate (1.5 base hours + 1 hour per known heir + 1 hour per estimated unknown heir) and
general information about HeirPros. The tool set is served by the remote server at runtime and is not
covered by a pinned commit. The package marks the server untrusted.

## Support

[Contact HeirPros](https://heirpros.com/contact-us/)
