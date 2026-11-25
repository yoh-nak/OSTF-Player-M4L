# OSTF Player for Max for Live

**Version 2.0 — Legacy Release · Development Ended · Continued in OSTF Studio**

> **Development of OSTF Player for Max for Live has ended.**
>
> **OSTF Studio is its successor, and future development is now focused on OSTF Studio.**
>
> This repository documents the existing **OSTF Player v2.0** release for supported **OSTF 3.x / OSTF 4.0** files. **OSTF 5.x support will not be added to this Max for Live device.**

### [Continue with OSTF Studio →](https://github.com/yoh-nak/OSTF-Studio)

### [☕ Support OSTF Studio on Buy Me a Coffee](https://buymeacoffee.com/yohsukenak)

| Project information | Status |
| --- | --- |
| Player version | v2.0 |
| Development | Ended |
| Successor | [OSTF Studio](https://github.com/yoh-nak/OSTF-Studio) |
| Supported formats | Supported OSTF 3.x files and OSTF 4.0 |
| OSTF 5.x in this device | Not supported; no update planned |
| Host | Ableton Live / Max for Live |
| Price | Free |
| Developer | [yoh-nak](https://github.com/yoh-nak) |

The Player version and the OSTF file-format version are maintained independently. **OSTF Player v2.0** does not mean OSTF 2.0, and development of newer OSTF specifications does not extend this device's compatibility automatically.

---

## Why OSTF Player Development Has Ended

OSTF Player helped establish a way to understand a complete song through its structure, chords, melodies, lyrics, arrangements, and performance information. As OSTF has developed, the scope of the format has grown beyond the foundation of this Player implementation.

**OSTF Player's existing Max for Live architecture cannot fully realize the expanded scope of OSTF 5.x.**

For this project, the current implementation has also reached its practical limits for further improvements in the built-in preview engine's sound quality and overall playback performance. Continuing to extend the same design would not provide the foundation needed for the next stage of development.

**Development has therefore moved to OSTF Studio**, where the song model, playback engine, interface, and performance can be developed together in a more flexible application architecture.

The existing Max for Live release remains useful for exploring the supported OSTF 3.x / 4.0 material described below. Future work on the project's broader musical capabilities, sound quality, and performance is now directed toward **OSTF Studio**.

## OSTF Studio — The Next Chapter

**OSTF Studio carries the ideas behind OSTF Player into a dedicated music creation environment.**

The goal is to bring song structure, harmony, melodies, lyrics, arrangements, and performance information together in a workflow that can grow with the OSTF format.

Development priorities include:

- **OSTF 5.x:** making fuller use of the format's expanded musical information and structure.
- **An integrated workflow:** connecting song exploration, composition, and arrangement.
- **A more flexible playback foundation:** creating room to improve the sound engine and musical playback.
- **Performance and responsiveness:** supporting the needs of more complex songs and arrangements.
- **Long-term extensibility:** providing a foundation for future OSTF features and related music creation tools.

These are the priorities guiding ongoing development. For the current implementation, documentation, development progress, and release information, visit the Studio repository.

### [Explore OSTF Studio on GitHub](https://github.com/yoh-nak/OSTF-Studio)

**If you are interested in the future of OSTF, follow OSTF Studio.**

Thank you to everyone who used OSTF Player, shared feedback, and helped shape the project. That experience continues to inform the development of OSTF Studio.

## ☕ Support the Next Chapter — Buy Me a Coffee

**If OSTF Player has helped you explore songs, understand arrangements, or develop musical ideas, please consider supporting its next chapter: OSTF Studio.**

OSTF is independently developed. Your support helps make time available for the work behind:

- **OSTF Studio development.**
- **The Open Song Timeline Format and its continued evolution.**
- Documentation, examples, and demo-song material.
- Related songwriting, composition, and arrangement tools.

### [☕ BUY ME A COFFEE — SUPPORT THE FUTURE OF OSTF](https://buymeacoffee.com/yohsukenak)

**Contributions are entirely voluntary. OSTF Player remains free, and no payment is required to use its core functionality.**

Thank you for supporting independent music software development.

---

## Contents

- [Legacy Player Overview](#legacy-player-overview)
- [Main Features](#main-features)
- [OSTF File Support](#ostf-file-support)
- [MIDI Expression and Note Behavior](#midi-expression-and-note-behavior)
- [Song View](#song-view)
- [Arrangement View and Mixer](#arrangement-view-and-mixer)
- [Preview Instruments and Sound Setup](#preview-instruments-and-sound-setup)
- [Lyrics](#lyrics)
- [Key Transposition and Key Diagrams](#key-transposition-and-key-diagrams)
- [Timeline and Playback](#timeline-and-playback)
- [Lead Sheet and Printing](#lead-sheet-and-printing)
- [MIDI-Oriented Workflows](#midi-oriented-workflows)
- [Included Demo Songs](#included-demo-songs)
- [Requirements](#requirements)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [About OSTF](#about-ostf)
- [Related Projects](#related-projects)
- [Design Philosophy](#design-philosophy)
- [Limitations and Maintenance Status](#limitations-and-maintenance-status)
- [Version History](#version-history)
- [Credits](#credits)
- [License and Copyright](#license-and-copyright)

---

## Legacy Player Overview

**OSTF Player** is a free interactive song player, visualizer, arrangement inspector, and lead sheet tool for **Ableton Live / Max for Live**, powered by the **Open Song Timeline Format (OSTF)**.

Load supported OSTF songs and explore their structure, chord progressions, chord voicings, melodies, lyrics, arrangement tracks, tempo, meter, key changes, MIDI performance data, and expression information in a single interface.

Version 2.0 expanded the earlier OSTF 3.x Player with OSTF 4.0 support, more detailed MIDI-expression visualization, GM Program Change handling, a GM instrument browser, arrangement sound setup, improved built-in preview playback, and playback/UI stability improvements.

**The documentation below describes the existing v2.0 Max for Live release. It does not describe the feature set of OSTF Studio.**

## Main Features

- OSTF 4.0 song playback and visualization.
- Compatibility with supported OSTF 3.x files.
- Song structure and chord progression timeline.
- Chord voicing piano roll.
- Multiple melody and arrangement-track visualization.
- Lyrics and pronunciation display.
- MIDI note and expression inspection.
- Program Change / GM instrument interpretation.
- CC, Pitch Bend, and Aftertouch visualization.
- Built-in lightweight preview sound engine.
- GM 1–128 instrument browser.
- Built-in drum-kit browser.
- Arrangement track mixer and sound setup.
- Song transposition and key diagrams.
- Lead sheet / print workflow.
- MIDI-oriented export workflows.
- 11 built-in OSTF 4.0 demo songs.

## OSTF File Support

OSTF Player v2.0 uses the **standard OSTF data model** for song metadata, timeline information, harmony, lyrics, tracks, presentation information, notes, and MIDI-style performance data.

Supported workflows include:

- Loading standard **OSTF 4.0** song files and supported OSTF 3.x files.
- Reading song title, metadata, genres, and key information.
- Reading timeline key changes, tempo changes, and meter changes.
- Reading song sections, harmonic events, and chord voicings.
- Reading melody tracks and arrangement tracks.
- Reading lyric documents and presentation information where available.
- Reading note-performance information.
- Reading Program Change, CC, Pitch Bend, and Aftertouch information.
- Preserving loaded OSTF data during normal Player playback and visualization.

OSTF Player does not require Player-specific private metadata for information already defined by the OSTF standard.

### OSTF 3.x and OSTF 4.0 Compatibility

OSTF Player v2.0 is designed to open supported **OSTF 3.x** songs and **OSTF 4.0** songs.

Older OSTF files remain useful for compatibility testing and playback. OSTF 4.0 is the format used by the demo collection included with this release.

The Player attempts to use the information actually stored in the file rather than silently inventing missing values:

- A missing key is not automatically treated as C major.
- A missing genre is not automatically treated as Pop.
- Track roles are not determined only from track names.
- Fixed MIDI triggers are not treated as normal transposable musical notes.
- Standard OSTF metadata takes priority over Player-specific assumptions.

**This legacy compatibility scope does not include OSTF 5.x. Support for newer format capabilities belongs to the ongoing OSTF Studio development effort.**

## MIDI Expression and Note Behavior

### OSTF 4.0 MIDI Expression Support

OSTF 4.0 expands the amount of MIDI-oriented performance information that can be stored with a song.

OSTF Player v2.0 can inspect and visualize supported information including:

- Note velocity.
- Release Velocity.
- Enabled / disabled notes.
- Probability.
- Velocity Deviation.
- Pitch roles.
- Program Change.
- Control Change.
- Pitch Bend.
- Aftertouch.

Expression lanes can be inspected alongside piano-roll information where applicable.

The Player is intended to preserve the distinction between the musical composition and its performance information rather than destructively converting everything into plain notes.

### Enabled and Disabled Notes

OSTF notes can remain part of the song data while being disabled for normal playback. For example, a note can contain the following property:

```json
{
  "enabled": false
}
```

This illustrates a property within a note object, not a complete OSTF document.

Disabled notes remain part of the OSTF document but are not treated as normally sounding notes during Player playback.

### Musical Notes and Fixed Triggers

OSTF can distinguish normal pitched musical notes from fixed MIDI triggers.

Typical fixed triggers include:

- Key switches.
- Articulation switches.
- Drum-style triggers.
- Device-specific trigger notes.
- Other MIDI notes whose absolute note number must remain unchanged.

When transposing a song, notes identified as fixed triggers remain at their original MIDI note numbers. This prevents musical transposition from accidentally moving articulation or control notes.

## Song View

**Song View** provides a structural overview of the complete song.

It includes:

- Song sections and chord progression.
- Playback cursor.
- Tempo, meter, and key information.
- Chord voicings and main melody.
- Lyrics and MIDI-expression information.
- Timeline navigation and adjustable time zoom.
- Section navigation.
- Follow Cursor playback behavior.

Chord progression, voicing piano rolls, melody piano rolls, and the playback cursor use a shared song timeline so the current playback position remains synchronized across the interface.

### Chord Voicing Piano Roll

Chord voicings can be inspected in their own piano-roll area.

The display can show:

- Stored voicing notes.
- Note velocity and pitch positions.
- Timeline placement.
- Playback cursor.
- Preview sound assignment.

The voicing display is intended for inspection and auditioning of OSTF harmony data. It does not create additional performance notes simply because a chord contains descriptive voicing information.

### Main Melody

The Main Melody area provides detailed inspection of the primary melody.

Depending on the source OSTF data, the Player can display:

- Melody clips and MIDI notes.
- Velocity.
- CC information.
- Pitch Bend and Aftertouch.
- Program information.
- Lyrics and pronunciation.
- Playback position.

OSTF 4.0 songs can contain richer performance data than conventional note-only MIDI representations.

## Arrangement View and Mixer

### Arrangement View

**Arrangement View** displays the song's individual arrangement tracks.

Each supported track can provide:

- Piano-roll visualization.
- Track role and track order.
- Note information and velocity.
- CC, Pitch Bend, and Aftertouch.
- Level and pan.
- Solo and mute.
- Preview sound.
- Visibility controls.

Arrangement tracks remain part of the OSTF song regardless of whether they are currently visible in the Player. Display visibility and audio mute are separate controls.

### Track Display & Mixer

The Track Display & Mixer area controls arrangement-preview playback.

Available controls include:

- Show / hide track.
- Display ordering.
- Preview sound.
- Level and pan.
- Solo and mute.
- Velocity display options.

These settings are Player-side preview controls. Selecting a different preview sound or mixer setting does not rewrite the source OSTF song.

## Preview Instruments and Sound Setup

### GM Instrument Browser

OSTF Player v2.0 includes a **GM 1–128 instrument browser**. Users can choose preview instruments using familiar General MIDI program names.

The browser organizes the 128 GM programs into the standard 16 families:

1. Piano
2. Chromatic Percussion
3. Organ
4. Guitar
5. Bass
6. Strings
7. Ensemble
8. Brass
9. Reed
10. Pipe
11. Synth Lead
12. Synth Pad
13. Synth Effects
14. Ethnic
15. Percussive
16. Sound Effects

Each family contains eight GM programs.

The browser can be used for Player preview assignment in areas such as chord voicing, melody, arrangement tracks, Track Display & Mixer, and Arrangement Sound Setup.

### GM Program Change Interpretation

OSTF Player can interpret GM Program Change values across the normal **0–127 MIDI program range**, presented as the conventional **GM 1–128** instrument list.

| Capability | Behavior |
| --- | --- |
| GM Program Change interpretation | Supported |
| Instrument browser | GM 1–128 program names |
| Preview sound assignment | Programs map to lightweight internal synthesis families |
| 128 independent professional GM instruments | Not provided |

The internal engine does **not** contain 128 fully sampled General MIDI instruments. It is intended for structural preview playback, song inspection, and arrangement auditioning.

### Built-in Preview Sound Engine

OSTF Player contains a lightweight built-in synthesis engine so supported songs can be auditioned without loading additional instrument plug-ins.

Internal preview families include sounds suited to roles such as:

- Keys and Electric Piano.
- Organ.
- Bass.
- Guitar and Distorted Guitar.
- Strings.
- Lead, Pluck, and Pad.
- Brass / Reed.
- Other general preview roles.

The engine supports:

- Polyphonic playback.
- Velocity-sensitive playback.
- Basic instrument-specific envelopes.
- Basic filtering.
- Program-based preview assignment.
- MIDI-style expression interpretation where supported.
- Automatic instrument preview assignment.

The internal sounds are intentionally lightweight. They are designed for checking song structure, auditioning arrangements, inspecting OSTF files, previewing harmony and melody, and comparing tracks.

**They are not intended to replace professional sample libraries, synthesizers, orchestral libraries, or dedicated instrument plug-ins.**

Further development toward the project's sound-quality and playback goals is now focused on **OSTF Studio**.

### Drum Preview Engine

OSTF Player v2.0 includes four built-in drum preview kits:

- Electronic Kit.
- Acoustic-like Kit.
- Tight Kit.
- 808-style Kit.

Drum tracks use their MIDI drum-note layout while the selected preview kit determines the Player-side sound character.

A dedicated Drum Kit Browser is used instead of treating drum kits as normal GM melodic instruments.

### Arrangement Sound Setup

The **Arrangement Sound Setup** window provides centralized control over Player preview sounds.

It can be used to:

- Inspect current track sound assignments.
- Assign GM instruments.
- Assign drum kits.
- Apply settings to visible tracks.
- Apply settings across song tracks.
- Automatically assign preview sounds based on instrument information.
- Audition individual tracks.

Sound Setup changes affect Player preview behavior and do not rewrite the OSTF source file.

## Lyrics

OSTF supports multiple lyric documents and vocal-related information.

OSTF Player can display:

- Synchronized lyrics.
- Pronunciation information where available.
- Selected lyric documents.
- Primary lyric-document references.
- Melody-related lyric timing.

The Player avoids automatically merging unrelated lyric documents into one combined lyric stream.

This allows OSTF songs to maintain separate documents for main vocal lyrics, alternate lyrics, translations, pronunciation guides, and other vocal parts.

## Key Transposition and Key Diagrams

### Key Transposition

Songs can be transposed directly in the Player.

Available behavior includes:

- Transposition in semitone steps.
- Updated displayed chord and key information.
- Restore Original Key.
- Timeline key-change tracking.
- Fixed-trigger MIDI note-number preservation.
- A distinction between original and temporary playback keys.

OSTF Player distinguishes between the original song key, current timeline key, temporary Player transposition, independent print transposition, musical notes, and fixed MIDI trigger notes.

A missing or non-major/minor key is not silently converted to C major. Non-major/minor tonal systems are not automatically forced into an incorrect major/minor classification.

### Key Diagrams

OSTF Player includes:

- Camelot Key Wheel.
- Circle of Fifths.

These diagrams can be used to compare original and transposed key positions.

> **Music theory note:** Camelot notation is primarily intended for major and minor keys. Modes and non-major/minor tonal systems may only have approximate Camelot relationships.

## Timeline and Playback

### Timeline Support

OSTF Player reads tempo changes, meter changes, key changes, song sections, harmonic events, and arrangement events.

The Player is also designed to handle situations such as:

- Pickup / anacrusis material.
- Meter changes during a song.
- Notes extending across structural boundaries.
- Simultaneous MIDI-style events.
- Material extending beyond nominal section boundaries.

### Playback

Playback can use the Player's internal preview engine without requiring external instruments.

Playback controls include:

- Play, Pause, and Stop.
- Panic.
- Mute All.
- Section navigation.
- Loop / range workflows where available.
- Follow Cursor.

The timeline, piano rolls, and playback cursor are synchronized to the same song-time reference.

## Lead Sheet and Printing

OSTF Player includes a printable lead-sheet workflow.

Available options include:

- Chord symbols and lyrics.
- Section labels and bar numbers.
- Song credits.
- Portrait / landscape layouts.
- Font and spacing adjustments.
- Page scaling.
- Print preview.
- Independent print key selection.

Lead-sheet metadata is taken from standard OSTF song data where available.

The print key can be changed independently without changing the Player's current playback transposition.

## MIDI-Oriented Workflows

OSTF Player can work with melody and arrangement information in MIDI-oriented workflows.

Depending on the destination, some OSTF information can be represented directly while other performance semantics may not have an exact Standard MIDI File equivalent.

General behavior includes:

- Musical notes follow selected transposition.
- Fixed-trigger notes retain their MIDI note number.
- Disabled notes are not treated as normally sounding notes.
- Release Velocity can be preserved where supported.
- OSTF performance information is not intentionally converted into destructive random MIDI data merely for export.

**OSTF can contain richer information than a conventional Standard MIDI File.** MIDI-oriented workflows should not be interpreted as a guarantee that every OSTF feature can be exported without loss.

## Included Demo Songs

OSTF Player v2.0 includes **11 built-in OSTF 4.0 demo songs**.

| No. | Genre | Song Title | Initial Key |
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

The demo songs can also be downloaded separately as:

**`OSTF_v4.0_Demo_Song.zip`**

The archive contains the demo songs as individual standard `.ostf` files.

### Demo Version Management

Demo filenames identify the **OSTF file-format version**, independently from the Player version.

For example:

```text
OSTF4.0_Demo_01_Pop_City_Lights_Again.ostf
```

This distinguishes format-specific demo collections and helps identify material suitable for legacy compatibility testing.

**OSTF Player v2.0** and **OSTF 4.0** are separate version numbers. A newer OSTF demo collection is not automatically compatible with this Player.

## Requirements

- Ableton Live with **Max for Live**.
- A compatible Max / Max for Live environment.
- Windows or macOS.
- External `.ostf` files for songs other than the included demos.

The Player is distributed as a single `.amxd` device. No external instrument plug-in is required for basic preview playback.

> **Compatibility note:** Every possible Ableton Live, Max, operating-system, hardware, and OSTF-file combination has not been exhaustively certified. Performance may vary between host environments. Development has ended, and compatibility with future host or operating-system versions is not guaranteed.

## Installation

1. Download `OSTF_Player_v2.0.amxd` from the [OSTF Player repository](https://github.com/yoh-nak/OSTF-Player-M4L).
2. Open Ableton Live.
3. Create or select a MIDI track.
4. Drag `OSTF_Player_v2.0.amxd` onto the MIDI track.
5. Click **Open** in the compact Max for Live device view.
6. Select a built-in demo or load a supported external `.ostf` file.

If replacing an older OSTF Player version, keeping a backup of the previous device and important Live Sets is recommended.

## Quick Start

1. **Open the Player:** click **Open** in the Max for Live device view.
2. **Choose a song:** select one of the 11 built-in demos or load a supported external `.ostf` file.
3. **Play:** use the Player transport to audition the song.
4. **Explore Song View:** inspect sections, chords, chord voicings, melody, lyrics, and timeline information.
5. **Explore Arrangement View:** inspect individual arrangement tracks and MIDI-expression information.
6. **Choose preview sounds:** use the GM Instrument Browser or Drum Kit Browser.
7. **Adjust the arrangement preview:** use Track Display & Mixer or Arrangement Sound Setup.
8. **Transpose:** change the song key in semitone steps.
9. **Inspect keys:** open Key Diagrams for Camelot and Circle of Fifths information.
10. **Print:** open the lead-sheet interface and choose the desired print layout and key.

## About OSTF

**OSTF (Open Song Timeline Format)** is a structured song-data format for describing musical compositions and arrangements along a timeline.

The OSTF 4.0 data model used by this Player can describe information such as:

- Song structure and sections.
- Chord progressions and chord voicings.
- Keys and key changes.
- Tempo and tempo changes.
- Meter and meter changes.
- Melodies and multiple melody tracks.
- Lyrics, multiple lyric documents, and pronunciation.
- Instrument tracks and arrangement data.
- MIDI notes, Velocity, and Release Velocity.
- Note Probability and Velocity Deviation.
- Program Change and Control Change.
- Pitch Bend and Aftertouch.
- Fixed MIDI triggers.
- Genres, languages, and moods.
- Credits and presentation information.
- Other structured timeline information.

OSTF is intended to make musical information easier to exchange, inspect, edit, visualize, arrange, perform, and reuse across compatible music-production tools.

The format continues to evolve beyond this Player's compatibility scope. **OSTF Studio is the successor project for ongoing work with OSTF 5.x and future capabilities.**

## Related Projects

| Project | Purpose |
| --- | --- |
| [OSTF Studio](https://github.com/yoh-nak/OSTF-Studio) | Successor to OSTF Player and focus of ongoing application development |
| [OSTF Player for Max for Live](https://github.com/yoh-nak/OSTF-Player-M4L) | Legacy Max for Live device, documentation, and demos |
| [Open Song Timeline Format 4.0](https://github.com/yoh-nak/Open-Song-Timeline-Format-4.0) | Format specification used by this Player release and its included demo songs |

## Design Philosophy

These principles informed OSTF Player and continue to guide the broader project.

**Standards-first**  
Use the OSTF specification as the source of truth rather than creating Player-specific replacements for information already represented by OSTF.

**Visualization**  
Make it possible to understand a complete song without manually opening many individual MIDI clips.

**Playback**  
Provide lightweight integrated preview playback for checking song structure and arrangement.

**Interoperability**  
Allow structured song information to move between compatible OSTF applications and DAW workflows.

**Non-destructive behavior**  
Avoid rewriting the loaded OSTF song simply because the Player transposes, previews, hides, solos, mutes, or assigns a temporary preview instrument.

**Semantic preservation**  
Avoid silently converting structured OSTF information into a different meaning merely because another format or playback environment cannot represent it exactly.

## Limitations and Maintenance Status

### Development Status

- **Active development of OSTF Player for Max for Live has ended.**
- **OSTF Studio is the successor and the focus of ongoing development.**
- OSTF Player v2.0 supports the legacy OSTF 3.x / 4.0 workflows documented here.
- **OSTF 5.x support will not be added to this device.**
- Further feature development, sound-quality work, and performance improvements are directed toward OSTF Studio.
- Compatibility with future Ableton Live, Max, or operating-system versions is not guaranteed.

### Existing Player Limitations

- Built-in sounds are intended primarily for preview purposes.
- The GM browser does not represent 128 independent professional sample-based instruments.
- GM programs are mapped to the Player's lightweight internal synthesis system.
- The four internal drum kits are intended for preview playback.
- Sound quality, timing, and CPU usage depend on the host environment.
- Large or highly detailed arrangements may require additional processing resources.
- Not every DAW-specific feature can be represented in OSTF.
- Not every OSTF feature can be represented exactly in Standard MIDI Files.
- Compatibility with every legacy, experimental, or non-standard OSTF file is not guaranteed.
- Some functionality depends on the installed Max for Live environment.
- Camelot relationships for non-major/minor tonal systems may be approximate.
- Host behavior may vary depending on Ableton Live, Max, operating-system, graphics, and hardware versions.

## Version History

### Development Concluded — Continued in OSTF Studio

- End active development of OSTF Player for Max for Live.
- Direct future application development toward OSTF Studio.
- Retain v2.0 documentation for supported OSTF 3.x / 4.0 workflows.
- Clarify that OSTF 5.x support will not be added to this device.
- Redirect voluntary development support toward OSTF Studio and the broader OSTF project.

This is a project-status and documentation update. The Player version remains **v2.0**.

### v2.0 — OSTF 4.0 Player & Major UI / Playback Update

- Add OSTF 4.0 support.
- Retain compatibility with supported OSTF 3.x files.
- Update the 11 built-in demo songs to OSTF 4.0.
- Add a separately downloadable OSTF 4.0 demo-song archive.
- Add richer OSTF 4.0 MIDI-expression visualization.
- Add Program Change interpretation.
- Add CC visualization.
- Add Pitch Bend visualization.
- Add Aftertouch visualization.
- Add GM 1–128 instrument browser.
- Add GM Program Change preview mapping.
- Add dedicated Drum Kit Browser.
- Add Arrangement Sound Setup.
- Add unified per-track preview-sound assignment.
- Improve Track Display & Mixer.
- Improve Song View chord-voicing inspection.
- Improve Main Melody inspection.
- Improve Arrangement View track inspection.
- Improve built-in preview instrument definitions.
- Improve built-in drum preview kits.
- Improve demo-song preview assignments.
- Improve timeline and playback-cursor synchronization.
- Improve piano-roll playback tracking.
- Improve Song View / Arrangement View consistency.
- Improve internal playback stability.
- Preserve standard OSTF metadata rather than replacing it with Player-specific assumptions.

### v1.3.2 — OSTF 3.5 Support & Playback Cursor Fix

- Add OSTF 3.5 support.
- Update the 11 built-in demos to OSTF 3.5.
- Add OSTF 3.5 note-state support.
- Add enabled-note handling.
- Add Release Velocity support.
- Add Probability support.
- Add Velocity Deviation support.
- Add pitch-role support.
- Preserve fixed-trigger MIDI notes during transposition.
- Improve playback-cursor layering.
- Maintain compatibility with earlier OSTF 3.x files where possible.

### v1.2.0 — OSTF 3.4 Standard Support

- Add OSTF 3.4 support.
- Move supported metadata handling to standard OSTF fields.
- Improve key, genre, credits, voicing, lyrics, and track handling.
- Improve multiple lyric-document handling.
- Improve original-key and transposition behavior.

### v1.1.3 — OSTF 3.3 Compatibility & Key Display Fixes

- Add OSTF 3.3 compatibility.
- Add genre metadata support.
- Improve metadata header layout.
- Improve Camelot and Circle of Fifths displays.
- Improve key-diagram modal behavior.

### v1.0 — Initial Public Release

- OSTF song loading.
- Song and arrangement visualization.
- Chord progression display.
- Melody visualization.
- Lyrics and pronunciation.
- Built-in preview instruments.
- Built-in drum kits.
- Key transposition.
- Key diagrams.
- Lead-sheet printing.
- MIDI-oriented workflows.
- Demonstration songs.
- Compact Max for Live launcher.

## Credits

**Software development:** [yoh-nak](https://github.com/yoh-nak)  
**Project:** Open Song Timeline Format (OSTF)  
**Repository:** [OSTF Player for Max for Live](https://github.com/yoh-nak/OSTF-Player-M4L)  
**Successor:** [OSTF Studio](https://github.com/yoh-nak/OSTF-Studio)

The included demo compositions are provided as example song material.

Software-development credit does not necessarily imply personal authorship of every demo composition, lyric, or arrangement.

## License and Copyright

A software license has not been specified in this repository.

Unless a separate license is provided, public access to the repository does not by itself grant permission to redistribute, modify, sublicense, or commercially reuse the software.

Demo-song materials may be subject to separate rights and usage conditions.

Check the applicable conditions before redistributing or reusing demo music outside this project.

---

## ☕ Help Build the Future of OSTF

**OSTF Player's development has ended. Its ideas and future development continue in OSTF Studio.**

If you found the Player useful and would like to support what comes next, please consider a voluntary contribution.

### [☕ BUY ME A COFFEE — SUPPORT OSTF STUDIO](https://buymeacoffee.com/yohsukenak)

**Thank you for helping this independent project move forward.**

---

**OSTF Player v2.0 — Legacy OSTF 3.x / 4.0 Player for Ableton Live / Max for Live**  
**Development ended · Continued in [OSTF Studio](https://github.com/yoh-nak/OSTF-Studio)**
