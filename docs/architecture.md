# Architecture

## Overview

Caption Calculator parses CMX_3600 EDL files client-side and extracts graphic events from specified tracks.

Data Flow:

EDL Files → Parse → Filter by Track → Merge → Build Results → Export

## Event Structure

{
  recIn: string,
  recInF: number,
  recOutF: number
}

## Inclusive OUT

OUT = REC OUT - 1 frame

Duration = OUT - IN + 1

## Constraints

- 25fps
- CMX_3600 only
- Non-drop frame assumed
