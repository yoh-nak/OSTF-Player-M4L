# OSTF Player for Max for Live

**Version 2.0 — OSTF 4.0 Support, GM Preview Browser, Unified Song / Arrangement Playback**

**OSTF Player** is a free interactive song player, visualizer, arrangement inspector, and lead sheet tool for **Ableton Live / Max for Live**, powered by the **Open Song Timeline Format (OSTF)**.

Load complete OSTF songs and explore their structure, chord progressions, chord voicings, melodies, lyrics, arrangement tracks, tempo, meter, key changes, MIDI performance data, and expression information in a single interface.

OSTF Player v2.0 significantly expands the Player beyond the earlier OSTF 3.x versions with improved OSTF 4.0 support, more detailed MIDI-expression visualization, GM Program Change handling, a new GM instrument browser, arrangement sound setup, improved built-in preview playback, and major playback/UI stability improvements.

> **Current version:** OSTF Player **v2.0** supports **OSTF 4.0** and retains compatibility with supported OSTF 3.x files.  
> The Player version and the OSTF file-format version are maintained independently.

---

## Main Features

- OSTF 4.0 song playback and visualization
- Compatibility with supported OSTF 3.x files
- Song structure and chord progression timeline
- Chord voicing piano roll
- Multiple melody and arrangement-track visualization
- Lyrics and pronunciation display
- MIDI note and expression inspection
- Program Change / GM instrument interpretation
- CC, Pitch Bend, and Aftertouch visualization
- Built-in lightweight preview sound engine
- GM 1–128 instrument browser
- Built-in drum-kit browser
- Arrangement track mixer and sound setup
- Song transposition
- Key diagrams
- Lead sheet / print workflow
- MIDI-oriented export workflows
- 11 built-in OSTF 4.0 demo songs

---

# OSTF File Support

OSTF Player v2.0 uses the **standard OSTF data model** for song metadata, timeline information, harmony, lyrics, tracks, presentation information, notes, and MIDI-style performance data.

Supported workflows include:

- Load standard **OSTF 4.0** song files
- Load supported OSTF 3.x files
- Read song title and metadata
- Read genres
- Read song key information
- Read timeline key changes
- Read tempo changes
- Read meter changes
- Read song sections
- Read harmonic events
- Read chord voicings
- Read melody tracks
- Read arrangement tracks
- Read lyric documents
- Read presentation information where available
- Read note-performance information
- Read Program Change information
- Read CC information
- Read Pitch Bend information
- Read Aftertouch information
- Preserve loaded OSTF data during normal Player playback and visualization

OSTF Player does not require Player-specific private metadata for information already defined by the OSTF standard.

---

# OSTF 3.x and OSTF 4.0 Compatibility

OSTF Player v2.0 is designed to open both supported **OSTF 3.x** songs and **OSTF 4.0** songs.

Older OSTF files remain useful for compatibility testing and playback, while OSTF 4.0 provides the current format for the included demo collection.

The Player attempts to use the information actually stored in the OSTF file rather than silently inventing missing values.

For example:

- A missing key is not automatically treated as C major.
- A missing genre is not automatically treated as Pop.
- Track roles are not determined only from track names.
- Fixed MIDI triggers are not treated as normal transposable musical notes.
- Standard OSTF metadata takes priority over Player-specific assumptions.

---

# OSTF 4.0 MIDI Expression Support

OSTF 4.0 expands the amount of MIDI-oriented performance information that can be stored with a song.

OSTF Player v2.0 can inspect and visualize supported information including:

- Note velocity
- Release Velocity
- Enabled / disabled notes
- Probability
- Velocity Deviation
- Pitch roles
- Program Change
- Control Change
- Pitch Bend
- Aftertouch

Expression lanes can be inspected alongside piano-roll information where applicable.

The Player is intended to preserve the distinction between the musical composition and its performance information rather than destructively converting everything into plain notes.

---

# Enabled and Disabled Notes

OSTF notes can remain part of the song data while being disabled for normal playback.

For example:

```json
"enabled": false
```

Disabled notes remain part of the OSTF document but are not treated as normally sounding notes during Player playback.

---

# Musical Notes and Fixed Triggers

OSTF can distinguish normal pitched musical notes from fixed MIDI triggers.

Typical fixed triggers include:

- Key switches
- Articulation switches
- Drum-style triggers
- Device-specific trigger notes
- Other MIDI notes whose absolute note number must remain unchanged

When transposing a song, fixed triggers remain at their original MIDI note numbers.

This prevents musical transposition from accidentally moving articulation or control notes.

---

# Song View

