---
name: heir-search-estimate
description: Estimate how many research hours a US probate heir search will take (locating missing or unknown heirs for an estate) with the free HeirPros MCP server. Use for questions like "how long will an heir search take for an estate with 4 known heirs and 2 missing ones" or "what does a probate genealogist do".
---

# Heir search hours estimate (HeirPros)

Every tool named below comes from the free HeirPros MCP server, `https://heirpros.com/mcp` (Streamable HTTP,
no sign-in, no API key, all tools read-only). If `estimate_heir_search_hours` is not available, add the server
first: `claude mcp add --transport http heirpros https://heirpros.com/mcp` (Claude Code), or point any other
MCP client at the URL.

## Steps

1. Get two numbers from the user:
   - `known_heirs`: how many family members (heirs) are already known, 1 to 100.
   - `unknown_heirs`: how many heirs are missing or unknown and need to be found, 1 to 25. If the user is
     unsure, ask for their best guess; the estimate needs at least 1.
2. Optional details, only if the user mentions them: `estate_type` (testate, intestate, n/a),
   `search_purpose` (notice, distribution, n/a), `immigration_or_emigration` (yes, no) and the other fields
   in the tool schema. They are recorded but do not change the hours.
3. Call `estimate_heir_search_hours` and report `estimated_hours`, with the `method` line so the user sees
   how it was worked out.
4. For what HeirPros does, how the research is done or how to order, call `about_heirpros` and pass on the links.

## Reporting rules

- The result is an estimate in hours only. Do not convert it to a price; HeirPros confirms final hours
  before work starts.
- Do not ask for or send names, case numbers or other personal details. The tool does not need them.
- This is information about a research service, not legal advice.
