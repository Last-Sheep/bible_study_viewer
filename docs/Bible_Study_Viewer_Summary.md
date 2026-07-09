2026-07-09
# Bible Study Viewer

## Overview

Bible Study Viewer is a single-page HTML/CSS/JavaScript application for
viewing prebuilt Bible studies stored as JSON. It is designed to display
multiple Bible translations side-by-side while providing a foundation
for study tools such as notes, bookmarks, cross references, dictionary
lookups, and audio.

------------------------------------------------------------------------

## Features

### Layout

The interface consists of:

-   Header
-   Top Controls
-   Study Toolbar
-   Left Drawer
-   Center Viewer
-   Right Drawer
-   Floating Viewer Navigation Bar

The Study Toolbar remains independent of the drawers so it does not
collapse when the drawers are hidden.

------------------------------------------------------------------------

## Study Loading

On startup the application:

1.  Reads `manifest.json`
2.  Populates the Study selector
3.  Loads the selected study
4.  Loads optional `highlights.json`
5.  Loads optional `keywords.json`

------------------------------------------------------------------------

## Scripture Viewer

Studies are rendered as:

``` text
Study
 └── Blocks
      └── Verse Rows
           └── Version Columns
```

Each block contains:

-   Scripture reference
-   Block title
-   Verse rows

Each verse row displays every visible Bible version.

------------------------------------------------------------------------

## Multi-Version Comparison

Supports multiple Bible translations simultaneously.

The viewer automatically pages through version columns.

Responsive layout:

  Screen              Visible Versions
  ----------------- ------------------
  Phone Portrait                     1
  Phone Landscape                    2
  Medium                             3
  Desktop                            4
  Maximum                            6

Collapsing the left and/or right drawers allows additional version
columns.

------------------------------------------------------------------------

## Verse Display

Each verse cell displays:

-   Bible version
-   Scripture reference
-   Verse text

Jesus' words are converted from inline spans into a reusable CSS class.

Optional verse highlighting is loaded from `highlights.json`.

------------------------------------------------------------------------

## Verse Toolbar

Each verse/version cell has an independent toolbar with three states:

-   Closed
-   Open
-   Pinned

Current toolbar buttons:

-   Pin
-   Bookmark
-   Notes
-   Dictionary
-   Concordance / Strong's
-   Cross References
-   Audio
-   Close

Toolbar state is maintained independently for every version and verse.

------------------------------------------------------------------------

## Navigation

### Floating Viewer Navbar

Provides:

-   Previous Version Window
-   Next Version Window
-   Current Version Indicator
-   Close

### Keyboard

Arrow keys navigate version windows unless the user is typing in an
input field.

------------------------------------------------------------------------

## Table of Contents

The TOC is generated dynamically from the study blocks.

Selecting an entry:

-   Scrolls smoothly to the passage
-   Closes the TOC

------------------------------------------------------------------------

## Export

Exports the currently loaded study as a standalone HTML document while
preserving:

-   Scripture layout
-   Highlights
-   Jesus-word styling

------------------------------------------------------------------------

## Scrollbar Control

The center viewer hides scrollbars by default.

A toggle allows scrollbars to be shown or hidden.

------------------------------------------------------------------------

## Debug Overlay

Displays runtime layout information including:

-   Window size
-   Device pixel ratio
-   Panel widths
-   Visible columns
-   Version window size
-   Active toolbar count

------------------------------------------------------------------------

## Architecture

The application is organized into logical modules including:

-   Global state
-   Study loading
-   Rendering engine
-   Responsive column engine
-   Version window management
-   Verse toolbar state machine
-   Navigation
-   Export
-   Table of Contents
-   Debug overlay

The rendering system is state-driven. UI updates are produced by changes
to application state, providing a solid foundation for future features
such as notes, bookmarks, dictionaries, cross references, audio
integration, and additional study tools.