**Song View** provides a structural overview of the complete song.

It includes:

- Song sections
- Chord progression
- Playback cursor
- Tempo information
- Meter information
- Key information
- Chord voicings
- Main melody
- Lyrics
- MIDI-expression information
- Timeline navigation
- Adjustable time zoom
- Section navigation
- Follow Cursor playback behavior

Chord progression, voicing piano rolls, melody piano rolls, and the playback cursor use a shared song timeline so the current playback position remains synchronized across the interface.

---

# Chord Voicing Piano Roll

Chord voicings can be inspected in their own piano-roll area.

The display can show:

- Stored voicing notes
- Note velocity
- Pitch positions
- Timeline placement
- Playback cursor
- Preview sound assignment

The voicing display is intended for inspection and auditioning of OSTF harmony data.

It does not create additional performance notes simply because a chord contains descriptive voicing information.

---

# Main Melody

The Main Melody area provides detailed inspection of the primary melody.

Depending on the source OSTF data, the Player can display:

- Melody clips
- MIDI notes
- Velocity
- CC information
- Pitch Bend
- Aftertouch
- Program information
- Lyrics
- Pronunciation
- Playback position

OSTF 4.0 songs can contain richer performance data than conventional note-only MIDI representations.

---

# Arrangement View

**Arrangement View** displays the song's individual arrangement tracks.

Each supported track can provide:

- Piano-roll visualization
- Track role
- Track order
- Note information
- Velocity
- CC
- Pitch Bend
- Aftertouch
- Level
- Pan
- Solo
- Mute
- Preview sound
- Visibility controls

Arrangement tracks remain part of the OSTF song regardless of whether they are currently visible in the Player.

Display visibility and audio mute are separate controls.

---

# Track Display & Mixer

OSTF Player v2.0 includes a Track Display & Mixer area for controlling arrangement-preview playback.

Available controls include:

- Show / hide track
- Display ordering
- Preview sound
- Level
- Pan
- Solo
- Mute
- Velocity display options

These settings are Player-side preview controls.

They do not rewrite the source OSTF song merely because a different preview sound or mixer setting is selected.

---

# GM Instrument Browser

OSTF Player v2.0 introduces a **GM 1–128 instrument browser**.

Instead of exposing only the Player's internal synthesis categories, users can choose instruments using familiar General MIDI program names.

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

The browser can be used for Player preview assignment in areas such as:

- Chord voicing
- Melody
- Arrangement tracks
- Track Display & Mixer
- Arrangement Sound Setup

---

# GM Program Change Interpretation

OSTF Player can interpret GM Program Change values across the normal **0–127 MIDI program range**.

The Player presents these as the conventional **GM 1–128** instrument list.

The internal preview engine does **not** contain 128 fully sampled General MIDI instruments.

Instead, GM programs are mapped to suitable lightweight internal synthesis families for structural preview playback.

For this reason:

**GM Program interpretation:** supported  
**128 independent professional GM instruments:** not provided

The built-in engine is intended for song preview and arrangement inspection rather than replacing a dedicated General MIDI module, sampler, or virtual instrument collection.

---

# Built-in Preview Sound Engine

OSTF Player contains a lightweight built-in synthesis engine so songs can be auditioned without loading additional instrument plug-ins.

Internal preview families include sounds suited to roles such as:

- Keys
- Electric Piano
- Organ
- Bass
- Guitar
- Strings
- Lead
- Pluck
- Pad
- Brass / Reed
- Distorted Guitar
- Other general preview roles

The engine supports:

- Polyphonic playback
- Velocity-sensitive playback
- Basic instrument-specific envelopes
- Basic filtering
- Program-based preview assignment
- MIDI-style expression interpretation where supported
- Automatic instrument preview assignment

The internal sounds are intentionally lightweight.

They are designed for:

- Checking song structure
- Auditioning arrangements
- Inspecting OSTF files
- Previewing harmony and melody
- Comparing tracks

They are **not intended to replace professional sample libraries, synthesizers, orchestral libraries, or dedicated instrument plug-ins**.

---

# Drum Preview Engine

OSTF Player v2.0 includes four built-in drum preview kits:

- Electronic Kit
- Acoustic-like Kit
- Tight Kit
- 808-style Kit

Drum tracks use their MIDI drum-note layout while the selected preview kit determines the Player-side sound character.

A dedicated Drum Kit Browser is used instead of treating drum kits as normal GM melodic instruments.

---

# Arrangement Sound Setup

The **Arrangement Sound Setup** window provides centralized control over Player preview sounds.

It can be used to:

