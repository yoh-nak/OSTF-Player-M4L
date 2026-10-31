# OSTF Player for Max for Live

**Version 1.0 — Initial Release**

An interactive song player, visualizer, and lead sheet tool for Ableton Live, powered by the **Open Song Timeline Format (OSTF)**.

OSTF Player allows you to load, explore, play, and transpose structured song data, including chord progressions, melodies, lyrics, sections, and arrangement tracks.

The device includes built-in instruments, drum kits, and 11 demonstration songs.

## Features

### OSTF File Support

- Supports OSTF 3.0, 3.1, and 3.2
- Loads `.ostf` song files
- Displays song structure and musical information
- Preserves the original OSTF file during playback and editing operations
- Supports tempo, meter, key, and section information

### Song View

Explore a complete song through an interactive timeline.

- Song sections and chord progressions
- Melody visualization
- Synchronized lyrics and pronunciation
- Playback position highlighting
- Timeline navigation and zoom
- Chord and melody pitch information

### Tracks View

Inspect arrangement tracks individually.

- Piano-roll visualization
- Instrument and MIDI note information
- Track-level controls
- Playback and navigation
- Arrangement inspection

### Built-in Sound Engine

Preview songs without loading additional instrument plugins.

Includes:

- 13 instrument sound definitions
- 4 drum kits
- Automatic instrument preview assignment
- Polyphonic playback
- Basic velocity-sensitive performance

The internal sound engine is intended for song previews and structural inspection rather than replacing dedicated VST instruments or professional sample libraries.

### Key Transposition

Transpose songs while retaining their original OSTF source data.

- Adjustable semitone transposition
- Key and chord display updates
- Restore original key
- Independent key selection for lead sheet printing

### Lead Sheet and PDF Export

Generate printable lead sheets directly from the Player.

Available options include:

- A4 and other available paper settings
- Portrait and landscape layouts
- Chord symbols and lyrics
- Section labels and bar numbers
- Title and credit information
- Font size and spacing adjustments
- Custom PDF scale
- Independent print key
- PDF preview before export

### MIDI Export

Generate MIDI material from OSTF arrangement information for further use in Ableton Live.

The Player provides MIDI export functionality for working with song material in a DAW environment.

## Requirements

- Ableton Live with Max for Live support
- A compatible Max for Live environment
- Windows or macOS
- OSTF song files for loading external songs

Developed using the Max for Live device format (`.amxd`).

**Note:** Exact Ableton Live and Max version compatibility has not been fully certified across all supported operating systems.

## Installation

1. Download `OSTF_Player_v1.0.amxd` from this repository.
2. Open Ableton Live.
3. Create or select a MIDI track.
4. Drag the `.amxd` file onto the MIDI track.
5. Click **Open** on the device.
6. The OSTF Player interface will appear.

You can now load an OSTF song or select one of the built-in demonstration songs.

## Quick Start

### 1. Open the Player

Click the **Open** button in the Max for Live device view.

### 2. Select a Demo Song

Choose one of the included demonstration songs to explore the Player.

### 3. Start Playback

Use the playback controls to listen to the song through the built-in sound engine.

### 4. Explore the Song

Switch between Song and Tracks views to inspect song structure, chord progressions, melodies, lyrics, and arrangement data.

### 5. Change the Key

Use the transpose controls to hear or display a song in another key.

The original OSTF file remains unchanged.

### 6. Print a Lead Sheet

Open the lead sheet printing interface.

Adjust the layout, scaling, displayed information, and print key. Preview the result before exporting a PDF.

## Included Demo Songs

The initial release includes 11 demonstration songs.

| No. | Genre | Song Title |
|---|---|---|
| 01 | Pop | City Lights Again |
| 02 | Rock | Against the Current |
| 03 | Ballad | The Last Train Home |
| 04 | Jazz Swing | After Midnight |
| 05 | Jazz Bebop | Corner Changes |
| 06 | Blues | Crossroads at Dawn |
| 07 | Latin Bossa | Rua do Sol |
| 08 | House | Open Till Sunrise |
| 09 | Techno | Circuit After Dark |
| 10 | Trance | Above the Horizon |
| 11 | Feature Demo | Shifting Ground |

The demo collection is also available separately:

`OSTF_v3.2_Demo_Song.zip`

All 11 demo songs are provided in OSTF 3.2 format.

### Demo Version Management

Demo song files use version-specific naming, such as:

`OSTF3.2_Demo_01_Pop_City_Lights_Again.ostf`

This allows demo collections to be maintained independently of the Player software version.

Future OSTF specification updates may be accompanied by updated demo collections without changing the original OSTF 3.2 examples.

## About OSTF

**OSTF (Open Song Timeline Format)** is a structured song data format designed to represent musical compositions and arrangements along a timeline.

It can describe:

- Song sections and structure
- Chord progressions
- Key, tempo, and time signature
- Melody information
- Lyrics and pronunciation
- Arrangement tracks
- MIDI-related performance data
- Musical metadata

OSTF is intended to support interoperability between songwriting, arrangement, playback, and music production tools.

OSTF Player is part of the broader OSTF ecosystem.

### Related Projects

- [Open Song Timeline Format 3.0](https://github.com/yoh-nak/Open-Song-Timeline-Format-3.0)
- [OSTF Player for Max for Live](https://github.com/yoh-nak/OSTF-Player-M4L)

## Design Philosophy

OSTF Player focuses on three main purposes:

**Visualization**

Understand the structure of a complete song without manually opening and inspecting multiple MIDI clips.

**Playback**

Preview musical arrangements using an integrated lightweight sound engine.

**Interoperability**

Use structured song information across compatible OSTF tools and Ableton Live workflows.

The Player is intended to provide a convenient reference environment for OSTF compositions and arrangements.

## Limitations

- Built-in instrument sounds are designed primarily for preview purposes.
- Sound quality and timing may depend on the host environment.
- Complex OSTF arrangements may require additional processing resources.
- Not all DAW-specific features are represented in OSTF.
- Compatibility with every OSTF file variation is not guaranteed.
- Some advanced operations may depend on the installed Max for Live environment.

## Version History

### v1.0 — Initial Public Release

- OSTF 3.0–3.2 file support
- Interactive Song and Tracks views
- Chord and melody visualization
- Synchronized lyric display
- Internal instrument and drum playback
- Automatic instrument preview assignment
- Key transposition
- Customizable lead sheet PDF export
- Independent print key
- MIDI export functionality
- 11 OSTF 3.2 demonstration songs
- Compact Max for Live device interface
- Playback and interface performance optimizations

## Credits

**Software Development:** yoh-nak  
**GitHub:** https://github.com/yoh-nak

The demonstration compositions are provided as OSTF example material. Software development credit does not imply authorship of the demo compositions, lyrics, or arrangements.

## License and Copyright

A software license has not yet been specified in this repository.

Unless a separate license is provided, no additional permission to copy, modify, redistribute, or commercially use the software is granted merely by making the repository public.

Demo song materials may have separate rights and usage conditions.

---

**OSTF Player v1.0 — Open Song Timeline Format Player for Ableton Live / Max for Live**
