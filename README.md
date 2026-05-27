# VJAM

**A lightweight, browser-based VJ mixing system for live events, installations, premieres, and venues.**

No installs. No server. One HTML file.

> **VJAM is a public resource for visual mixing and collaborative jamming with others.** This is a community-driven open-source project. [Support the development](#support--funding).

---

## 🎥 Live Demos

**Try VJAM right now — no setup required:**

- **[evo.ist/vjam/demo](https://evo.ist/vjam/demo)** — Primary demo instance
- **[ghostoflinkwray.com/vjam](https://ghostoflinkwray.com/vjam)** — Alternative instance

### See it in action

Watch the demo video to see VJAM in two real use cases:

1. **Live Festival Projection** — Fast deck switching with cross-fade transitions during a concert set
2. **Gallery Installation Loop** — Auto-advance with automated takeover messages for ambient display

[📹 VJAM Demo Video](#) *(demo video link and embed)*

---

## What it is

VJAM is a single-file web VJ engine built for live performance. Drop it in a browser, load your assets, connect to a projector, and you are ready to mix. It runs entirely client-side with no dependencies.

Designed for speed of setup and ease of use — equally accessible to first-time VJs and experienced operators working fast under live conditions.

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
# Clone the repo
git clone https://github.com/LightLodges/vjam.git

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
- Educational workshops and creative coding

---

## Support & Funding

VJAM is developed as a **public resource** for visual mixing and live performance. We believe creative tools should be accessible to all.

### Become a contributor or supporter

**Help shape the future of VJAM:**

- 💰 **[Donate via GitHub Sponsors](#)** — Fund ongoing development and feature requests
- 🤝 **[Contribute code](https://github.com/LightLodges/vjam/blob/main/CONTRIBUTING.md)** — Submit features, fixes, and improvements
- 📢 **[Share your VJAM setup](#)** — Show us how you're using VJAM at your event or venue
- 🎨 **[Submit asset packs](#)** — Share reusable transition effects or themes

### For organizations and venues

**Interested in commercial licensing or custom development?**

- **White label license** — Deploy VJAM under your brand for commercial use or client projects
- **Bespoke features** — Custom VJ system development for your specific event, venue, or platform
- **Maintenance & support** — Ongoing updates, bug fixes, and dedicated support

**Contact Realitycraft:** [evo@playable.agency](mailto:evo@playable.agency)

---

## Licensing

VJAM is open source and available for **non-commercial use** under the [MIT License](LICENSE).

**Commercial use:** If you wish to use VJAM commercially, license VJAM through Realitycraft or commission custom modifications.

**Contact:** [evo@playable.agency](mailto:evo@playable.agency)

---

## About

VJAM is maintained by **LightLodges** as an open-source project dedicated to making professional VJ tools accessible to everyone. VJAM was originally created by **Realitycraft**.

- **GitHub:** [github.com/LightLodges/vjam](https://github.com/LightLodges/vjam)
- **Live demos:** [evo.ist/vjam/demo](https://evo.ist/vjam/demo) | [ghostoflinkwray.com/vjam](https://ghostoflinkwray.com/vjam)
- **Commercial licensing:** [evo@playable.agency](mailto:evo@playable.agency)

---

## Project structure

```
vjam/
├── vjam.html                 # Core engine — white label, configurable
├── REALITY_GAMES_VJ.html     # Event-specific build (example deployment)
├── README.md                 # This file
├── CONTRIBUTING.md           # Contribution guidelines
├── LICENSE                   # MIT License (non-commercial)
└── demo-video.mp4           # VJAM in action (2 use cases)
```

Assets are loaded at runtime via the browser file API and stored in IndexedDB. No asset files are committed to the repository.

---

## Contributing

We welcome contributions! Whether you're fixing bugs, adding features, or improving documentation:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Make your changes and commit** (`git commit -m 'Add amazing feature'`)
4. **Push to your fork** (`git push origin feature/amazing-feature`)
5. **Open a Pull Request** with a clear description

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

---

*VJAM — built for the room, not the desk.*
