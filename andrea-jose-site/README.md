# The Andrea & Jose Show — Episode 1

A single-page scroll story. No build step, no server code — just static files.

## Files
- `index.html` — the whole page (HTML + CSS + JS inline)
- `img/` — scene stills (used as video posters) + the spotlight photo
- `vid/` — the 10 animated scene clips (silent, looping)
- `revival.mp4` — the real concert video that plays in the polaroid

## Deploy on Cloudflare Pages — drag and drop (fastest)
1. Go to Cloudflare dashboard → **Workers & Pages** → **Create** → **Pages** → **Upload assets**.
2. Name the project (e.g. `andrea-jose-show`).
3. Drag this whole folder in (or the .zip). Click **Deploy site**.
4. You get a link like `andrea-jose-show.pages.dev`. That's it.

## Deploy from GitHub instead
1. Create a new repo on GitHub (private is fine).
2. Upload these files to it (GitHub web: **Add file → Upload files**, drag the folder in), or from a terminal:
   ```
   git init
   git add .
   git commit -m "Episode 1"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```
3. Cloudflare dashboard → **Workers & Pages** → **Create** → **Pages** → **Connect to Git** → pick the repo.
4. Build settings: **Framework preset: None**, **Build command: (leave empty)**, **Build output directory: `/`**. Save and deploy.
5. Every push to `main` redeploys automatically.

## Custom domain (optional)
In the Pages project → **Custom domains** → add e.g. `us.gozaentertainment.com` and follow the DNS step.

## Notes
- The page is set to `noindex`, so search engines skip it. It is still public to anyone with the link.
- The scene clips are silent. Sound (waves, rain, music, the wheel) starts when she taps the button at the top.
- The prize wheel is random and allows one spin per page load; reloading gives another spin.
