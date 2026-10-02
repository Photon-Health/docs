# Photon Network API docs

Source for Photon's public API documentation, published with [Mintlify](https://mintlify.com).

## Structure

- `docs.json` — site config: theme, colors, navigation
- `introduction.mdx`, `authentication.mdx` — Get Started
- `patient-mutation.mdx`, `prescription-mutation.mdx`, `order-mutation.mdx` — workflow guides
- `api/` — mutation and type reference
- `concepts/`, `reference/` — change model, entity resolution, screening, errors, enums

## Local preview

```bash
npm i -g mint
mint dev
```

The preview runs at `http://localhost:3000`.

## Publishing

Changes merged to `main` deploy to production automatically. Work on a branch and open a pull request for review.
