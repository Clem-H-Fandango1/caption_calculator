# Caption Calculator

A lightweight browser-based utility for post-production teams working with **Avid CMX_3600 EDL exports**.

This tool reads multiple EDL files from a sequence, identifies graphics-related events on chosen video tracks, merges adjoining edits where needed, and produces:

- a **caption register CSV** for Excel
- an optional **marker EDL** for timeline reference

Everything runs locally in the browser. No backend, no build step, no dependencies.

## What it is for

This project is aimed at workflows where editors or assistants need a quick way to turn timeline graphic events into a clean caption list for sales / delivery versions of a programme.

Typical examples include on-screen:

- money graphics
- timers
- location straps
- caption graphics
- other recurring labelled visual elements

## How it works

The user exports CMX_3600 EDLs from Avid for multiple video tracks, then loads them into the tool.

The app:

1. detects the track number from each filename
2. parses valid video edit events from the EDL text
3. collects graphic events from configured tracks
4. merges adjacent events where needed
5. converts them into a caption register
6. allows download as CSV and marker EDL

## Features

- fully client-side
- no installation required
- single-file app (`index.html`)
- UTF-8 BOM CSV export for Excel compatibility
- marker EDL export for timeline reference
- configurable track inputs
- simple, dependable workflow for assistants / editors

## Assumptions

Current assumptions baked into the tool:

- **25fps**
- **CMX_3600** format
- **REC OUT is exclusive**
- graphics live on dedicated tracks

## Typical workflow

1. In Avid, create or identify the relevant graphics tracks.
2. Add markers on each graphic if needed for reference.
3. Export the required EDLs using the List Tool.
4. Open `index.html` in a browser.
5. Upload the EDL files.
6. Set track numbers if required.
7. Click **Process**.
8. Download CSV or Marker EDL.

## File structure

- `index.html` — complete app UI and logic
- `README.md` — project overview
- `CHANGELOG.md` — version notes
- `docs/architecture.md` — architecture notes
- `LICENSE` — license file

## Running it

No build or install is needed.

Just open:

```bash
index.html
```

in any modern browser.

## Why it is useful

This is the sort of small tool that saves repeated manual work.
Instead of reading edits by eye and assembling caption timings by hand, it turns export files into a usable register in seconds.

## Good candidate for sharing

This repo is already in decent shape for sharing because it is:

- small
- dependency-free
- easy to understand
- tied to a real workflow problem

If you share it publicly, consider adding a couple of real-world screenshots or a sample EDL set to make the use case immediately obvious.

## License

See `LICENSE`.
