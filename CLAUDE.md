# Venn Kit — context for Claude

Single static page (`index.html`), no build step. Deploys to Vercel on push to `main`.

## Versioning

Bump the version in the `.version` badge in `index.html` (0.0.10 -> 0.0.11 -> ...)
in every commit that ships a user-visible change. It's shown at the bottom-right
of the app so the deployed build can be checked against what's expected —
skipping the bump breaks that.

## Testing policy

Automate every check that can be automated: unit, integration, and end-to-end
with Playwright against the live site, using throwaway data the test creates
and deletes itself. Never hand the owner a manual checklist for something a
script can do. Manual steps only for what truly can't be automated (browser
permission prompts like folder pickers, and judging feel/usability). Keep
those to the minimum, say why each one can't be automated, and give one short
step at a time.
