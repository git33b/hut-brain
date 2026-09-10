# Runbook

How to execute the schematic.

## 1. Open locally

1. Save or clone `index.html`.
2. Double-click it, or:

```bash
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

3. Confirm you see a large ring and a small organ in the center.
4. Click the organ. Rate should spike and sparks should burst.
5. Press `F`. Same burst.

## 2. Phone check

1. AirDrop or download `index.html`.
2. Open in **Safari**, not the iMessage preview.
3. Tap the organ.

If the activity panel is a blank rectangle, you are still in Quick Look. Use Share → Open in Safari.

## 3. GitHub Pages

1. Repo Settings → Pages.
2. Source: Deploy from a branch.
3. Branch: `main`, folder: `/ (root)`.
4. Wait a minute, then open `https://git33b.github.io/hut-brain/`.

## 4. Firebase

```bash
npm install -g firebase-tools
firebase login
firebase init hosting
# public directory: .   (this folder)
# SPA rewrite: No
# do not overwrite index.html
firebase deploy --only hosting
```

Site URL: `https://PROJECT_ID.web.app`

## 5. Netlify Drop

Drag `index.html` onto https://app.netlify.com/drop and copy the URL.

## Expected idle vs stimulus

| State | Rate | Amplitude | Status |
| --- | --- | --- | --- |
| Idle | ~8–18 Hz | low | IDLE |
| Stimulus | ~40–72 Hz | high | STIMULUS |
| After ~0.9s | returns to idle | low | IDLE |
