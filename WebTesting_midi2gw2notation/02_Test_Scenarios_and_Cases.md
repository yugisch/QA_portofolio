# 🧾 Test Scenarios & Test Cases

**Default execution status for all cases: Not Run.** Update only after testing the target build.

## A. Import and file validation

### TS-01 — MIDI import and conversion
**Goal:** Confirm a valid MIDI file can be imported and converted.

| ID | Steps | Expected result | Priority |
|---|---|---|---|
| TC-001 | Open app; import a small valid `.mid` with a recognizable melody. | File loads; notation is generated; no uncaught error appears. | P1 |
| TC-002 | Import a `.midi` extension file containing valid MIDI data. | File is accepted and converted. | P2 |
| TC-003 | Import a multi-track MIDI file. | Distinct source tracks appear as separate output tracks where supported. | P1 |
| TC-004 | Import an empty or invalid MIDI file. | App shows a useful error or safely rejects it; page remains usable. | P1 |
| TC-005 | Import a non-music file renamed to `.mid`. | Invalid content is rejected gracefully; no silent corrupted output. | P2 |

## B. Conversion correctness

| ID | Steps | Expected result | Priority |
|---|---|---|---|
| TC-006 | Convert a score containing notes across the supported octave range. | Octave markers and pitch mapping follow the app's notation rules. | P1 |
| TC-007 | Convert a score containing low/high notes outside the intended playable range. | Range/key optimization behaves as designed, or out-of-range behavior is clearly indicated. | P1 |
| TC-008 | Convert a melody with rests of different lengths. | Rest symbols/durations match the app's notation specification. | P1 |
| TC-009 | Convert a score with simultaneous notes/chords. | Simultaneous notes are represented using the chord format expected by the app. | P1 |
| TC-010 | Convert dotted notes and different durations. | Duration markers are applied consistently. | P1 |
| TC-011 | Change beat-grid settings and reconvert. | Output line/grouping changes as expected without changing the underlying musical sequence. | P2 |
| TC-012 | Enable key optimization for a score with accidentals. | Output favors the intended key/range and minimizes unnecessary accidentals without changing melody. | P1 |
| TC-013 | Convert the same file twice with the same settings. | Output is deterministic and identical, unless the app intentionally includes variable metadata. | P2 |

## C. Playback and SoundFont

| ID | Steps | Expected result | Priority |
|---|---|---|---|
| TC-014 | Play one generated track. | Correct track plays and play/pause/stop controls respond. | P1 |
| TC-015 | Select two different SoundFont instruments for a track and compare playback. | Selected presets produce their corresponding timbres; selection does not silently reset. | P1 |
| TC-016 | Play one track while another track exists. | Only the selected track plays and its own playhead/highlight updates. | P1 |
| TC-017 | Use Play All on a multi-track output. | All intended tracks start together and stop coherently. | P2 |
| TC-018 | Use the virtual piano with mouse input. | Pressing keys produces notes in the selected octave/instrument. | P2 |
| TC-019 | Use documented keyboard and numpad shortcuts. | Correct notes/octave actions occur without triggering unrelated controls. | P2 |
| TC-020 | Release a key/note during playback. | Sound release/sustain behaves consistently with the implemented audio envelope. | P3 |
| TC-021 | Test playback before interacting with the page, then after a user gesture. | Browser audio restrictions are handled clearly; no unexplained failure. | P2 |

## D. Output and UI

| ID | Steps | Expected result | Priority |
|---|---|---|---|
| TC-022 | Copy generated notation. | Clipboard contains the intended notation and no `undefined` or unrelated text. | P1 |
| TC-023 | Download notation as TXT. | File downloads with correct content and sensible filename; no `undefined` artifacts. | P1 |
| TC-024 | Inspect track headings on a multi-track file. | Names are meaningful and note counts/labels do not duplicate or disappear unexpectedly. | P2 |
| TC-025 | Scroll long output. | Output area scrolls and lower controls/reference content remain accessible. | P2 |
| TC-026 | Inspect desktop and narrow/mobile viewport. | Controls remain usable; no critical overlap or clipping. | P2 |
| TC-027 | Expand/read output and notation reference. | Output defaults and reference layout behave as specified. | P3 |
| TC-028 | Load a new file after converting another file. | Old tracks/output are replaced or reset cleanly; no stale playback remains. | P1 |
| TC-029 | Refresh the app and load a file again. | App initializes without relying on stale state. | P2 |

## Execution record template

For each test, record:
- **Actual result:** What happened, not what was expected.
- **Status:** Pass / Fail / Blocked / Not Run.
- **Evidence:** Screenshot/video, console error, input file.
- **Defect ID:** If failed.
- **Environment:** Browser/version, OS, viewport, build/commit.
