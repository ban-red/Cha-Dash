# M0 design prototypes

## `m0-directions.html`: two visual directions, one dogfood home

This is a single self-contained HTML file. Open it in a browser; there's no build step. It renders the [dogfood home](../../docs/plan/05-dogfood-home.md) with today's real incidents (PBS 92% plus a failed task, jupiter-nas memory at 95%, Plex and Karakeep needing repair) in two directions:

| | A · Instrument | B · Paper |
|---|---|---|
| Idea | A precision instrument panel | The literal *front page* of your home |
| Base | Warm graphite, hairlines, flat tiles | Newsprint, column rules, no cards |
| Type | Instrument Sans · Geist Mono for every value · Doto (dot-matrix) clock | Newsreader serif headlines · Schibsted Grotesk (UI and figures) |
| Status sentence | One line of prose with tappable phrases | A headline with a deck underneath |
| Cameras | Footage with surveillance-style timestamps | Grayscale "photos" with italic captions |
| Fleet | Instrument table | Market-table layout |

**Controls** (in the bottom bar, or from the keyboard):

| Key | Action |
|---|---|
| `1` / `2` | Switch direction |
| `H` | Today ↔ all quiet |
| `T` | Cycle theme: light, dark, night |
| `P` | Phone frame |
| `W` | Widget sheet |
| `E` | Edit-mode look |
| `⌘K` | Command palette |
| `Esc` | Close the top layer, or clear a lens |

**Things to try:**
- **Tap a phrase in the status sentence** to filter the page to that topic (a "lens"). Unrelated tiles fade out.
- **Hover any sparkline.** Every sparkline on the page scrubs to the same moment.
- **Click a tile** to expand it into a detail sheet. Open **Fleet → Reboot** on `pluto` or `jupiter`, then **hold**. The blast radius builds while you hold: rebooting pluto takes down the router.
- **Open the Inbox:** repairs (Plex, Karakeep), label-discovered services, and credential-hygiene hints.
- **⌘K:** fuzzy-search services and actions, e.g. `rebjup` → "Reboot jupiter".
- **Widget sheet:** the Unraid widget in all 7 sizes (each a different layout, never scaled), and the Sonarr widget in all 9 states.

Nothing is executed. Every action ends in a "prototype" toast.

### What to decide from it
1. **Direction:** A, B, or a blend (e.g. A's structure with B's headline and light theme).
2. **Density:** is the front page too much or too little at desktop and phone sizes?
3. **Signal color:** does amber Ember read as "needs you" without feeling alarming?
4. **Status sentence:** a terse line (A) or a headline (B)?

### Findings recorded so far
- **Orange vs red is not distinguishable enough** for colorblind readers, or even for normal vision (validator ΔE 11–12.5, below the floor of 15). Ember moved to amber and "down" to crimson; both pairs pass. See [02 · Experience → Color](../../docs/plan/02-experience.md#color).
- Long host names in prose need non-breaking hyphens (`jupiter‑nas`).
- Interactive phrases in a headline have to be wrappable inline elements, not buttons, or the headline breaks badly.

### Known limits
- Fonts load from Google Fonts. The product bundles them, per the Pact.
- No drag or resize in edit mode yet; that's the separate layout-engine spike.
- Data is static and seeded, but shaped like the real home.
