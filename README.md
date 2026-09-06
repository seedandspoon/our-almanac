# Our Almanac

A warm, mobile-first family almanac for planning birthdays, gifts, seasonal rituals, and someday ideas throughout the year — not a task list, a way to remember the life you want to live with the people you care about.

**Live app:** https://seedandspoon.github.io/our-almanac/

## What's here

`index.html` is the whole app: markup, iOS-inspired styles, and vanilla JS — no build step, no dependencies. This repo *is* the live app: GitHub Pages serves `index.html` straight from `main`, so a push here updates the real thing within a minute or so, no separate publish step.

## How your data is stored

The app saves everything to the browser's own `localStorage` — there's no server-side database. That means:

- Your data stays **on whichever device and browser you added it from**. Opening the link on a new phone, or in a different browser, starts fresh rather than showing what you already saved.
- Clearing that browser's site data (or using it in a private/incognito window) clears your almanac too.
- This was a deliberate trade-off for simplicity: one link, one place, no publish-sync step to think about — at the cost of no automatic sync across devices.

If cross-device sync ever matters enough to be worth the extra step back, the app already has a Claude Artifact–based version with a real shared database — ask for that setup again.

## Updating the app

Edit `index.html`, commit, push. That's it.

## Running it locally

No build step — just serve the folder and open it:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`. It'll seed itself with a few example people and plans on first run (clearly editable/deletable, not real data).
