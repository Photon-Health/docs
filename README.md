# Photon docs

Source for Photon's public documentation, published with [Mintlify](https://mintlify.com).

## Structure

- `docs.json`: site config, including theme, navigation and redirects
- **Get started** product: `introduction`, `architecture`, `environments`, `authentication`, `dashboard`, plus `integrations/` (the four common integrations)
- **Prescribe** product: `prescribe/overview`, then two sections: **App** (`prescribe/app`, the web app and deep links) and **Embed** (`prescribe/embed`, the React components, iframe, JavaScript client, styling and migrating from Elements)
- **Network** product: `network/`, covering GraphQL (patient, prescription, order, changes, screening, errors, reference) and MCP

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
