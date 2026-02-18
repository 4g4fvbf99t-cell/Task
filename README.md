# Focus Timer — PWA Setup

A Sanzo Wada split-color focus timer. Works offline, installs to your iPhone home screen as a standalone app.

## Files
```
index.html      ← the app
manifest.json   ← PWA config
sw.js           ← service worker (offline support)
icon-192.png    ← you need to add this (see below)
icon-512.png    ← you need to add this (see below)
```

## 1. Make your icons

You need two square PNG icons. Quickest options:

- **[realfavicongenerator.net](https://realfavicongenerator.net)** — upload any image, it generates all sizes
- **[favicon.io](https://favicon.io)** — can generate from text (e.g. a simple "F") or an emoji
- Or just make a 512×512 solid-color square in any image editor and save as `icon-512.png`, then resize to 192×192 for `icon-192.png`

The icon should be square with no transparency (iOS crops it to a rounded rect automatically).

## 2. Deploy to GitHub Pages

1. Go to [github.com](https://github.com) and sign in (free account is fine)
2. Click **New repository** — name it anything, e.g. `focus-timer`
3. Make it **Public**
4. Upload all four files: `index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`
5. Go to **Settings → Pages**
6. Under "Branch" select `main`, folder `/root`, click **Save**
7. After ~60 seconds your URL appears: `https://yourusername.github.io/focus-timer`

## 3. Install on iPhone

1. Open the URL in **Safari** (must be Safari, not Chrome)
2. Tap the **Share** button (box with arrow)
3. Tap **Add to Home Screen**
4. Tap **Add**

It now lives on your home screen, launches fullscreen with no browser UI, and works offline.

## Updating the app

Edit `index.html` on GitHub directly (pencil icon), commit the change.  
The service worker version is pinned to `focus-timer-v1` in `sw.js` — if you make big changes, bump it to `focus-timer-v2` so users get the fresh version.
