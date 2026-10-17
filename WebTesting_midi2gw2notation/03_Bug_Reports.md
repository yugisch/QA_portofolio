# 🐞 Historical Bug Reports & Defect Log

## How to interpret these records

These reports summarize issues described during iterative development conversations. They are **historical reports**, not proof that the latest build has passed regression testing. Where the conversation indicates a fix was made, the status is recorded as **Reported fixed — retest required** unless a current-build test was documented.

## BUG-001 — Copy/download output contained `undefined`
- **Area:** Output / export
- **Severity:** S2 — High
- **Priority:** P1 — Urgent
- **Type:** Functional / data integrity
- **Observed behavior:** Copy or TXT export reportedly included `undefined` text beneath track headings such as Piano, Strings, Brass, Percussion, or Melody.
- **Expected behavior:** Exported/copied content should contain only valid notation and intended track labels.
- **Impact:** User receives corrupted or confusing output; undermines core export workflow.
- **Fix history:** A “copy/download fixed” project build was produced during iteration.
- **Current status:** Reported fixed — retest required.
- **Regression tests:** TC-022, TC-023.
- **Evidence needed:** Before/after TXT output and clipboard paste.

## BUG-002 — Track playback highlighted the wrong tracks
- **Area:** Playback / playhead visualization
- **Severity:** S2 — High
- **Priority:** P2 — High
- **Type:** Functional / UI state
- **Observed behavior:** Playing one track reportedly highlighted notes/beats in other tracks as well.
- **Expected behavior:** Only the active track's playhead/highlighting should update, unless Play All is active.
- **Impact:** Playback visualization becomes misleading when checking individual parts.
- **Fix history:** Track-player/play-all/highlight iterations were made.
- **Current status:** Reported addressed during iteration — retest required.
- **Regression tests:** TC-016, TC-017.
- **Evidence needed:** Screen recording of individual-track playback in a multi-track file.

## BUG-003 — Instrument selection did not reliably change timbre
- **Area:** SoundFont / instrument selector
- **Severity:** S2 — High
- **Priority:** P1 — Urgent
- **Type:** Functional / audio
- **Observed behavior:** Different selected instruments sounded the same or did not match the selected preset. Earlier mappings also produced mismatched sounds (for example, a Piano track sounding like a flute).
- **Expected behavior:** Changing the instrument should select the intended SoundFont preset and playback should use that preset.
- **Impact:** Instrument preview/playback is unreliable and the score may sound incorrect.
- **Fix history:** Several SoundFont builds were created. User later said a friend fixed the current GitHub repository, but the exact changes were not known from the conversation.
- **Current status:** User-reported fixed in their repo — independent verification required.
- **Regression tests:** TC-015, TC-018.
- **Evidence needed:** Same notes played using at least two clearly different presets, with selector values and recording.

## BUG-004 — MIDI track labels were generic or inconsistent
- **Area:** Track metadata / UI
- **Severity:** S3 — Medium
- **Priority:** P2 — High
- **Type:** Usability / display
- **Observed behavior:** Track labels showed generic channel names such as “Channel 1/2” rather than useful instrument names; user also reported missing color accent indicators.
- **Expected behavior:** Track headings should show an appropriate instrument/track name and the intended visual accent.
- **Impact:** Harder to identify parts in multi-track arrangements.
- **Fix history:** Builds for channel-name UI and accent indicator fixes were produced.
- **Current status:** Reported fixed — retest required.
- **Regression tests:** TC-003, TC-009, TC-016, TC-024.
- **Evidence needed:** Screenshot of a multi-track file with distinct names and accents.

## BUG-005 — Chosen beat-grid settings did not visibly affect most output
- **Area:** Conversion / beat grid
- **Severity:** S3 — Medium
- **Priority:** P2 — High
- **Type:** Functional / conversion formatting
- **Observed behavior:** User reported beat-grid controls appeared to affect mainly the eighth-beat behavior while other settings seemed to have little effect.
- **Expected behavior:** Changing grid settings should produce the documented change in grouping/line formatting and preserve note order/timing.
- **Impact:** User cannot predict or control output formatting.
- **Fix history:** An adaptive/local beat-grid build was produced.
- **Current status:** Reported addressed during iteration — retest required.
- **Regression tests:** TC-011, TC-013.
- **Evidence needed:** Same MIDI converted with two grid settings and compared.

## BUG-006 — Copy/download content or track output had incorrect extra labels
- **Area:** Output generation
- **Severity:** S3 — Medium
- **Priority:** P2 — High
- **Type:** Formatting
- **Observed behavior:** During iterations, duplicate labels and a leading output gap were reported and addressed; later export-specific `undefined` issue is separately tracked in BUG-001.
- **Expected behavior:** Track output starts cleanly and contains one intended heading with no spurious prefix/gap.
- **Impact:** Output is harder to read and may confuse copy/paste workflows.
- **Fix history:** A build described as fixing duplicate labels and leading output gap was produced.
- **Current status:** Reported fixed — retest required.
- **Regression tests:** TC-022, TC-023, TC-024.
- **Evidence needed:** Screenshot and exported TXT from a known sample.

## BUG-007 — Keyboard numpad input was not handled as expected
- **Area:** Virtual piano / keyboard input
- **Severity:** S3 — Medium
- **Priority:** P3 — Normal
- **Type:** Input handling
- **Observed behavior:** Numpad support was requested after an initial numpad issue.
- **Expected behavior:** Documented numeric-key and numpad controls trigger the intended notes/actions consistently.
- **Impact:** Keyboard-oriented users cannot rely on the expected controls.
- **Fix history:** Numpad support was included in subsequent requirements/iterations.
- **Current status:** Implemented by iteration, but current behavior not independently verified.
- **Regression tests:** TC-019.
- **Evidence needed:** Test with Num Lock on/off and record browser/OS behavior.

## BUG-008 — Copy/download track title could be followed by missing data
- **Area:** Export / serialization
- **Severity:** S2 — High
- **Priority:** P1 — Urgent
- **Type:** Data integrity
- **Observed behavior:** In the reported `undefined` export defect, track title blocks appeared to be serialized even when the associated notation value was missing or referenced incorrectly.
- **Expected behavior:** Export code should omit invalid values or report an explicit error rather than writing JavaScript's `undefined`.
- **Impact:** Same core export symptom as BUG-001.
- **Fix history:** Likely related to the copy/download fix; retained separately here as a possible root-cause investigation item.
- **Current status:** Candidate duplicate/root-cause note — merge with BUG-001 if investigation confirms same defect.
- **Regression tests:** TC-022, TC-023.
