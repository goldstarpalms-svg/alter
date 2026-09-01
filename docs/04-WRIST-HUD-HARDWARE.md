# 04 — Wrist HUD Hardware (funded phase)

ALTER currently projects as a hologram over your phone camera. The end-game is a **wrist-worn holographic heads-up display** — a wrist AR that renders ALTER's face and status in your field of view without a phone in your hand.

This lives here as the full spec so the hardware phase can begin when funding lands.

## Bill of materials (draft)

| Module | Purpose |
|---|---|
| Micro-OLED projector (~720p+) | Renders the HUD image |
| Waveguide / diffractive optics | Couples the projected light into your eye (transparent see-through) |
| LCoS or MEMS mirror | Scans/steers the image |
| SoC (e.g. low-power ARM) | Runs ALTER's lightweight local brain + face |
| Battery cell | ~2–4h active use target |
| IMU | Tracks head/wrist movement to stabilize the image |

## Optics

- **FOV target:** ~40–50° diagonal (enough for a conversational face + glanceable stats)
- **Exit pupil:** ~10–12mm for a comfortable eyebox
- **Resolution:** sufficient for legible text at arm's length and a crisp avatar

## Thermal

- Projectors are the main heat source.
- Passive heatsinking via the chassis + active fan for sustained use; target sustained < 40°C skin temperature.

## Why this matters

ALTER is software now. The wrist HUD is where the hardware degree and the project converge — a self you can glance at, not just hold. It waits for funding, not invention: the software that drives it is already running on a $0 budget.
