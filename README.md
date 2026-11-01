# OSTF Player for Max for Live

**Version 1.3.2 — OSTF 3.5 Support**

**OSTF Player** is a free, interactive song player, visualizer, and lead sheet tool for **Ableton Live / Max for Live**, powered by the **Open Song Timeline Format (OSTF)**.

Load and explore complete songs—including sections, chord progressions, melodies, lyrics, arrangement tracks, and detailed note-performance information—in one interface. Preview arrangements with the built-in sound engine, transpose the music, inspect MIDI notes, and export printable lead sheets.

The device includes **13 instrument sound definitions, 4 drum kits, and 11 built-in OSTF 3.5 demo songs**.

> **Current versions:** OSTF Player **v1.3.2** supports the **OSTF 3.5 standard** while retaining compatibility with OSTF 3.0–3.4 files where possible. The separately downloadable demo collection uses **OSTF 3.5**. The Player version and the OSTF file-format version are maintained independently.

## Features

### OSTF File Support

OSTF Player v1.3.2 uses the **standard OSTF data model** for song metadata, timeline information, harmony, lyrics, tracks, presentation data, and note-performance state.

- Full support for standard **OSTF 3.5** song files.
- Compatibility with OSTF 3.0, 3.1, 3.2, 3.3, and 3.4 files where possible.
- Read song key information from standard OSTF fields.
- Read key changes from the standard OSTF timeline.
- Read genre metadata directly from standard OSTF song metadata.
- Read tempo and meter changes from the OSTF timeline.
- Read song credits and contributor information from standard OSTF fields.
- Read chord voicing information from standard harmony data.
- Read primary melody and lyric-document references from standard OSTF fields.
- Read standard presentation information where available.
- Read OSTF 3.5 note-performance state.
- Preserve the source OSTF file during playback, visualization, and temporary transposition.

## OSTF 3.5 Note State Support

OSTF 3.5 expands note-level performance information.

OSTF Player v1.3.2 supports standard OSTF 3.5 fields including:

- `enabled`
- `releaseVelocity`
- `probability`
- `velocityDeviation`
- `pitchRole`
- `phraseInstance.noteStateMode`

### Enabled / Muted Notes

Notes with:

`enabled: false`

remain part of the OSTF song data but are not sounded during normal Player playback.

The Player does not remove these notes from the source song simply because they are disabled.

### Release Velocity

OSTF 3.5 can store a separate Note Off velocity using:

`releaseVelocity`

OSTF Player preserves this information when supported by the destination workflow.

### Note Probability

OSTF 3.5 supports note-level probability.

The Player can use this information during preview playback without permanently rewriting the source song.

Probability is treated as performance behavior rather than as a destructive modification to the original OSTF data.

### Velocity Deviation

OSTF 3.5 can describe controlled variation around the stored note velocity.

OSTF Player can interpret this information during playback while keeping the original stored velocity unchanged.

### Musical Notes and Fixed Triggers

OSTF 3.5 introduces note pitch roles such as:

- `musical`
- `fixedTrigger`

A **musical** note participates in musical pitch operations such as transposition.

A **fixedTrigger** represents a MIDI note whose absolute note number must remain fixed—for example:

- Key switches
- Drum-style triggers
- Articulation switches
- Device-specific trigger notes
- Other non-pitched performance controls represented as MIDI notes

When the song is transposed, **fixedTrigger notes are not transposed**.

This prevents musical transposition from accidentally changing articulation switches or other fixed MIDI triggers.

## No Player-Specific OSTF Metadata Extensions

OSTF Player does not depend on Player-specific metadata extensions for information already defined by the OSTF standard.

Key, genre, credits, voicing, lyric selection, track roles, note state, and other supported information are obtained from the corresponding **standard OSTF fields**.

This allows standard OSTF files created by compatible OSTF applications to be loaded without requiring OSTF Player-specific metadata.

The Player does not automatically invent missing metadata.

For example:

- A missing key is not automatically treated as C major.
- A missing genre is not automatically treated as Pop.
- Track roles are not inferred only from track names.
- Fixed triggers are not treated as transposable musical notes.
- Standard OSTF metadata is preferred over application-specific assumptions.

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

