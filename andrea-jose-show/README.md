# The Andrea & Jose Show

One static site, both episodes. No build step.

- `index.html` — the hub (pick an episode)
- `ep1/` — Episode 1, "Lincoln, Not Omaha" (index.html + img/ + vid/ + revival.mp4)
- `ep2/` — Episode 2, "The First Bite" (index.html + media/)
- `img/` — the two episode thumbnails

Every path is relative, so the folder deploys exactly as it is.

## Cloudflare Pages
Push this folder to a GitHub repo (or drag-and-drop it in the Pages dashboard), then:

- Framework preset: **None**
- Build command: **leave empty**
- Build output directory: **`/`**

Episode 1's old repo used an `out/` folder and a `wrangler.jsonc`. Neither is needed here; everything sits at the root.

Once it's live, the hub is at `/`, Episode 1 at `/ep1/`, Episode 2 at `/ep2/`.
