# OSTF Player for Max for Live

**Version 1.1.3 — OSTF 3.3 Support & UI Improvements**

**OSTF Player** is a free, interactive song player, visualizer, and lead sheet tool for **Ableton Live / Max for Live**, powered by the **Open Song Timeline Format (OSTF)**.

Load and explore complete songs—including sections, chord progressions, melodies, lyrics, and arrangement tracks—in one interface. Preview arrangements with the built-in sound engine, transpose the music, inspect MIDI notes, and export printable lead sheets.

The device includes **13 instrument sound definitions, 4 drum kits, and 11 built-in demo songs**.

> **Current versions:** OSTF Player **v1.1.3** supports **OSTF 3.0–3.3**. The separately downloadable demo collection uses **OSTF 3.3**. The Player version and the OSTF file-format version are maintained independently.

## Features

### OSTF File Support (3.0–3.3)

- Load `.ostf` song files from OSTF 3.0, 3.1, 3.2, and 3.3.
- Display song sections, chords, key, tempo, meter, and arrangement data.
- Read **genre metadata directly from OSTF 3.3 song files**, including multiple genres when provided.
- Display the file's genre information in the song interface instead of relying on a hard-coded preset classification.
- Keep the source OSTF file unchanged during playback, visualization, and transposition.
- Continue to read older OSTF files that do not contain genre metadata; their genre is not guessed or automatically set to Pop.

Genre metadata is descriptive information. It does **not** automatically change the selected instrument sounds or the musical arrangement.

### Song View

Explore a complete song using an interactive timeline:

- Song sections and chord progressions
- Melody visualization and pitch information
- Synchronized lyric and pronunciation displays
- Playback-position highlighting
- Timeline navigation and adjustable zoom
- Compact, single-row song information, tempo, key, and transpose controls

### Tracks View

Inspect individual arrangement tracks:

- Piano-roll visualization
- Instrument and MIDI note information
- Track-level controls and playback navigation
- Arrangement inspection and MIDI-oriented workflows

### Built-in Sound Engine

Preview songs without loading additional instrument plugins:

- 13 built-in instrument sound definitions
- 4 drum kits
- Automatic instrument preview assignment
- Polyphonic playback
- Basic velocity-sensitive performance

The internal sound engine is intended for song previews and structural inspection, not as a replacement for professional sample libraries or dedicated virtual instruments.

### Key Transposition & Key Diagrams

- Transpose songs in semitone steps.
- Update displayed key and chord information.
- Restore the original key at any time.
- Inspect the **Camelot Key Wheel** and **Circle of Fifths**.
- Distinguish original and current keys in the key diagrams.
- Use an independent key for lead sheet printing without changing the Player's current setting.

The v1.1.3 update improves key-color highlighting after transposition, synchronization between the key displays and diagrams, and the key-diagram modal layout.

> **Music theory note:** Camelot notation is primarily based on major and minor keys. For modes such as Blues, the Player may show an approximate Camelot relationship rather than claiming an exact standard Camelot assignment.

### Lead Sheet & PDF Export

Generate printable chord charts and lead sheets with:

- Paper and portrait/landscape settings
- Chord symbols, lyrics, and section labels
- Bar numbers and song credits
- Font and spacing adjustments
- Page scaling and layout options
- Independent print key selection
- Print preview before PDF export

### MIDI Export

Generate MIDI material from OSTF melody and arrangement information for further use in Ableton Live and other MIDI workflows.

## Requirements

- Ableton Live with **Max for Live** support
- A compatible Max for Live / Max environment
- Windows or macOS
- External `.ostf` files if you want to load songs other than the built-in demos

The device is distributed as a single `.amxd` file. No external instrument plug-in is required for basic built-in sound previews.

**Compatibility note:** Exact Ableton Live, Max, and operating-system combinations have not been certified exhaustively. Behavior and performance can depend on your host environment.

## Installation

1. Download `OSTF_Player_v1.1.3.amxd` from this repository.
2. Open Ableton Live.
3. Create or select a MIDI track.
4. Drag the `.amxd` file onto the MIDI track.
5. Click **Open** in the compact device view.
6. Select a built-in demo or load an external `.ostf` song file.

If you already have an earlier release installed, keep a backup of your previous device and Live Set before replacing it with v1.1.3.

## Quick Start

1. **Open the Player:** Click **Open** in the Max for Live device view.
2. **Choose a song:** Select one of the 11 built-in demos or open an external `.ostf` file.
3. **Play:** Use the playback controls to preview the song with the internal instruments and drums.
4. **Explore:** Switch between **Song** and **Tracks** to examine sections, chords, melodies, lyrics, and arrangement data.
5. **Inspect metadata:** Check the song title, genre information (where present), key, and tempo.
6. **Transpose:** Change the key in semitone steps. Open **Key Diagrams** to compare original and transposed positions.
7. **Print:** Open the lead sheet print interface, choose layout and print key, preview, and export a PDF.
8. **Work with MIDI:** Use the available MIDI export tools when you want to continue editing the arrangement in your DAW.

