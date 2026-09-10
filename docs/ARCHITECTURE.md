# Architecture

Single file: `index.html`. Three layers in one document.

## Layers

1. **Markup** — lab chrome, specimen readout, vault stage, pea button, activity panel.
2. **CSS** — dark HUD, scan rings, pea size, CSS spark dots, waveform fallback, mobile stack.
3. **JavaScript** — baseline flicker, stimulus handler, readout updates.

CSS is the fallback so the pea and some sparks still show if a viewer blocks JS (iMessage Quick Look). JS is the enhancement that makes tap-to-stimulate feel alive.

## DOM map

| id / class | Purpose |
| --- | --- |
| `#pea` | Button wrapping the tiny organ SVG. 56px hit target. |
| `.vault` | Large empty scan ring that makes the pea look small. |
| `.sparks span` | CSS-only synapse dots around the pea. |
| `#rate` `#amp` `#status` | Live readout fields. |
| `#wave` | CSS waveform bars. Extra height on stimulus. |
| `#log` | Short event log. |

## Stimulus execution

```
pointerdown / keydown(F)
  → pea class "fired" (scale + glow)
  → sparks class "burst" (faster / brighter dots)
  → readout rate and amplitude jump for ~900ms
  → status text = STIMULUS
  → log line appended
  → timers restore idle values
```

The handler is debounced so a held finger does not stack ten bursts.

## Why the pea is small

The organ SVG is ~28px inside a vault that is most of the stage width. The scale contrast is visual, not a medical claim.

## Mobile

- Layout stacks: header, readout, vault, activity.
- Vault `min-height` keeps the ring from collapsing into a sliver.
- Captions sit above and below the ring so they do not overlap.
- Hit target is 56px for a thumb.

## What is not in this repo

No server, no API, no auth, no analytics, no personal data.
