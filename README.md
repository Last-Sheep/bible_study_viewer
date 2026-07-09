2026-07-09
# Bible Study Viewer

A responsive web application for viewing structured Bible studies with
multiple Bible translations displayed side by side.

------------------------------------------------------------------------

## ✨ Features

-   📖 Load Bible studies from JSON
-   🔀 Compare multiple Bible versions simultaneously
-   📑 Automatically generated Table of Contents
-   🎯 Verse highlighting support
-   ❤️ Jesus' words styled automatically
-   🧰 Per-verse action toolbar (open/pinned states)
-   ⌨️ Keyboard navigation between version windows
-   📤 Export studies as standalone HTML
-   📱 Responsive layout for desktop, tablet, and mobile
-   🐞 Built-in debug overlay for development

------------------------------------------------------------------------

## Layout

``` text
Header
Controls
Study Toolbar
--------------------------------------------
Left Drawer | Viewer | Right Drawer
--------------------------------------------
Floating Viewer Navigation
```

The study toolbar remains independent of the left and right drawers.

------------------------------------------------------------------------

## Project Structure

``` text
/
├── index.html
├── images/
├── data/
│   └── bible_studies/
│       ├── manifest.json
│       ├── StudyName/
│       │   ├── StudyName.json
│       │   ├── highlights.json
│       │   └── keywords.json
```

------------------------------------------------------------------------

## Study Format

``` text
Study
 └── Header
 └── Versions
 └── Blocks
      └── Reference
      └── Title
      └── Rows
           └── Verse
           └── Texts
```

------------------------------------------------------------------------

## Current Capabilities

### Study Loading

-   Loads studies from `manifest.json`
-   Loads optional highlights and keyword metadata

### Scripture Viewer

-   Block-based rendering
-   Responsive multi-version comparison
-   Automatic verse formatting

### Verse Toolbar

Each verse/version cell has an independent toolbar with:

-   Pin
-   Bookmark
-   Notes
-   Dictionary
-   Concordance / Strong's
-   Cross References
-   Audio
-   Close

### Navigation

-   Floating viewer navigation
-   Keyboard arrow navigation
-   Dynamic version window sizing

### Export

Exports the loaded study as a standalone HTML document while preserving
formatting and highlights.

------------------------------------------------------------------------

## Architecture

The application is organized around a state-driven rendering model.

Major components include:

-   Global application state
-   Study loader
-   Rendering engine
-   Responsive column engine
-   Version window manager
-   Verse toolbar state machine
-   Table of Contents
-   Export engine
-   Debug overlay

------------------------------------------------------------------------

## Roadmap

Planned future enhancements include:

-   Notes system
-   Bookmarks
-   Dictionary integration
-   Strong's / Concordance support
-   Cross-reference explorer
-   Audio playback
-   Enhanced left and right drawers
-   Additional study tools

------------------------------------------------------------------------

## Technology

-   HTML5
-   CSS3
-   Vanilla JavaScript (ES6)

No external JavaScript frameworks are required.
