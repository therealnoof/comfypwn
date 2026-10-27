# comfypwn.com

Consumer-facing critical CVE monitor — a static snapshot of the CVE watch,
served on Cloudflare Workers (Static Assets).

## Deploy

Push to `main` and the GitHub Actions workflow deploys via Wrangler.
Requires these repo secrets:

- `CLOUDFLARE_API_TOKEN` — API token with Workers Scripts:Edit permission
- `CLOUDFLARE_ACCOUNT_ID` — your Cloudflare account ID

Or deploy by hand: `npx wrangler deploy` (after `wrangler login`).

Live URL after deploy: `https://comfypwn.<your-subdomain>.workers.dev`
(a custom domain, e.g. comfypwn.com, can be attached in the Cloudflare
dashboard once the domain is registered).

## Updating the data

`public/index.html` is an export of the Muse artifact
`comfypwn-com-cyberpunk-blend`. When the dashboard data changes, re-export
the artifact and replace this file, then commit and push — the workflow
redeploys automatically.
