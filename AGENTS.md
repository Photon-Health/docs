# Documentation project instructions

## About this project

- Public documentation for Photon, built on [Mintlify](https://mintlify.com). It covers two products: **Embed** (React components, iframe, app links and the JavaScript client) and **Network** (GraphQL and MCP).
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Use the Mintlify MCP server, `https://mcp.mintlify.com`, to edit content and settings via MCP
- Use the Mintlify docs MCP server, `https://www.mintlify.com/docs/mcp`, to query information about using Mintlify via MCP

## Content rules

- Keep it simple. Lead with the shortest path that works, and don't rebuild workflows that Embed already provides.
- Link to Neutron (`*.neutron.health`, the sandbox) by default. Use Photon (`*.photon.health`, production) only when a page is about production. Never document boson.
- Machine tokens can't sign prescriptions. Any flow that signs or sends goes through a prescriber's user token, usually in Embed.
- Photon's backend makes the decisions (matching, drug resolution, screening). Docs describe what to send and how to read `changes`, not client-side rules.
- Validate GraphQL examples against the live schema at `https://network.neutron.health/graphql` (introspection is open).
- MCP is in private preview. Label it that way.

## Style preferences

- Use active voice and second person ("you")
- Keep sentences concise, with one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- Requests authenticate with the `Authorization: Bearer <token>` header
