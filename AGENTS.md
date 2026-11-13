# Documentation project instructions

## About this project

- Public documentation for Photon, built on [Mintlify](https://mintlify.com). It covers two products: **Prescribe** (the web app and deep links, plus embedding with React components, an iframe or the JavaScript client) and **Network** (GraphQL, MCP and webhooks).
- The prescribing UI is always **Prescribe**, whatever the mechanism (React, iframe, link, or anything added later). Its docs have two sections: **App** (the Prescribe app and deep links) and **Embed** (putting Prescribe in your product). "Embed" names that section and the act of embedding, never the product. Link prescribing to the Prescribe app: `rx.neutron.health` in the sandbox and `rx.new` in production (not `rx.photon.health`, which `rx.new` aliases). The sandbox app is live. Production Prescribe is in private preview: label it that way, with access through a Photon contact. Link `app.<env>.health` only for dashboard settings (API credentials, team, catalog, templates), which the **Admin** section (`admin/`) documents. Name roles as the dashboard does: **Administrator**, **Developer**, **Prescriber**, **Medical Operations**, **Staff** and **Support**. The **Resources** section holds the changelog and other developer reference. Elements is deprecated on January 1, 2027, and fully sunset by mid-2027. Mention it only in the migration guide.
- Don't document the previous APIs (`api.<env>.health`, `clinical-api.<env>.health`) or vendor-specific migrations (DoseSpot, MDToolbox).
- Document returned pharmacy offers and patient benefits as supported by the current schema. Don't imply that every offer includes insurance coverage or a guaranteed final price.
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
- Validate GraphQL examples against the live schema at `https://network.neutron.health/graphql` with a valid bearer token. If live introspection is unavailable, verify against the current Core operations and schema, and record that validation limitation.
- MCP runs at `ai.<env>.health` in both environments. It's open to every Neutron account. The ChatGPT plugin is available in production. Claude remains in private preview and connects manually; only ChatGPT and Claude are whitelisted for production OAuth. Other clients should email support. `ai.<env>.health` is the final URL: MCP isn't moving to `network.<env>.health/mcp`. Document its tools as they are today.
- Mark anything documented ahead of launch (a URL that isn't live, a package that isn't published) with ⚠️ and a `{/* TODO(launch): … */}` comment. Search for `TODO(launch)` before going public, and remove each marker as it's fixed. Inline components inside table cells don't survive the editor, so use the plain ⚠️ there.
- Permissions: `read:` lets a token read and draft. `write:` commits: `write:patient` adds and edits patients, `write:prescription` signs (machine tokens never have it), and `write:order` sends.

## Style preferences

- Use explicit placeholder IDs in examples, such as `pat_PATIENT_ID`, `rx_PRESCRIPTION_ID` and `ord_ORDER_ID`. Use suffixes like `_2` when examples need distinct records. Never use real or realistic-looking record IDs.

- Use active voice and second person ("you")
- Keep sentences concise, with one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- Requests authenticate with the `Authorization: Bearer <token>` header
