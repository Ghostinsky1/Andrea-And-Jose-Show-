# The Andrea & Jose Show

Two episodes, plain static files. No build step, no Worker code.

```
index.html      hub page (links to both episodes)
img/            hub thumbnails
ep1/            Episode 1 — "Lincoln, Not Omaha"
ep2/            Episode 2 — "The First Bite" (film has sound)
wrangler.jsonc  only needed if you deploy with wrangler
```

## Best way: a NEW Cloudflare Pages project (no build, no wrangler)
1. Cloudflare dashboard → **Workers & Pages** → **Create** → **Pages** → **Upload assets**
2. Name it something new, e.g. `andrea-jose-show`
3. Drag this whole folder (or the .zip) in → **Deploy site**
4. You get `andrea-jose-show.pages.dev`. Done.

Do NOT reuse the old project — it is a Workers project whose deploy command runs
`npx wrangler deploy`, and its config points at a Worker entry file (`src/worker.js`)
that does not exist here. That is what the build error was.

## If you connect this repo to Git instead
Cloudflare → **Create** → **Pages** → **Connect to Git** → pick the repo, then:
- Framework preset: **None**
- Build command: **(empty)**
- Build output directory: **/**
- Deploy command: **(empty — leave it blank; do not use `npx wrangler deploy`)**

## If you insist on the Workers + wrangler flow
Keep `wrangler.jsonc` at the repo root exactly as it is here (assets only, no `main`),
and delete any old `src/worker.js` reference from your previous config. Then
`npx wrangler deploy` uploads the folder as static assets.

## Notes
- Episode 2's film has a full score and sound effects. It starts muted because phones
  block auto-sound; tapping play turns the sound on, and there is a speaker button.
- Episode 1's scene clips are silent by design; that page has its own soft music toggle.
