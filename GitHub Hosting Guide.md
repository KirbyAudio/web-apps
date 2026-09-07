# 🚀 Hosting your PWA Apps on GitHub Pages (free)

**Apps:** Ripple Viz + Aethelgard are already PWA-ready in this folder.
GitHub Pages serves over HTTPS (required for PWAs / service workers / install).

## The zero-tools way (recommended if you don't want Git)
1. Create a GitHub account: https://github.com/signup
2. Create a new repository: **+ → New repository**
   - Name it e.g. `kirby-web-apps` (public or private)
3. Upload the contents of **`/rool-drive/web-apps/`** (NOT the folder itself — the files inside):
   - drag-drop `ripple-viz/`, `aethelgard/`, `icons/` into the repo upload page
4. Go to **Settings → Pages** (left sidebar)
   - Source: **Deploy from a branch** → branch `main` → folder `/ (root)` → Save
5. Wait ~1 minute. You'll get a URL like `https://yourname.github.io/kirby-web-apps/`
6. Your apps:
   - Ripple Viz: `https://yourname.github.io/kirby-web-apps/ripple-viz/`
   - Aethelgard: `https://yourname.github.io/kirby-web-apps/aethelgard/`
7. **Open on your iPhone/iPad → Share → Add to Home Screen** → it's now a full-screen standalone app with icon. ✅

## The Git way (once you want to version things)
```bash
cd /rool-drive/web-apps
git init
git add .
git commit -m "PWA: Ripple Viz + Aethelgard"
git branch -M main
git remote add origin https://github.com/YOURNAME/kirby-web-apps.git
git push -u origin main
# then Settings → Pages as above
```

## If you don't want GitHub yet — the plain-HTTP answer
PWAs need HTTPS. But you can **still use the apps on a device without any hosting**:
- **Android/iPad (anywhere):** the easiest option that works offline is the **local Hermes server** or a tiny `python3 -m http.server` on your PC + open on the same Wi-Fi. Offline-after-first-load works even then (service worker caches), but iOS is picky about HTTPS — use the GitHub route for solid iOS installs.
- **Best no-hosting trick:** for pure offline you can open each `index.html` in Safari **from the drive** — but iOS blocks local files, so GitHub Pages (or a free host like Netlify/Vercel) is genuinely the cleanest for iPad/PWA.

## Updating when you change the game/app
- GitHub Pages (Git way): `git add . && git commit -m "update" && git push`
- Upload way: re-upload the changed file, wait a minute.
- The service worker re-fetches the newest index each launch (network-first), so updates appear automatically.

— **Dog Eyes** · *the girls' Chore Crawl, but now it's a real installable thing* ⚔️💜
