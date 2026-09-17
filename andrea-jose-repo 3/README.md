# The Andrea & Jose Show — Episode 1

Static site. No build step.

- `out/` — everything that gets served (index.html, img/, vid/, revival.mp4)
- `wrangler.jsonc` — tells Cloudflare to serve the `out/` folder

## Cloudflare (Workers, deploy command `npx wrangler deploy`)
Nothing to change — `wrangler.jsonc` already points at `out/`.
Build command: leave empty. Deploy command: `npx wrangler deploy`.

## Cloudflare Pages instead
Framework preset: None · Build command: empty · Build output directory: `out`
