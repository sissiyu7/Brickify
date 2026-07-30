[README.md](https://github.com/user-attachments/files/30528772/README.md)

# Brickify

Turn a picture into a 3D‑printable, buildable LEGO‑style model — with a
step‑by‑step build manual. Single self‑contained `index.html`, no build
step, no backend, no dependencies to install.

## Open it in Cursor

1. Open Cursor.
2. **File → Open Folder** and select this folder.
3. Right‑click `index.html` in the sidebar → **Open with Live Server**
   (or just double‑click `index.html` in Finder/Explorer to open it
   directly in a browser — it works standalone, no server required).
4. To keep developing it, just describe the change you want to Cursor's
   chat/agent (Cmd/Ctrl+L or Cmd/Ctrl+K), the same way you'd ask for any
   code change. Everything lives in this one file.

## Publish it so other people can use it

Once you're happy with a version, deploy straight from Cursor's built‑in
terminal (**Terminal → New Terminal**, or `` Ctrl+` ``):

### Option A — Netlify (fastest)
```bash
npx netlify-cli deploy --prod
```
Follow the prompts (log in, pick "create a new site", point it at this
folder). You'll get a live URL in under a minute.

### Option B — Vercel
```bash
npx vercel --prod
```
Same idea — log in, confirm the folder, get a live URL.

### Option C — GitHub Pages (best if you want version history)
```bash
git init
git add .
git commit -m "Brickify"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/brickify.git
git push -u origin main
```
Then in the GitHub repo: **Settings → Pages → Deploy from branch → main
→ / (root)**. Your site goes live at
`https://YOUR_USERNAME.github.io/brickify/`.

If you go with Netlify or Vercel and connect them to this same GitHub
repo (instead of deploying straight from the CLI), every future
`git push` auto‑redeploys the live site — that's the smoothest long‑term
workflow if you plan to keep improving it.

## Notes

- Everything runs client‑side in the browser (image processing, 3D
  preview, STL/manual/ZIP generation) — there's no server or database,
  so hosting cost stays effectively zero at any amount of usage.
- The app loads three.js from a public CDN (cdnjs). If you ever want to
  be independent of that CDN, download `three.min.js` (r128) and
  reference it locally instead of via `<script src="https://...">`.
- No accounts, saved projects, or usage limits exist yet. If you
  eventually want people to save/revisit models or want to track usage,
  that's the point where you'd need to add real backend storage — the
  current version doesn't need one to just let people use it.
