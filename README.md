# Cantor traditions for Trope on the Go

Versioned runtime packs for the app's tradition picker. The app pins each tradition to an immutable Git commit through jsDelivr.

`Torah-Binder/` contains Binder's Torah notes, recording manifest, 1,102 normalized AAC recordings, and the normalization report. Audio paths mirror the app's Default assets.

Audio normalization uses the original Trope on the Go two-pass FFmpeg loudnorm method: −27 LUFS integrated, −2 dBTP peak, LRA 11, AAC 160 kbps, fast-start metadata. Sample rate is not forced, matching the original process. The original scripts are in app commits `3a1aae8a0` and `83eec4cdb`.

Source WAVs and portal save files are preserved in the original app-workspace archive and are not included here. The portal-only custom Shalshelet alternate is excluded.

Import future packs using the app repository's `tools/import-tradition`. Validate required audio slots against the live app before publishing a release, then add its commit-pinned root to `Assets/Traditions/traditions.json`.

## Binder correction release — October 15, 2026

Merged `Torah-Binder-changes-2026-10-15_2014.zip` into the complete pack: 17 Sof Aliyah Mercha-before-Siluk words, the three one-syllable Mercha-before-Tipcha words (lo, ki, ish), and two Siluk words (bo, bah). All 22 recordings retain their existing app paths and word metadata. The other 1,080 recordings and the note pack are unchanged.

The replacements were normalized directly from source WAVs with the same two-pass settings above and decoded successfully with FFmpeg. All 22 output sample rates are 96 kHz; no sample-rate override was used. The complete release contains 79,274,761 audio bytes (211,527 more than the previous release). The manifest contains updated sizes, SHA-256 checksums, and recording-update provenance. Source WAVs, portal data, and blessing exports are excluded from runtime assets.
