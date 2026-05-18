
VJ lightweight browser for events, premieres, playful public interactive art; project takeover messages

# VJAM

**A lightweight, browser-based VJ mixing system for live events, installations, premieres, and venues.**

No installs. No server. One HTML file.

---

## What it is

VJAM is a single-file web VJ engine built for live performance. Drop it in a browser, load your assets, connect to a projector, and you are ready to mix. It runs entirely client-side with no dependencies, no accounts, and no network required after load.

Designed for speed of setup and ease of use — equally accessible to first-time VJs and experienced operators working fast under live conditions.

**Live at** [evo.ist/vjam](https://evo.ist/vjam)

---

## Features

### Core mixing engine
- Dual-deck crossfader (A/B layers) with animated transitions
- Six transition modes: Cut, Fade, Glitch, Zoom, Slide, Strobe
- Per-deck opacity control and animated crossfade
- Real-time FX: hue rotate, contrast, brightness, saturation, invert, mirror, VHS, scanlines, glitch loop

### Asset system
- Drag-and-drop image and video loading (PNG, JPG, GIF, WebP, MP4, WebM)
- Assets persist across page reloads via IndexedDB — no re-uploading between sessions
- Thumbnail grid with direct A/B deck routing
- Drag from library directly to stage

### Automation
- Auto-advance with configurable interval (2–60 seconds), sequential, random, or ping-pong modes
- Auto takeover: fires a full-screen asset takeover on a configurable timer with color overlay and title flash
- Auto title flash: bursts the configured event title on a randomized interval
- BPM tap tempo display

### Live control
- Red and Blue takeover buttons — hold to hold, release to clear
- Title flash button with four styles: solid, outline, glitch, rainbow
- Live text overlay with color picker and position control (top, center, bottom)
- Fullscreen mode via browser Fullscreen API — whole-page, no UI loss on ESC
- In fullscreen: controls auto-hide after 3 seconds, reappear on mouse move

### White label
- Single CONFIG block at the top of the file — set title, colors, intervals, defaults
- No external dependencies
- No build step required
- Works offline

---

## Quickstart

```bash
# Clone or download
git clone https://github.com/realitycraft/vjam.git

# Open in browser (Chrome or Edge recommended for broadest codec support)
open vjam.html
```

Then:
1. Drop image or video files onto the asset panel or stage
2. Click any thumbnail to load it to the next deck and cut
3. Use the A/B deck tags to route assets manually
4. Crossfader blends between decks in real time
5. Hit **FULLSCREEN** and connect your projector

Assets auto-restore on next open — no need to re-import between sets.

---

## Keyboard shortcuts

| Key | Action |
|-----|--------|
| `Space` | Flash title |
| `F` | Toggle fullscreen |
| `Q` | Previous asset |
| `E` | Next asset |
| `R` | Hold Red takeover |
| `B` | Hold Blue takeover |
| `A` | Toggle auto-advance |
| `G` | Toggle glitch FX |
| `T` | Tap BPM |
| `1–9` | Load asset # to next deck |
| `Esc` | Release takeover / exit fullscreen |

---

## White label configuration

All branding and behavioral defaults live in a single `CONFIG` object at the top of `vjam.html`. No code changes required beyond this block.

```js
const CONFIG = {
  title:           'YOUR EVENT NAME',   // Shown in header and title flash
  subtitle:        'VJ SYSTEM',         // Tagline under the title
  accentColor:     '#00ffcc',           // Primary UI accent (hex)
  redColor:        '#ff1a1a',           // Red takeover color
  blueColor:       '#1a4fff',           // Blue takeover color
  defaultTrans:    'glitch',            // cut | fade | glitch | zoom | slide | strobe
  defaultAutoOn:   true,               // Auto-advance on by default
  defaultInterval: 10,                 // Seconds between auto-advances
  defaultMode:     'rnd',              // seq | rnd | ping
  autoTakeover:    true,               // Auto takeover enabled
  tkoInterval:     120,                // Seconds between auto takeovers
  tkoDuration:     5,                  // Seconds a takeover holds
  autoFlash:       true,               // Auto title flash enabled
  flashInterval:   30,                 // Seconds between title flashes
  flashStyle:      'solid',            // solid | outline | glitch | rainbow
};
```

Custom CSS theming, logo injection, and multi-window output configurations are available as part of a consulting engagement.

---

## Browser support

| Browser | Status |
|---------|--------|
| Chrome 90+ | Recommended |
| Edge 90+ | Full support |
| Firefox 88+ | Full support |
| Safari 15+ | Supported (some codec limits) |

MP4/H.264 video works across all modern browsers. ProRes (.mov) files should be converted to MP4 before use.

---

## Use cases

- Concert and festival projection
- Brand activation and launch events
- Gallery installations and art exhibitions
- Venue atmospherics and ambient display loops
- Conference and premiere backgrounds
- Collaborative live VJ performance

---

## Licensing and white label

VJAM is available for white label licensing and bespoke integration.

**To license VJAM or commission a custom build:**

Contact **[evo@playable.agency](mailto:evo@playable.agency)**

Engagement options include:

- **White label license** — deploy VJAM under your own brand for internal use or client projects
- **Consulting** — bespoke VJ system development on top of VJAM for your specific event, venue, or platform
- **Collaborator** — join Realitycraft as a creative or technical collaborator
- **Service agreement** — ongoing support and feature development for organizations and venues

More information: [evo.ist/vjam](https://evo.ist/vjam)

---

## About

VJAM is a project by **[Realitycraft](https://evo.ist)**, built for live creative production.

Realitycraft builds immersive experiences, XR worlds, and live performance tools at the intersection of design, technology, and event production.

> To learn more about the ecosystem: [evo.ist](https://evo.ist)

---

## Project structure

```
vjam/
├── vjam.html          # Core engine — white label, configurable
├── REALITY_GAMES_VJ.html  # Event-specific build (example deployment)
└── README.md          # This file
```

Assets are loaded at runtime via the browser file API and stored in IndexedDB. No asset files are committed to the repository.

---

## Contributing

VJAM is maintained by Realitycraft. Collaboration opportunities are available through a service agreement or contributor arrangement.

Contact [evo@playable.agency](mailto:evo@playable.agency) to discuss.

---

*VJAM — built for the room, not the desk.*

