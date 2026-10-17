# 🧪 Test Plan — GW2 MIDI-to-Notation

## 1. Objective

Validate that the application reliably imports supported musical files, converts notes and timing into Guild Wars 2 numeric notation, provides usable per-track playback, and exports output without data corruption.

## 2. Application overview

The application is a browser-based tool intended to:
- Import MIDI files and convert their tracks into GW2 numeric notation.
- Provide notation features for rests, chords, octave ranges, and note durations.
- Optimize key/range choices and organize output using a beat grid.
- Play tracks using a bundled SoundFont, with per-track instrument selection and a virtual piano.
- Copy notation or download it as a text file.

## 3. Scope

### In scope
- File picker and file-type validation.
- MIDI parsing and multi-track conversion.
- Part/track separation and naming.
- Pitch, octave, chord, rest, and duration conversion.
- Beat-grid and key/range optimization behavior.
- SoundFont instrument selection and playback.
- Track playback, play-all, playhead/highlighting, and virtual piano.
- Copy/download actions.
- Layout, scrolling, and basic keyboard controls.
- Regression checks across MIDI import, conversion, playback, and export workflows.

### Out of scope for this pass
- Compatibility with every possible MIDI file and every unusual MIDI event/metadata combination.
- Optical music recognition (PDF/image sheet music).
- Formal accessibility certification, performance benchmarking, and security penetration testing.
- Verifying copyright or redistribution rights for bundled SoundFont assets.

## 4. Test approach

- **Functional testing:** Verify each feature against expected behavior.
- **Negative testing:** Try unsupported, malformed, empty, and corrupted files.
- **Regression testing:** Repeat key MIDI, playback, export, and UI tests after changes.
- **Cross-browser smoke testing:** At minimum, test a current Chromium-based browser; add Firefox/Edge where available.
- **Exploratory testing:** Try real-world scores with multiple parts, rests, chords, accidentals, ties, tuplets, and unusual timing.
- **Evidence capture:** Record screenshots/video, test data file names, browser/version, and observed result.

## 5. Test environment

Record actual environment before execution:

| Field | Value to record |
|---|---|
| Build / commit | Git commit hash or ZIP version |
| OS | e.g., Windows 11 |
| Browser | e.g., Chrome + version |
| Viewport | Desktop dimensions and mobile viewport if tested |
| Test date | Actual date |
| Tester | Actual tester |
| Source files | Names and source of MIDI/score fixtures |

## 6. Severity definitions

| Severity | Definition |
|---|---|
| **S1 — Critical** | App cannot load or core conversion is unusable; major data loss or widespread failure. |
| **S2 — High** | Major feature broken, such as importing supported files, track conversion, or playback for most users. |
| **S3 — Medium** | Feature works partially or produces incorrect output in a limited workflow; workaround may exist. |
| **S4 — Low** | Cosmetic, minor usability, or low-impact issue. |

## 7. Priority definitions

| Priority | Definition |
|---|---|
| **P1 — Urgent** | Fix before release; blocks core usage or causes broad failure. |
| **P2 — High** | Fix in the next iteration; important workflow is affected. |
| **P3 — Normal** | Fix when scheduled; limited impact or workaround exists. |
| **P4 — Low** | Cosmetic or enhancement; can be deferred. |

Severity describes impact; priority describes urgency. They do not have to match.

## 8. Entry criteria

- A build is available locally or on GitHub Pages.
- Test files are available: valid single-track MIDI, multi-track MIDI, and invalid/empty MIDI samples.
- Browser console can be opened.
- Test tracker is ready.

## 9. Exit criteria

- All P1/P2 test cases are executed and results recorded.
- No open S1/S2 defects remain, or remaining risks are explicitly accepted.
- Core MIDI conversion, playback, and export regression checks have been run for the build under test.
- Import limitations are documented.

## 10. Risks and focus areas

- MIDI files may use unusual timing, dense chords, overlapping notes, or track metadata that is not handled as expected.
- Instrument names and MIDI program numbers may not map cleanly to available SoundFont presets.
- Browser audio may require a user gesture before playback.
- Timing conversion and beat-grid alignment may be sensitive to tempo changes or unusual rhythmic patterns.
- A syntactically valid build is not proof that all user workflows work correctly.
