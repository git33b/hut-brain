# HUT'S BRAIN

Interactive neural schematic. A tiny organ sits in a large scan vault. Tap the pea (or press `F`) to apply a stimulus and watch pathways fire.

Live file: [`index.html`](./index.html)

Repo: https://github.com/git33b/hut-brain

## What this is

A single-page visualization. No backend, no accounts, no tracking, no data collection.

- Subject label: `HUT`
- Visual: small organ centered in a large cranial vault ring
- Interaction: press the organ to stimulate firing
- Readout: live rate, amplitude, pathway status

This is a schematic visualization, not a medical record and not a diagnosis.

## Files

| Path | Role |
| --- | --- |
| `index.html` | The whole app: markup, styles, and stimulus logic |
| `docs/ARCHITECTURE.md` | How the code is structured and how a stimulus event runs |
| `docs/RUNBOOK.md` | How to open, test, and deploy |
| `README.md` | This file |

## Run it

### Local

1. Download `index.html` (or clone this repo).
2. Open `index.html` in **Safari, Chrome, or Firefox**.
3. Tap the pea, or press `F`.

```bash
git clone https://github.com/git33b/hut-brain.git
cd hut-brain
open index.html
```

### Phone / iMessage

iMessage file preview is not a real browser. It keeps some CSS and drops most JavaScript, so the empty activity box you saw is Quick Look, not a bug in the page.

- Open the file → Share → **Open in Safari**
- Or send a hosted `https://` link instead of the raw `.html` file
- Or screen-record a few seconds in Safari and send the video if you want the animation inside the chat bubble

## GitHub Pages

After Pages is enabled on this repo (Settings → Pages → Deploy from branch `main` / root):

`https://git33b.github.io/hut-brain/`

## Other hosts

- Netlify Drop: drag `index.html` onto https://app.netlify.com/drop
- Firebase Hosting:

```bash
npm install -g firebase-tools
firebase login
firebase init hosting
firebase deploy --only hosting
```

Use `index.html` at the hosting public root so `/` loads the schematic.

## Controls

| Input | Effect |
| --- | --- |
| Tap / click the pea | Stimulus burst: organ pulse, extra sparks, rate spike |
| `F` | Same stimulus |
| Page load | Idle sparks at a low baseline |

## Notes

- No build step. No npm dependencies.
- Works offline once the file is on disk.
- Do not rely on iMessage Quick Look for the interactive parts.
