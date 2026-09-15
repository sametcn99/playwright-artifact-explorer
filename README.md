# Playwright Artifact Explorer

A lightweight viewer for browsing Playwright test screenshots and videos locally.

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
- Remember the last folder and ask before reloading it on the next visit
- Save playback speed, mute, intro skipping, theme and display preferences locally
- Install as a PWA with offline access to the viewer
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

To copy absolute trace commands, enter the selected folder's full disk path in **Folder path** (for example `C:\projects\hiretea\test-results`). Browsers do not expose this path automatically. The path is remembered for that folder name and appears in the restore prompt. Without it, commands use relative paths. Update the path when switching between folders with the same name.

The last folder name is stored in localStorage, and its read-access handle is stored in IndexedDB when supported. On your next visit, choose **Load folder**, **Not now**, or **Forget folder**. Your browser may ask for read permission again; if access cannot be restored, select the folder again. Files remain on your device.

## Install as an app

Open the hosted app in a supported browser and use **Install app** when it appears, or the browser's install menu. PWA installation requires HTTPS or localhost; directly opening `index.html` still works as a viewer but does not enable installation or the service worker.

After the first online visit, the app shell can open offline. Artifacts are not cached: reopen the remembered local folder to browse them. The manifest, `sw.js`, and `icons/` must be served alongside `index.html` for PWA support.

## Requirements

A modern Chromium-based browser is recommended because folder selection uses the browser's directory picker APIs.
