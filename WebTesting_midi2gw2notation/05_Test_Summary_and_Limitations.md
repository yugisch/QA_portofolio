# 📊 QA Test Summary & Limitations

## Project

**Application:** GW2 MIDI-to-Notation  
**Test documentation date:** 12 October 2026  
**Build under test:** Record the exact Git commit or ZIP before executing cases.

## Summary of work documented

> This is a QA documentation for my browser-based music-notation application (https://yugisch.github.io/midi-to-gw2notation/), including a test plan, functional test cases, regression checklist, traceability matrix, and severity/priority-based historical defect log. Covered file import, notation conversion, multi-track behavior, SoundFont playback, keyboard input, UI, and export workflows.

The project has evolved through iterative development of:
- MIDI file conversion into GW2 numeric notation.
- Multi-track/track-label presentation and notation formatting.
- Beat-grid and key/range optimization.
- Virtual piano, keyboard/numpad input, and track playback controls.
- SoundFont playback and instrument selection.
- Play All and per-track playhead/highlighting.
- Copy-to-clipboard and TXT export.
- Scroll/layout refinements.

## Current test execution status

| Category | Status |
|---|---|
| Historical issues documented | Complete as documentation |
| Test scenarios/cases authored | Complete as documentation |
| Current-build manual execution | Not yet recorded |
| Cross-browser validation | Not yet recorded |

## Recommended next test session

1. Record the exact app build/commit and browser.
2. Start with TC-001, TC-003, TC-015, TC-022, and TC-023 as the smoke suite.
3. Then run the remaining P1/P2 conversion, playback, and export cases; capture evidence for any failures.
4. Capture evidence and actual results for every failure.
5. Retest any fixed defect and record the result before changing its status to Verified Fixed.