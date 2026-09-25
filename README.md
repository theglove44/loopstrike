# Loopstrike

A sci-fi vertical shooter for iPhone that works offline. Drag to fly, fire automatically,
use bullet time, and upgrade your ship between deaths. *Die. Learn. Loop.*

Play: https://theglove44.github.io/loopstrike/

## Install on iPhone (for offline play)

1. On Wi-Fi, open the link above in **Safari**.
2. Tap **Share**, then **Add to Home Screen**.
3. Open it once from the home screen. From then on it works in airplane mode.

Progress (loop data, upgrades, checkpoints, best score) is saved on the phone only.

## Files

| File | What it does |
|---|---|
| `index.html` | The whole game: graphics, sound, levels and save data |
| `sw.js` | Service worker: stores a copy of the game on the phone so it runs offline |
| `manifest.webmanifest` | Tells the phone the name, icon and full-screen mode |
| `icon.png` | Home-screen icon |

## Updating

1. Edit `index.html`.
2. Change `CACHE` in `sw.js` (e.g. `loopstrike-v1` → `loopstrike-v2`). Otherwise phones keep the old copy.
3. Commit and push to `main`. GitHub Pages redeploys in about a minute.
4. On the phone, open the game while online, close it, and open it again.

## Test locally

```bash
python3 -m http.server 8765
```

Then open http://localhost:8765 (the service worker needs `http`, not `file://`).
