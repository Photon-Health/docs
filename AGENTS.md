# Documentation project instructions

## About this project

- Public documentation for Photon, built on [Mintlify](https://mintlify.com). It covers two products: **Prescribe** (React components, iframe, app links and the JavaScript client) and **Network** (GraphQL, MCP and webhooks).
- The prescribing UI is always **Prescribe**, whatever the mechanism (React, iframe, link, or anything added later). Use "embed" only as a verb or in app URLs like `/order/embed`. Elements is deprecated. Mention it only in the migration guide.
- Don't document the previous APIs (`api.<env>.health`, `clinical-api.<env>.health`) or vendor-specific migrations (DoseSpot, MDToolbox).
- Benefits and coverage checks aren't documented yet. Benefits will arrive as offers on prescriptions and orders.
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Use the Mintlify MCP server, `https://mcp.mintlify.com`, to edit content and settings via MCP
- Use the Mintlify docs MCP server, `https://www.mintlify.com/docs/mcp`, to query information about using Mintlify via MCP

## Content rules

- Keep it simple. Lead with the shortest path that works, and don't rebuild workflows that Prescribe already provides.
- Link to Neutron (`*.neutron.health`, the sandbox) by default. Use Photon (`*.photon.health`, production) only when a page is about production. Never document boson.
- Machine tokens can't sign prescriptions. Any flow that signs or sends goes through a prescriber's user token, usually in Prescribe.
- Photon's service makes the decisions (matching, drug resolution, screening). Docs describe what to send and how to read `changes`, not client-side rules.
- Call Photon a **service**, never a backend. "Backend" always means the customer's own service ("your backend").
- Validate GraphQL examples against the live schema at `https://network.neutron.health/graphql` (introspection is open).
- MCP is in private preview. Label it that way. Its tools are documented as they are today and will change when MCP moves to `network.<env>.health/mcp`.
- Mark anything documented ahead of launch (a URL that isn't live, a package that isn't published) with ⚠️ and a `{/* TODO(launch): … */}` comment. Search for `TODO(launch)` before going public, and remove each marker as it's fixed. Inline components inside table cells don't survive the editor, so use the plain ⚠️ there.
- Permissions: `read:` lets a token read and draft. `write:` commits: `write:patient` adds and edits patients, `write:prescription` signs (machine tokens never have it), and `write:order` sends.

## Style preferences

- Use active voice and second person ("you")
- Keep sentences concise, with one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- Requests authenticate with the `Authorization: Bearer <token>` header
