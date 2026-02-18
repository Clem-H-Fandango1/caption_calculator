# Caption Calculator

A lightweight browser-based tool for generating caption lists for the sales versions of **BOL**.

## Purpose

This tool processes CMX_3600 EDL exports from Avid and generates:

- A caption register (CSV for Excel)
- An optional marker EDL file for timeline reference

No server required. No dependencies. Fully client-side.

---

## Workflow (Avid)

1. Create a V14 track.
2. Add markers on every graphic (e.g. £200, Timer, GERMAN TOWNS).
   - They do NOT need to be placed exactly at the start.
3. Export CMX_3600 EDLs via the List Tool.
   - You should end up with:
     SEQ_NAME_V1.edl
     SEQ_NAME_V2.edl
     ...
     SEQ_NAME_V14.edl

---

## Using the Tool

1. Open index.html
2. Upload all EDL files
3. Adjust track numbers if required
4. Click Process
5. Download CSV or Marker EDL

CSV includes UTF-8 BOM for proper £ symbol handling in Excel.

---

## Architecture Overview

Core functions:

- detectTrack() → extracts track number from filename
- parseEDL() → parses CMX_3600 events
- merge() → merges add-edits
- processFiles() → orchestrates parsing and output
- downloadCSV() → Excel-safe export
- downloadMarkerEDL() → generates marker EDL

---

## Assumptions

- 25fps
- CMX_3600 format
- REC OUT is exclusive
- Graphics on dedicated tracks

---

## Versioning

v1.x = stability
v2.x = structural upgrades
v3.x = workflow redesign

---

## License

MIT