The playback cursor is displayed above the timeline content so that the current playback position remains visible across chord clips and related timeline elements.

## Tracks View

Inspect individual arrangement tracks:

- Piano-roll visualization
- Instrument and MIDI note information
- Track-level controls and playback navigation
- Arrangement inspection and MIDI-oriented workflows
- OSTF 3.5 note-state information
- Display of OSTF tracks without hiding them based only on Player-specific track-name assumptions

OSTF Player uses the information stored in the OSTF file when identifying melody, lyric, arrangement, and performance data.

## Lyrics

OSTF supports multiple lyric documents.

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
- Velocity-sensitive performance
- OSTF 3.5 note-state interpretation

The internal sound engine is intended for song previews and structural inspection, not as a replacement for professional sample libraries or dedicated virtual instruments.

Playback uses the performance-note information stored in the OSTF song.

OSTF Player does not generate additional performance notes from chord voicing snapshots or other descriptive metadata during normal playback.

## Key Transposition & Key Diagrams

- Transpose songs in semitone steps.
- Update displayed key and chord information.
- Restore the original key at any time.
- Read the original key from standard OSTF song data.
- Follow standard OSTF timeline key changes.
- Preserve `fixedTrigger` MIDI note numbers during transposition.
- Inspect the **Camelot Key Wheel** and **Circle of Fifths**.
- Distinguish original and current keys in the key diagrams.
- Use an independent key for lead sheet printing without changing the Player's current setting.

OSTF Player distinguishes between:

- Original song key
- Current playback-position key
- Timeline key changes
- Temporary Player transposition
- Independent print transposition
- Musical notes
- Fixed MIDI trigger notes

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

The Player also handles timeline situations such as:

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

Where possible, OSTF 3.5 note information is preserved appropriately.

### MIDI Export Behavior

- Musical notes follow the selected transposition.
- `fixedTrigger` notes retain their original MIDI note number.
- Release Velocity can be represented as Note Off velocity where supported.
- Disabled notes are not treated as normally sounding notes.
- Probability and Velocity Deviation are not automatically baked into a permanently randomized MIDI performance.

OSTF contains information that cannot always be represented exactly by a conventional Standard MIDI File. The Player avoids silently converting OSTF-specific performance semantics into destructive random MIDI data.

## Requirements

- Ableton Live with **Max for Live** support
- A compatible Max for Live / Max environment
- Windows or macOS
- External `.ostf` files if you want to load songs other than the built-in demos

The device is distributed as a single `.amxd` file. No external instrument plug-in is required for basic built-in sound previews.

**Compatibility note:** Exact Ableton Live, Max, and operating-system combinations have not been certified exhaustively. Behavior and performance can depend on your host environment.

## Installation

1. Download `OSTF_Player_v1.3.2.amxd` from this repository.
2. Open Ableton Live.
3. Create or select a MIDI track.
4. Drag the `.amxd` file onto the MIDI track.
5. Click **Open** in the compact device view.
6. Select a built-in demo or load an external `.ostf` song file.

If you already have an earlier release installed, keep a backup of your previous device and Live Set before replacing it with v1.3.2.

## Quick Start

1. **Open the Player:** Click **Open** in the Max for Live device view.
2. **Choose a song:** Select one of the 11 built-in demos or open an external `.ostf` file.
3. **Play:** Use the playback controls to preview the song with the internal instruments and drums.
4. **Explore:** Switch between **Song** and **Tracks** to examine sections, chords, melodies, lyrics, arrangement data, and note state.
5. **Inspect metadata:** Check the song title, genre, key, tempo, and other available standard OSTF information.
6. **Transpose:** Change the key in semitone steps. Fixed-trigger notes remain at their original MIDI note numbers.
7. **Inspect keys:** Open **Key Diagrams** to compare original and transposed positions.
8. **Print:** Open the lead sheet print interface, choose layout and print key, preview, and export a PDF.
9. **Work with MIDI:** Use the available MIDI export tools when you want to continue editing the arrangement in your DAW.

