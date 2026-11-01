# OSTF Player for Max for Live

**Version 1.2.0 — Full OSTF 3.4 Standard Support**

**OSTF Player** is a free, interactive song player, visualizer, and lead sheet tool for **Ableton Live / Max for Live**, powered by the **Open Song Timeline Format (OSTF)**.

Load and explore complete songs—including sections, chord progressions, melodies, lyrics, and arrangement tracks—in one interface. Preview arrangements with the built-in sound engine, transpose the music, inspect MIDI notes, and export printable lead sheets.

The device includes **13 instrument sound definitions, 4 drum kits, and 11 built-in OSTF 3.4 demo songs**.

> **Current versions:** OSTF Player **v1.2.0** is designed for the **OSTF 3.4 standard**. Compatibility with OSTF 3.0–3.3 files is retained where possible. The separately downloadable demo collection uses **OSTF 3.4**. The Player version and OSTF file-format version are maintained independently.

## Features

### OSTF File Support

OSTF Player v1.2.0 uses the **standard OSTF data model** for song metadata, timeline information, harmony, lyrics, tracks, and presentation data.

- Full support for standard **OSTF 3.4** song files.
- Compatibility with OSTF 3.0, 3.1, 3.2, and 3.3 files where possible.
- Read song key information from standard OSTF key fields.
- Read key changes from the standard OSTF timeline.
- Read genre metadata directly from standard OSTF song metadata.
- Read tempo and meter changes from the OSTF timeline.
- Read song credits and contributor information from standard OSTF fields.
- Read chord voicing information from standard harmony data.
- Read primary melody and lyric-document references from standard OSTF fields.
- Read standard presentation information where available.
- Preserve the source OSTF file during playback, visualization, and temporary transposition.

### No Player-Specific OSTF Metadata Extensions

Beginning with v1.2.0, OSTF Player no longer depends on Player-specific metadata extensions for information that is defined by the OSTF standard.

Key, genre, credits, voicing, lyric selection, track roles, and other supported song information are obtained from the corresponding **standard OSTF fields**.

This allows standard OSTF 3.4 files created by compatible OSTF applications to be loaded without requiring OSTF Player-specific metadata.

The Player does not automatically invent missing metadata.

For example:

- A missing key is not automatically treated as C major.
- A missing genre is not automatically treated as Pop.
- Track roles are not inferred only from track names.
- Standard song metadata is preferred over application-specific assumptions.

## Song View

Explore a complete song using an interactive timeline:

- Song sections and chord progressions
- Melody visualization and pitch information
- Synchronized lyric and pronunciation displays
- Playback-position highlighting
- Timeline navigation and adjustable zoom
- Song title, genre, tempo, key, and transpose controls
- Key changes during the song
- Standard OSTF presentation information where available

## Tracks View

Inspect individual arrangement tracks:

- Piano-roll visualization
- Instrument and MIDI note information
- Track-level controls and playback navigation
- Arrangement inspection and MIDI-oriented workflows
- Display of OSTF tracks without hiding them based only on Player-specific track-name assumptions

OSTF Player v1.2.0 uses the information stored in the OSTF file when identifying important melody, lyric, and arrangement data.

## Lyrics

OSTF 3.4 can contain multiple lyric documents.

OSTF Player supports lyric-document selection while preserving the source song structure.

- Display synchronized lyrics
- Display pronunciation information where available
- Switch between available lyric documents
- Respect the standard primary lyric-document reference when provided
- Avoid merging unrelated lyric documents into one combined lyric display

This is useful for songs containing alternate lyrics, translations, pronunciation guides, or multiple vocal-related documents.

## Built-in Sound Engine

Preview songs without loading additional instrument plugins:

- 13 built-in instrument sound definitions
- 4 drum kits
- Automatic instrument preview assignment
- Polyphonic playback
- Basic velocity-sensitive performance

The internal sound engine is intended for song previews and structural inspection, not as a replacement for professional sample libraries or dedicated virtual instruments.

Playback uses the performance-note information stored in the OSTF song.

OSTF Player does not generate additional performance notes from chord voicing snapshots or other descriptive metadata during normal playback.

## Key Transposition & Key Diagrams

