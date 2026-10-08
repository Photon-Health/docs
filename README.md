# Photon docs

Source for Photon's public documentation, published with [Mintlify](https://mintlify.com).

## Structure

- `docs.json`: site config, including theme, navigation and redirects
- **Get started** tab: `introduction`, `architecture`, `environments`, `authentication`, plus `integrations/` (the four common integrations)
- **Embed** tab: `embed/`, covering the React components, iframe, app links, JavaScript client and styling
- **Network** tab: `network/`, covering GraphQL (patient, prescription, order, changes, screening, errors, reference) and MCP

## Conventions

- Link to Neutron (the sandbox) by default. Link to Photon (production) only when a page is about production.
- Don't document internal environments.
- Validate GraphQL examples against the live schema at `https://network.neutron.health/graphql`.

## Local preview

```bash
npm i -g mint
mint dev
```

The preview runs at `http://localhost:3000`.

## Publishing

Changes merged to `main` deploy to production automatically. Work on a branch and open a pull request for review.
