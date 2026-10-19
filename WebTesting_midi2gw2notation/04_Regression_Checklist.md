# 🔁 Regression Checklist

Run this checklist whenever import, notation generation, playback, or export code changes.

## Core MIDI workflow
- [x] App loads without a fatal console error.
- [x] Import a valid single-track MIDI.
- [x] Import a valid multi-track MIDI.
- [x] Each track produces non-empty output where expected.
- [x] Track names are useful and do not duplicate unexpectedly.
- [x] Octave markers, rests, chords, and durations look correct for the fixture.
- [x] Key/range optimizer does not alter the melody unexpectedly.
- [x] Beat-grid settings have a visible, explainable effect.

## Playback and SoundFont
- [ ] Play one track; only that track's playhead/highlight updates.
- [ ] Stop/pause controls work.
- [ ] Play All starts intended tracks together.
- [ ] Switching between two different SoundFont presets changes the sound.
- [ ] Virtual piano responds to mouse input.
- [ ] Keyboard and numpad controls match the documented mapping.
- [ ] No audio continues unexpectedly after stopping/changing files.

## Export
- [ ] Copy output and paste into a plain-text editor.
- [ ] Download TXT and inspect the entire file.
- [ ] No `undefined`, `[object Object]`, duplicate headings, or unexplained leading gaps.
- [ ] Track order and notation are preserved.

## UI
- [ ] Output panel scrolls for long tracks.
- [ ] Track controls and notation reference remain reachable.
- [ ] Desktop layout is usable.
- [ ] Narrow viewport is usable.
- [ ] Reloading and importing a second file does not leave stale tracks/playback.