- Transpose songs in semitone steps.
- Update displayed key and chord information.
- Restore the original key at any time.
- Read the original key from standard OSTF song data.
- Follow standard OSTF timeline key changes.
- Inspect the **Camelot Key Wheel** and **Circle of Fifths**.
- Distinguish original and current keys in the key diagrams.
- Use an independent key for lead sheet printing without changing the Player's current setting.

OSTF Player v1.2.0 improves the distinction between:

- Original song key
- Current playback-position key
- Timeline key changes
- Temporary Player transposition
- Independent print transposition

A missing or non-major/minor key is not silently converted to C major.

> **Music theory note:** Camelot notation is primarily based on major and minor keys. For modes such as Blues or other non-major/minor systems, the Player may show an approximate relationship where appropriate rather than claiming an exact standard Camelot assignment.

## Timeline Support

OSTF Player reads standard timeline information including:

- Tempo changes
- Meter changes
- Key changes
- Song sections
- Harmonic events
- Arrangement events

v1.2.0 also improves handling of timeline situations such as:

- Pickup / anacrusis regions
- Meter changes within a song
- Notes extending across clip or structural boundaries
- Simultaneous MIDI-style events
- Song material extending beyond nominal section boundaries

## Lead Sheet & PDF Export

Generate printable chord charts and lead sheets with:

- Paper and portrait/landscape settings
- Chord symbols, lyrics, and section labels
- Bar numbers and song credits
- Font and spacing adjustments
- Page scaling and layout options
- Independent print key selection
- Print preview before PDF export

Song metadata used by the lead sheet is taken from the standard OSTF song data whenever available.

## MIDI Export

Generate MIDI material from OSTF melody and arrangement information for further use in Ableton Live and other MIDI workflows.

## Requirements

- Ableton Live with **Max for Live** support
- A compatible Max for Live / Max environment
- Windows or macOS
- External `.ostf` files if you want to load songs other than the built-in demos

The device is distributed as a single `.amxd` file. No external instrument plug-in is required for basic built-in sound previews.

**Compatibility note:** Exact Ableton Live, Max, and operating-system combinations have not been certified exhaustively. Behavior and performance can depend on your host environment.

## Installation

1. Download `OSTF_Player_v1.2.0.amxd` from this repository.
2. Open Ableton Live.
3. Create or select a MIDI track.
4. Drag the `.amxd` file onto the MIDI track.
5. Click **Open** in the compact device view.
6. Select a built-in demo or load an external `.ostf` song file.

If you already have an earlier release installed, keep a backup of your previous device and Live Set before replacing it with v1.2.0.

## Quick Start

1. **Open the Player:** Click **Open** in the Max for Live device view.
2. **Choose a song:** Select one of the 11 built-in demos or open an external `.ostf` file.
3. **Play:** Use the playback controls to preview the song with the internal instruments and drums.
4. **Explore:** Switch between **Song** and **Tracks** to examine sections, chords, melodies, lyrics, and arrangement data.
5. **Inspect metadata:** Check the song title, genre, key, tempo, and other available standard OSTF information.
6. **Transpose:** Change the key in semitone steps. Open **Key Diagrams** to compare original and transposed positions.
7. **Print:** Open the lead sheet print interface, choose layout and print key, preview, and export a PDF.
8. **Work with MIDI:** Use the available MIDI export tools when you want to continue editing the arrangement in your DAW.

## Included Demo Songs

The Player includes 11 demo songs using the **OSTF 3.4 standard**:

| No. | Genre | Song title | Initial key |
| --- | --- | --- | --- |
| 01 | Pop | City Lights Again | C major |
| 02 | Rock | Against the Current | E minor |
| 03 | Ballad | The Last Train Home | G major |
| 04 | Jazz Swing | After Midnight | Bb major |
| 05 | Jazz Bebop | Corner Changes | F major |
| 06 | Blues | Crossroads at Dawn | A blues |
| 07 | Latin Bossa | Rua do Sol | C major |
| 08 | House | Open Till Sunrise | A minor |
| 09 | Techno | Circuit After Dark | C minor |
| 10 | Trance | Above the Horizon | E minor |
| 11 | Progressive Pop / Fusion | Shifting Ground — Feature Demo | C major |

The separately downloadable demo archive is:

**`OSTF_v3.4_Demo_Song.zip`**

It contains the 11 demo songs as standard OSTF 3.4 files.

