# Foothold

A small installable web app for executive dysfunction. No build step, no backend, no account. Data stays in the browser's localStorage.

## What each part is for

| Problem | What the app does |
| --- | --- |
| Starting | Shows one step at a time. "Start with 2 minutes" is the default button, and you may stop when it ends. |
| Overwhelm | "Make it smaller" puts a tinier step in front of the current one. "Pick for me" removes the choosing. Today holds 3 tasks. |
| Time blindness | A 60 minute dial where 25 minutes always looks like 25 minutes, chimes while a timer runs, a bar for how much of the day is left, and guess vs. tracked time. |
| Follow-through | "Not now" parks a task with a note on where you left off, and the note is shown when you come back. Done keeps today's finished steps. |

## Put it on your phone (GitHub Pages)

1. Create a new public repository, for example `foothold`.
2. Upload these five files to the repository root: `index.html`, `sw.js`, `manifest.webmanifest`, `icon-192.png`, `icon-512.png`.
3. Repository Settings → Pages → Source: "Deploy from a branch" → `main` / root → Save.
4. After a minute, open `https://<your-username>.github.io/foothold/` on your phone.
5. Android Chrome: menu → "Add to Home screen" / "Install app". iPhone Safari: Share → "Add to Home Screen".

To run it locally: `python3 -m http.server` in this folder, then open `http://localhost:8000`.

## Known limits

- A web app cannot ring reliably once the phone locks or the app is in the background. The timer keeps the screen awake while it runs, and the time is always correct when you come back, but the end chime can be late or silent in the background.
- Data lives on one device. Use Done → Settings → "Copy a backup" to move it or keep it safe.
- When you change `index.html`, bump `CACHE` in `sw.js` (for example `foothold-v2`) so installed copies drop the old cache.
