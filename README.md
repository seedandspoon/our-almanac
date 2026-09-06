# Our Almanac

A warm, mobile-first family almanac for planning birthdays, gifts, seasonal rituals, and someday ideas throughout the year — not a task list, a way to remember the life you want to live with the people you care about.

## What's here

`index.html` is the whole app: markup, iOS-inspired styles, and vanilla JS, no build step, no dependencies. It's meant to be published as a [Claude Artifact](https://claude.ai/code/artifact/6405a5bc-d68a-4df5-a3eb-823bfaab34b4), which is where the live version lives and where it gets its persistent database (the `db` runtime capability — people and plans you add there are stored server-side per artifact, shared across every device you open that link from).

Opened any other way — a static file, GitHub Pages, `python -m http.server` — the app still works fully: it detects that `window.claude` isn't available and falls back to storing everything in the browser's own `localStorage` instead. That's local-only and per-browser, but nothing breaks.

## Updating the live app

The GitHub copy and the published Claude Artifact are two separate files that happen to start identical — editing one does not update the other. To ship a change:

1. Edit `index.html` here, commit and push as usual.
2. Re-publish the same content to the Claude Artifact (via Claude Code, pointing at the artifact's existing URL) so the live link picks it up.

## Running it locally

No build step — just serve the folder and open it:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`. It'll seed itself with a few example people and plans on first run (clearly editable/deletable, not real data).
