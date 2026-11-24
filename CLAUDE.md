# Venn Kit — context for Claude

Single static page (`index.html`), no build step. Deploys to Vercel on push to `main`.

## Versioning

Bump the version in the `.version` badge in `index.html` (0.0.10 -> 0.0.11 -> ...)
in every commit that ships a user-visible change. It's shown at the bottom-right
of the app so the deployed build can be checked against what's expected —
skipping the bump breaks that.

## Testing policy

Automate every check that can be automated: unit, integration, and end-to-end
with Playwright, using throwaway data the test creates and deletes itself. Never hand the owner a manual checklist for something a
script can do. Manual steps only for what truly can't be automated (browser
permission prompts like folder pickers, and judging feel/usability). Keep
those to the minimum, say why each one can't be automated, and give one short
step at a time.

**Vercel requests are a budget** (owner, 2026-11-24: the free plan's 1M CDN
requests a month are shared by all his projects, and going over pauses them
all; a full live Playwright run costs thousands of requests). Every page,
file, API call and prefetch on the live site counts; local runs cost nothing.
- The full Playwright suite runs locally (against a local production build),
  never against the live site unless the owner asks for it.
- After a push the live site gets only a small smoke check (it loads, the
  version, one throwaway create + delete): tens of requests.
- Check the live `/version.json` at most every 30 s and stop once it shows the
  new version; don't browse the live site when a local run shows the same.
