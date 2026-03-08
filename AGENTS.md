# AGENTS.md

## Cursor Cloud specific instructions

This is a zero-dependency, zero-build static HTML web application (大富翁抽籤系統 — Monopoly-style random student picker). The entire app lives in a single `index.html` file with accompanying image (`*.png`) and sound (`sounds/*.mp3`) assets.

### Running the dev server

Serve the repository root with any static HTTP server:

```
python3 -m http.server 8080
```

Then open `http://localhost:8080/` in Chrome. The `file://` protocol will not work because the app uses `fetch()` for cloud sync and references relative asset paths.

### Lint / Test / Build

There is no build step, no linter, no test framework, and no package manager. The app is pure vanilla HTML/CSS/JS with no dependencies beyond two CDN resources (`canvas-confetti` and Google Fonts).

### Notable caveats

- The optional cloud sync feature calls an external Google Apps Script endpoint hardcoded in the source. It works without network access; the app simply runs in local-only mode.
- All image and sound assets are committed to the repo and load via relative paths.
