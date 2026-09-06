# Our Almanac

A warm, mobile-first family almanac for planning birthdays, gifts, seasonal rituals, and someday ideas throughout the year — not a task list, a way to remember the life you want to live with the people you care about.

**Live app:** https://seedandspoon.github.io/our-almanac/

## What's here

`index.html` is the whole app: markup, iOS-inspired styles, and vanilla JS — no build step, no dependencies. This repo *is* the live app: GitHub Pages serves `index.html` straight from `main`, so a push here updates the real thing within a minute or so, no separate publish step.

## How your data is stored and synced

Data lives in a small Firestore database (Firebase project `our-almanac-cb912`, owned by heyseedandspoon@gmail.com — a free "Spark" plan project, no billing attached). There's no login screen: the app signs each device in anonymously the moment it loads, invisibly.

What ties your devices together is a **sync code** — a random string like `ppvh6mef6l`, generated the first time you ever open the app. Tap **Sync** on Home to see this device's code, copy it, and enter it (via the same Sync screen → "Use a different code") on any other device to make it show the same almanac. No code, no access — that's the entire security model, and it's enforced by the database's own rules, not just by the app hiding a button.

If a device already has data saved locally from before sync existed, the very first time it sets up sync it carries that data over rather than starting blank.

**Fallback:** if Firebase is ever unreachable (offline, blocked, etc.), the app falls back to the browser's own `localStorage` automatically so it keeps working — just without syncing until it can reconnect.

**Backups:** the same Sync screen has "Download a backup" (saves everything as a JSON file) and "Restore from a backup" (loads one back in, replacing what's currently synced). Worth doing occasionally regardless of how much you trust Firebase — it's your data's exit door if you ever need one.

## Updating the app

Edit `index.html`, commit, push. That's it.

## Running it locally

No build step — just serve the folder and open it:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`. It'll seed itself with a few example people and plans on first run (clearly editable/deletable, not real data).