- Inspect current track sound assignments
- Assign GM instruments
- Assign drum kits
- Apply settings to visible tracks
- Apply settings across song tracks
- Automatically assign preview sounds based on instrument information
- Audition individual tracks

Sound Setup changes affect Player preview behavior and do not rewrite the OSTF source file.

---

# Lyrics

OSTF supports multiple lyric documents and vocal-related information.

OSTF Player can display:

- Synchronized lyrics
- Pronunciation information where available
- Selected lyric documents
- Primary lyric-document references
- Melody-related lyric timing

The Player avoids automatically merging unrelated lyric documents into one combined lyric stream.

This makes it possible for OSTF songs to maintain separate lyric-related documents such as:

- Main vocal lyrics
- Alternate lyrics
- Translations
- Pronunciation guides
- Other vocal parts

---

# Key Transposition

Songs can be transposed directly in the Player.

Available behavior includes:

- Transpose in semitone steps
- Update displayed chord information
- Update displayed key information
- Restore the original key
- Follow timeline key changes
- Preserve fixed-trigger MIDI note numbers
- Maintain a distinction between original and temporary playback keys

OSTF Player distinguishes between:

- Original song key
- Current timeline key
- Temporary Player transposition
- Independent print transposition
- Musical notes
- Fixed MIDI trigger notes

A missing or non-major/minor key is not silently converted to C major.

---

# Key Diagrams

OSTF Player includes key-reference diagrams such as:

- Camelot Key Wheel
- Circle of Fifths

These can be used to compare original and transposed key positions.

> **Music theory note:** Camelot notation is primarily intended for major and minor keys. Modes and non-major/minor tonal systems may only have approximate Camelot relationships.

---

# Timeline Support

OSTF Player reads timeline information including:

- Tempo changes
- Meter changes
- Key changes
- Song sections
- Harmonic events
- Arrangement events

The Player is also designed to handle situations such as:

- Pickup / anacrusis material
- Meter changes during a song
- Notes extending across structural boundaries
- Simultaneous MIDI-style events
- Material extending beyond nominal section boundaries

---

# Playback

Playback can use the Player's internal preview engine without requiring external instruments.

Playback controls include:

- Play
- Pause
- Stop
- Panic
- Mute All
- Section navigation
- Loop / range workflows where available
- Follow Cursor

The Player's timeline, piano rolls, and playback cursor are synchronized to the same song-time reference.

---

# Lead Sheet & Printing

OSTF Player includes a printable lead-sheet workflow.

Available options include:

- Chord symbols
- Lyrics
- Section labels
- Bar numbers
- Song credits
- Portrait / landscape layouts
- Font and spacing adjustments
- Page scaling
- Print preview
- Independent print key selection

Lead-sheet metadata is taken from standard OSTF song data where available.

The print key can be changed independently without changing the Player's current playback transposition.

---

# MIDI-Oriented Workflows

OSTF Player can work with melody and arrangement information in MIDI-oriented workflows.

Depending on the destination, some OSTF information can be represented directly while other performance semantics may not have an exact Standard MIDI File equivalent.

General behavior includes:

- Musical notes follow selected transposition
- Fixed-trigger notes retain their MIDI note number
- Disabled notes are not treated as normally sounding notes
- Release Velocity can be preserved where supported
- OSTF performance information is not intentionally converted into destructive random MIDI data merely for export

OSTF can contain richer information than a conventional Standard MIDI File.

---

# Included Demo Songs

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

The downloadable archive contains the demo songs as individual standard `.ostf` files.

---

# Demo Version Management

Demo filenames identify the **OSTF file-format version**, independently from the Player version.

For example:

```text
OSTF4.0_Demo_01_Pop_City_Lights_Again.ostf
```

This makes it possible to maintain older demo collections for compatibility testing while newer demos follow newer OSTF specifications.

**OSTF Player v2.0** and **OSTF 4.0** are separate version numbers.

---

# Requirements

- Ableton Live with **Max for Live**
- Compatible Max / Max for Live environment
- Windows or macOS
- External `.ostf` files for songs other than the included demos

The Player is distributed as a single `.amxd` device.

No external instrument plug-in is required for basic preview playback.

> **Compatibility note:** Every possible Ableton Live, Max, operating-system, hardware, and OSTF-file combination has not been exhaustively certified. Performance may vary between host environments.

---

# Installation

1. Download `OSTF_Player_v2.0.amxd`.
2. Open Ableton Live.
3. Create or select a MIDI track.
4. Drag `OSTF_Player_v2.0.amxd` onto the MIDI track.
5. Click **Open** in the compact Max for Live device view.
6. Select a built-in demo or load an external `.ostf` file.

