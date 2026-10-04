# Venn Kit — context for Claude

Single static page (`index.html`), no build step. Deploys to Vercel on push to `main`.

## Versioning

Bump the version in the `.version` badge in `index.html` (0.0.10 -> 0.0.11 -> ...)
in every commit that ships a user-visible change. It's shown at the bottom-right
of the app so the deployed build can be checked against what's expected —
skipping the bump breaks that.