## Included Demo Songs

The Player includes 11 demo songs across a variety of genres:

| No. | Genre | Song title |
| --- | --- | --- |
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

The separately downloadable demo archive is:

**`OSTF_v3.3_Demo_Song.zip`**

It contains the 11 songs as OSTF 3.3 files, with genre metadata stored in the song data.

### Demo Version Management

Demo filenames identify the **OSTF file-format version**, for example:

`OSTF3.3_Demo_01_Pop_City_Lights_Again.ostf`

This makes it possible to update the demo collection when the OSTF specification changes while keeping older examples available for compatibility testing. **OSTF Player v1.1.3** and **OSTF 3.3** are separate version numbers.

## About OSTF

**OSTF (Open Song Timeline Format)** is a structured song data format for describing musical compositions and arrangements along a timeline.

OSTF data can describe:

- Song sections and structure
- Chord progressions and harmonic information
- Key, tempo, and time signature
- Melody and lyric information
- Pronunciation and lyric alignment
- Instrument and arrangement tracks
- MIDI-related performance data
- Song metadata, including **genre information in OSTF 3.3**

OSTF is intended to make structured musical information easier to exchange, inspect, and reuse across songwriting, arrangement, and music production tools.

### Related Projects

- [Open Song Timeline Format 3.0](https://github.com/yoh-nak/Open-Song-Timeline-Format-3.0)
- [OSTF Player for Max for Live](https://github.com/yoh-nak/OSTF-Player-M4L)

## Design Philosophy

**Visualization:** Understand a complete song without manually inspecting multiple MIDI clips.

**Playback:** Preview musical arrangements using an integrated lightweight sound engine.

**Interoperability:** Work with structured song data across compatible OSTF tools and Ableton Live workflows.

## Limitations

- Built-in instrument sounds are designed primarily for preview purposes.
- Sound quality, timing, and CPU use depend on the host environment.
- Complex arrangements may require additional processing resources.
- Not all DAW-specific functionality is represented in OSTF.
- Compatibility with every possible OSTF variation is not guaranteed.
- Some advanced operations depend on the installed Max for Live environment.
- Camelot indications for non-major/minor modes may be approximate.

## Version History

### v1.1.3 — OSTF 3.3 Compatibility & Key Display Fixes

- Support OSTF 3.3, including genre metadata read from song files.
- Maintain compatibility with OSTF 3.0–3.2.
- Update the 11-song demo collection to OSTF 3.3.
- Consolidate song metadata, tempo, key, and transpose settings into a single compact header row.
- Correct Camelot color highlighting after transposition.
- Improve original/current key highlighting in Camelot and Circle of Fifths diagrams.
- Improve key-diagram modal layout and resizing for smaller windows.
- Preserve existing playback, lyric, MIDI, and PDF features.

### v1.0 — Initial Public Release

- OSTF 3.0–3.2 file support
- Interactive Song and Tracks views
- Chord, melody, and arrangement visualization
- Synchronized lyrics and pronunciation
- Built-in instruments and drum kits
- Automatic instrument preview assignment
- Key transposition and key diagrams
- Customizable lead sheet PDF export, including an independent print key
- MIDI export functionality
- 11 demonstration songs
- Compact Max for Live device launcher
- Playback and interface performance improvements

## Support Development — Buy Me a Coffee

OSTF Player is developed independently and made available **free of charge**.

If you enjoy the device and would like to support future improvements, new OSTF features, and additional free Max for Live tools, you can make a voluntary contribution:

**[☕ Buy Me a Coffee — yohsukenak](https://buymeacoffee.com/yohsukenak)**

Donations are entirely optional. No payment is required to use the device's core features.

## Credits

**Software development:** [yoh-nak](https://github.com/yoh-nak)  
**Project:** Open Song Timeline Format (OSTF)  
**Repository:** https://github.com/yoh-nak/OSTF-Player-M4L

The demo compositions are provided as example song material. Software development credit does not imply personal authorship of the demo compositions, lyrics, or arrangements.

## License and Copyright

A software license has not been specified in this repository. Unless a separate license is provided, public access to the repository does not itself grant permission to redistribute, modify, or commercially reuse the software.

Demo song materials may be subject to separate rights and usage conditions. Check those conditions before redistributing or reusing the music outside the project.

---

**OSTF Player v1.1.3 — Open Song Timeline Format Player for Ableton Live / Max for Live**