If replacing an older OSTF Player version, keeping a backup of the previous device and important Live Sets is recommended.

---

# Quick Start

1. **Open the Player**  
   Click **Open** in the Max for Live device view.

2. **Choose a song**  
   Select one of the 11 built-in demos or load an external `.ostf` file.

3. **Play**  
   Use the Player transport to audition the song.

4. **Explore Song View**  
   Inspect sections, chords, chord voicings, melody, lyrics, and timeline information.

5. **Explore Arrangement View**  
   Inspect the individual arrangement tracks and MIDI-expression information.

6. **Choose preview sounds**  
   Use the GM Instrument Browser or Drum Kit Browser.

7. **Adjust the arrangement preview**  
   Use Track Display & Mixer or Arrangement Sound Setup.

8. **Transpose**  
   Change the song key in semitone steps.

9. **Inspect keys**  
   Open Key Diagrams for Camelot and Circle of Fifths information.

10. **Print**  
    Open the lead-sheet interface and choose the desired print layout and key.

---

# About OSTF

**OSTF (Open Song Timeline Format)** is a structured song-data format for describing musical compositions and arrangements along a timeline.

OSTF can describe information such as:

- Song structure
- Sections
- Chord progressions
- Chord voicings
- Keys
- Key changes
- Tempo
- Tempo changes
- Meter
- Meter changes
- Melodies
- Multiple melody tracks
- Lyrics
- Multiple lyric documents
- Pronunciation
- Instrument tracks
- Arrangement data
- MIDI notes
- Velocity
- Release Velocity
- Note Probability
- Velocity Deviation
- Program Change
- Control Change
- Pitch Bend
- Aftertouch
- Fixed MIDI triggers
- Genres
- Languages
- Moods
- Credits
- Presentation information
- Other structured timeline information

OSTF is intended to make structured musical information easier to exchange, inspect, edit, visualize, arrange, perform, and reuse across compatible music-production tools.

---

# Related Projects

- [Open Song Timeline Format 4.0](https://github.com/yoh-nak/Open-Song-Timeline-Format-4.0)
- [OSTF Player for Max for Live](https://github.com/yoh-nak/OSTF-Player-M4L)

---

# Design Philosophy

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

---

# Limitations

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

---

# Version History

## v2.0 — OSTF 4.0 Player & Major UI / Playback Update

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

## v1.3.2 — OSTF 3.5 Support & Playback Cursor Fix

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

## v1.2.0 — OSTF 3.4 Standard Support

- Add OSTF 3.4 support.
- Move supported metadata handling to standard OSTF fields.
- Improve key, genre, credits, voicing, lyrics, and track handling.
- Improve multiple lyric-document handling.
- Improve original-key and transposition behavior.

## v1.1.3 — OSTF 3.3 Compatibility & Key Display Fixes

- Add OSTF 3.3 compatibility.
- Add genre metadata support.
- Improve metadata header layout.
- Improve Camelot and Circle of Fifths displays.
- Improve key-diagram modal behavior.

## v1.0 — Initial Public Release

- OSTF song loading
- Song and arrangement visualization
- Chord progression display
- Melody visualization
- Lyrics and pronunciation
- Built-in preview instruments
- Built-in drum kits
- Key transposition
- Key diagrams
- Lead-sheet printing
- MIDI-oriented workflows
- Demonstration songs
- Compact Max for Live launcher

---

# Support Development — Buy Me a Coffee

OSTF Player is independently developed and distributed **free of charge**.

If you enjoy the device and would like to support continued OSTF development, improvements, documentation, and additional free Max for Live tools, voluntary support is available here:

**[☕ Buy Me a Coffee — yohsukenak](https://buymeacoffee.com/yohsukenak)**

Donations are entirely optional.

No payment is required to use OSTF Player's core functionality.

---

# Credits

**Software development:** [yoh-nak](https://github.com/yoh-nak)  
**Project:** Open Song Timeline Format (OSTF)  
**Repository:** https://github.com/yoh-nak/OSTF-Player-M4L

The included demo compositions are provided as example song material.

Software-development credit does not necessarily imply personal authorship of every demo composition, lyric, or arrangement.

---

# License and Copyright

A software license has not been specified in this repository.

Unless a separate license is provided, public access to the repository does not by itself grant permission to redistribute, modify, sublicense, or commercially reuse the software.

Demo-song materials may be subject to separate rights and usage conditions.

Check the applicable conditions before redistributing or reusing demo music outside this project.

---

**OSTF Player v2.0 — OSTF 3.x / 4.0 Player for Ableton Live / Max for Live**
