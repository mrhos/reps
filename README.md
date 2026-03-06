# REPS

A personal workout tracker that lives in a single HTML file.

No server. No account. No install. Open in your mobile browser, save to your home screen, and train.

## How it works

- **Open** `workout.html` in your browser (or via GitHub Pages)
- **Add to Home Screen** on iOS or Android — runs full-screen like a native app
- **All data lives on your device** in `localStorage`
- **Export a backup** from Settings as a JSON file; import it on a new device

## Files

| File | What |
|------|------|
| `workout.html` | The entire app — HTML, CSS, and React in one file |
| `reps-mock-data.json` | 8-week sample dataset — import via Settings to populate charts |
| `manifest.json` | PWA manifest for home screen install |
| `icon-180.png` / `icon-192.png` / `icon-512.png` | App icons |

## Features

- **Today** — start and log your workout, set by set
- **Program** — define your weekly split (which exercises on which days)
- **Progress** — per-exercise weight and volume charts with muscle group filters
- **Library** — browse and add exercises by muscle group
- **Settings** — export / import JSON backup, reset data

Progressive overload suggestions, rest timer, exercise swap, ring progress indicator, and a completion screen are all built in.

## Tech

- React 18 via CDN + Babel standalone — no build step
- `localStorage` only — no backend, no tracking
- Custom SVG charts — no charting library
- PWA — `manifest.json` + apple meta tags for home screen install

## Deploying via GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings → Pages → Source: Deploy from branch → main / root**
3. Your app will be live at `https://<username>.github.io/<repo-name>/workout.html`
4. Share that URL — anyone can open it and save it to their home screen

Each person's data is stored on their own device. No data is shared or synced.

## Backup strategy

Export a JSON backup from Settings whenever you get the weekly nudge. Import it on a new device to restore all your history.