## Included Demo Songs

The Player includes 11 demo songs using the **OSTF 3.5 standard**:

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

**`OSTF_v3.5_Demo_Song.zip`**

It contains the 11 demo songs as standard OSTF 3.5 files.

The demo songs do not require OSTF Player-specific metadata extensions for information already defined by the OSTF standard.

### Demo Version Management

Demo filenames identify the **OSTF file-format version**, for example:

`OSTF3.5_Demo_01_Pop_City_Lights_Again.ostf`

This makes it possible to update the demo collection when the OSTF specification changes while keeping older examples available for compatibility testing.

**OSTF Player v1.3.2** and **OSTF 3.5** are separate version numbers.

## OSTF 3.5 Standard Data Used by the Player

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
- `enabled`
- `releaseVelocity`
- `probability`
- `velocityDeviation`
- `pitchRole`
- `phraseInstance.noteStateMode`

Information already defined by OSTF is represented using the OSTF standard rather than duplicated in a Player-specific private metadata layer.

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
- Note enable / mute state
- Release Velocity
- Note Probability
- Velocity Deviation
- Musical and fixed-trigger pitch roles
- Song metadata including genres, languages, moods, and credits
- Presentation information
- Detailed timeline-based musical information

OSTF is intended to make structured musical information easier to exchange, inspect, and reuse across songwriting, arrangement, performance, visualization, and music-production tools.

### Related Projects

- [Open Song Timeline Format 3.5](https://github.com/yoh-nak/Open-Song-Timeline-Format-3.5)
- [OSTF Player for Max for Live](https://github.com/yoh-nak/OSTF-Player-M4L)

## Design Philosophy

**Standards-first:** Use the OSTF specification as the source of truth instead of introducing Player-specific representations of information already defined by OSTF.

**Visualization:** Understand a complete song without manually inspecting multiple MIDI clips.

**Playback:** Preview musical arrangements using an integrated lightweight sound engine.

**Interoperability:** Work with structured song data across compatible OSTF tools and Ableton Live workflows.

**Non-destructive behavior:** Keep loaded OSTF song data unchanged during normal playback, visualization, and temporary transposition.

**Semantic preservation:** Do not transpose, randomize, discard, or reinterpret OSTF performance information when the destination format cannot represent it accurately.

## Limitations

- Built-in instrument sounds are designed primarily for preview purposes.
- Sound quality, timing, and CPU use depend on the host environment.
- Complex arrangements may require additional processing resources.
- Not all DAW-specific functionality is represented in OSTF.
- Not every OSTF feature can be represented exactly in Standard MIDI Files.
- Compatibility with every possible legacy or non-standard OSTF file is not guaranteed.
- Some advanced operations depend on the installed Max for Live environment.
- Camelot indications for non-major/minor modes may be approximate.
- Older OSTF files that stored important information only in non-standard application-specific extensions may not expose that information as standard OSTF metadata.
- Ableton Live / Max host behavior can vary depending on application and operating-system versions.

## Version History

### v1.3.2 — OSTF 3.5 Support & Playback Cursor Fix

- Add support for the OSTF 3.5 standard.
- Update the 11 built-in demo songs to OSTF 3.5.
- Add a separately downloadable OSTF 3.5 demo-song collection.
- Add support for note `enabled` state.
- Add support for Release Velocity.
- Add support for note Probability.
- Add support for Velocity Deviation.
- Add support for `pitchRole`.
- Preserve `fixedTrigger` MIDI note numbers during transposition.
- Add support for OSTF 3.5 phrase note-state behavior.
- Preserve standard OSTF metadata handling introduced in v1.2.0.
- Maintain compatibility with OSTF 3.0–3.4 where possible.
- Fix Song View playback-cursor layering.
- Keep the yellow playback cursor above chord clips and timeline elements.

### v1.2.0 — Full OSTF 3.4 Standard Support

- Add support for the OSTF 3.4 standard.
- Update the 11 built-in demo songs to OSTF 3.4.
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

**OSTF Player v1.3.2 — OSTF 3.5 Player for Ableton Live / Max for Live**
