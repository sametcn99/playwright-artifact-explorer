# Playwright Artifact Explorer

A lightweight, single-file viewer for browsing Playwright test screenshots and videos locally.

No server, build step, or installation required.

## Features

- Browse Playwright `test-results` artifacts
- View screenshots and recorded videos
- Filter failed, passed, and unknown tests
- Search tests by name
- Filter by media type
- Run and artifact statistics
- Drag & drop folder loading
- Image zoom and pan
- Keyboard navigation
- Dark and light themes
- Multiple display densities
- Export a JSON summary
- Copy test names and artifact paths
- Lazy-load media for large test runs

Everything runs locally in the browser. Files are not uploaded anywhere.

## Usage

1. Download or clone the repository.
2. Open `e2e-report.html` in your browser.
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
