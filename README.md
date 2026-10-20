# Cantor traditions for Trope on the Go

Versioned runtime packs for the app's tradition picker. The app pins each tradition to an immutable Git commit through jsDelivr.

`Torah-Binder/` contains Binder's Torah notes, recording manifest, 1,102 normalized AAC recordings, and the normalization report. Audio paths mirror the app's Default assets.

Audio normalization uses the original Trope on the Go two-pass FFmpeg loudnorm method: −27 LUFS integrated, −2 dBTP peak, LRA 11, AAC 160 kbps, fast-start metadata. Sample rate is not forced, matching the original process. The original scripts are in app commits `3a1aae8a0` and `83eec4cdb`.

Source WAVs and portal save files are preserved in the original app-workspace archive and are not included here. The portal-only custom Shalshelet alternate is excluded.

Import future packs using the app repository's `tools/import-tradition`. Validate required audio slots against the live app before publishing a release, then add its commit-pinned root to `Assets/Traditions/traditions.json`.

## Binder correction release — October 15, 2026

Merged `Torah-Binder-changes-2026-10-15_2014.zip` into the complete pack: 17 Sof Aliyah Mercha-before-Siluk words, the three one-syllable Mercha-before-Tipcha words (lo, ki, ish), and two Siluk words (bo, bah). All 22 recordings retain their existing app paths and word metadata. The other 1,080 recordings and the note pack are unchanged.

The replacements were normalized directly from source WAVs with the same two-pass settings above and decoded successfully with FFmpeg. All 22 output sample rates are 96 kHz; no sample-rate override was used. The complete release contains 79,274,761 audio bytes (211,527 more than the previous release). The manifest contains updated sizes, SHA-256 checksums, and recording-update provenance. Source WAVs, portal data, and blessing exports are excluded from runtime assets.

## Ashkenazi - Rosowsky/Fine — recordings withdrawn October 16, 2026

Mike reports that the recordings were made in the wrong key and requests a complete replacement set. All 1,104 Rosowsky/Fine runtime recordings, including inherited copies, have been removed from the current release. Its 59 note definitions remain unchanged in pitch and duration; recording-path metadata was removed. The manifest has zero recordings and `recordingsAvailable: false`. The old normalization report has been removed from this current release.

The app ships this notes-only snapshot under `Assets/Traditions/Torah-Rosowsky_Fine/` so synthesized practice can remain available offline. It blocks voice playback and removes this tradition's old download caches when the updated app loads. Source ZIPs are retained in the app workspace for reference. Earlier immutable Git commits still exist as history; the app no longer registers or loads that audio release. A complete new recording set must be supplied and validated before voice playback is enabled again.


## Fresh Rosowsky/Fine replacement — October 20, 2026

The October 16 notes-only withdrawal above is historical. `Torah-Rosowsky_Fine/` is replaced entirely from Mike’s October 20 export, SHA-256 `accc9478168921702045884b9bd98ed05c75c9528a5c976193073c1230fce5ef`. It contains 61 source base-note definitions and 1,077 normalized recordings: 1,076 supplied runtime entries plus the explicitly mapped Munach-before-Mercha-before-Pashta extra. The Siluk-clause Tipcha points to its byte-identical new ordinary Tipcha take. No old Rosowsky/Fine audio, old note definitions or historical Binder substitutions are reused.

Runtime metadata contains routing IDs/paths, hashes and byte counts, without per-word syllable/stress definitions. The app remains authoritative for word-specific note adaptation. Twenty portal extras duplicate active runtime takes; the distinct custom Shalshelet, unmapped Zarka phrase and Mercha-before-Etnachta extras remain preserved in the source archive for separate mapping review. Required runtime slots and all output hashes have been validated. Musical listening and physical-device acceptance remain separate checks.