The demo songs do not require OSTF Player-specific metadata extensions for standard information such as key and genre.

### Demo Version Management

Demo filenames identify the **OSTF file-format version**, for example:

`OSTF3.4_Demo_01_Pop_City_Lights_Again.ostf`

This makes it possible to update the demo collection when the OSTF specification changes while keeping older examples available for compatibility testing.

**OSTF Player v1.2.0** and **OSTF 3.4** are separate version numbers.

## OSTF 3.4 Standard Data Used by the Player

Where available, OSTF Player uses standard OSTF structures including:

- `song.key`
- `song.genres`
- `song.languages`
- `song.moods`
- `song.credits`
- `song.primaryMelodyTrackId`
- `song.primaryLyricDocumentId`
- `contributors`
- `timeline.tempoChanges`
- `timeline.meterChanges`
- `timeline.keyChanges`
- `harmony.chords`
- Standard chord voicing information
- Standard track and performance-note data
- Standard lyric documents
- Standard presentation information

This is an important architectural change in v1.2.0.

Information already defined by OSTF should be represented by the OSTF standard rather than duplicated in a Player-specific private metadata layer.

## About OSTF

**OSTF (Open Song Timeline Format)** is a structured song data format for describing musical compositions and arrangements along a timeline.

OSTF data can describe:

- Song sections and structure
- Chord progressions and harmonic information
- Key and key changes
- Tempo and tempo changes
- Meter and meter changes
- Melody and lyric information
- Multiple lyric documents
- Pronunciation and lyric alignment
- Instrument and arrangement tracks
- MIDI-related performance data
- Song metadata including genres, languages, moods, and credits
- Presentation information
- Detailed timeline-based musical information

OSTF is intended to make structured musical information easier to exchange, inspect, and reuse across songwriting, arrangement, performance, visualization, and music-production tools.

### Related Projects

- [Open Song Timeline Format 3.4](https://github.com/yoh-nak/Open-Song-Timeline-Format-3.4)
- [OSTF Player for Max for Live](https://github.com/yoh-nak/OSTF-Player-M4L)

## Design Philosophy

**Standards-first:** Use the OSTF specification as the source of truth instead of introducing Player-specific representations of information already defined by OSTF.

**Visualization:** Understand a complete song without manually inspecting multiple MIDI clips.

**Playback:** Preview musical arrangements using an integrated lightweight sound engine.

**Interoperability:** Work with structured song data across compatible OSTF tools and Ableton Live workflows.

**Non-destructive behavior:** Keep loaded OSTF song data unchanged during normal playback, visualization, and temporary transposition.

## Limitations

- Built-in instrument sounds are designed primarily for preview purposes.
- Sound quality, timing, and CPU use depend on the host environment.
- Complex arrangements may require additional processing resources.
- Not all DAW-specific functionality is represented in OSTF.
- Compatibility with every possible legacy or non-standard OSTF file is not guaranteed.
- Some advanced operations depend on the installed Max for Live environment.
- Camelot indications for non-major/minor modes may be approximate.
- Older OSTF files that stored important information only in non-standard application-specific extensions may not expose that information as standard OSTF metadata.
- Ableton Live / Max host behavior can vary depending on application and operating-system versions.

## Version History

### v1.2.0 — Full OSTF 3.4 Standard Support

- Add support for the OSTF 3.4 standard.
- Update the 11 built-in demo songs to OSTF 3.4.
- Add a separately downloadable OSTF 3.4 demo-song collection.
- Remove dependencies on Player-specific extensions for information defined by the OSTF standard.
- Read song key information from standard OSTF fields.
- Read timeline key changes from standard OSTF fields.
- Read genre information from standard OSTF song metadata.
- Use standard song credits and contributor information.
- Use standard chord voicing information.
- Use standard primary melody and primary lyric-document references.
- Improve handling of multiple lyric documents.
- Improve track display and avoid hiding tracks based only on Player-specific naming assumptions.
- Improve original-key, timeline-key, transposition, and print-key handling.
- Avoid treating an unspecified key as C major.
- Preserve support for older OSTF 3.0–3.3 files where possible.
- Preserve existing playback, visualization, MIDI, key-diagram, and lead-sheet features.

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

**OSTF Player v1.2.0 — OSTF 3.4 Standard Player for Ableton Live / Max for Live**
