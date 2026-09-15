# Playwright Artifact Explorer

A lightweight, single-file viewer for browsing Playwright test screenshots and videos locally.

[Live App](https://playwright-artifact-explorer.vercel.app/) · [GitHub Repository](https://github.com/sametcn99/playwright-artifact-explorer)

No server, build step, or installation required.

## Features

- Browse Playwright `test-results` artifacts
- View screenshots and recorded videos
- Filter failed, passed, and unknown tests
- Search tests by name
- Filter by media type
- Run and artifact statistics
- Drag & drop folder loading
- Refresh the selected folder without reloading the page
- Image zoom and pan
- Video timeline, play/pause, mute, and playback speed controls
- Optional “Skip white intro” detects and skips blank white opening frames during playback
- Keyboard navigation
- Dark and light themes
- Multiple display densities
- Export a JSON summary
- Copy test names and artifact paths
- Lazy-load media for large test runs

Everything runs locally in the browser. Files are not uploaded anywhere.

Enable **Skip white intro** in the video player to start at the first visible content. The preference is remembered, and the timeline and replay start at the detected point. Detection scans up to the first 30 seconds; if no transition is found, playback stays unchanged. This is a playback-only trim: **Save** and **Open tab** use the original video.

## Usage

1. Download or clone the repository.
2. Open `index.html` in your browser, or use the [live app](https://playwright-artifact-explorer.vercel.app/).
3. Select or drag your Playwright `test-results` folder.
4. Explore the artifacts.

Playwright usually writes artifacts under:

```text
test-results/
```

For traces, continue using Playwright's trace viewer:

```bash
bunx playwright show-trace path/to/trace.zip
```

## Requirements

A modern Chromium-based browser is recommended because folder selection uses the browser's directory picker APIs.
