# Cantor traditions for Trope on the Go

Versioned runtime packs for the app's tradition picker. The app pins each tradition to an immutable Git commit through jsDelivr.

`Torah-Binder/` contains Binder's Torah notes, recording manifest, 1,102 normalized AAC recordings, and the normalization report. Audio paths mirror the app's Default assets.

Audio normalization uses the original Trope on the Go two-pass FFmpeg loudnorm method: −27 LUFS integrated, −2 dBTP peak, LRA 11, AAC 160 kbps, fast-start metadata. Sample rate is not forced, matching the original process. The original scripts are in app commits `3a1aae8a0` and `83eec4cdb`.

Source WAVs and portal save files are preserved in the original app-workspace archive and are not included here. The portal-only custom Shalshelet alternate is excluded.

Import future packs using the app repository's `tools/import-tradition`. Validate required audio slots against the live app before publishing a release, then add its commit-pinned root to `Assets/Traditions/traditions.json`.

## Binder correction release — October 15, 2026

Merged `Torah-Binder-changes-2026-10-15_2014.zip` into the complete pack: 17 Sof Aliyah Mercha-before-Siluk words, the three one-syllable Mercha-before-Tipcha words (lo, ki, ish), and two Siluk words (bo, bah). All 22 recordings retain their existing app paths and word metadata. The other 1,080 recordings and the note pack are unchanged.

The replacements were normalized directly from source WAVs with the same two-pass settings above and decoded successfully with FFmpeg. All 22 output sample rates are 96 kHz; no sample-rate override was used. The complete release contains 79,274,761 audio bytes (211,527 more than the previous release). The manifest contains updated sizes, SHA-256 checksums, and recording-update provenance. Source WAVs, portal data, and blessing exports are excluded from runtime assets.

## Ashkenazi - Rosowsky/Fine — October 16, 2026

`Torah-Rosowsky_Fine/` is a complete independent Torah pack prepared from `Torah-Rosowsky_Fine.zip`. It contains 1,104 runtime recordings (76,974,797 audio bytes), with no runtime dependency on Binder. Source WAVs, blessings, portal saves, and portal-only custom content are excluded.

New Munach word takes are confined to Munach before Etnachta. Mike approved carrying Binder recordings into Munach before Revii, Pazeir, Telisha Ketanah, Telisha Gedolah, and Zarka without rerecording. All existing non-Etnachta Munach word paths preserve the current Binder audio (95 file slots total, including shared Telisha/Pazeir paths and existing Segol/Zakef slots); the manifest records per-slot import provenance. No new Etnachta takes are copied into other contexts.

649 unchanged/approved recordings were copied from Binder release `c078ed774164a3ab8a13cd69e951b76ba0306f53` without re-encoding. 454 distinct new WAV takes were normalized directly with the established two-pass FFmpeg settings; one duplicate output was reused. Sample rates were not forced: the complete pack has 618 outputs at 96 kHz and 486 at 48 kHz.

The valid `tipcha-siluk` and `munach-mercha-pashta` recordings in portal extras were assigned explicit runtime paths under `Assets/Audio/Tradition Extras/`; their note entries include `audioPath`. The unused `mercha-etnachta` extra has no matching note entry in this export and is excluded, along with the custom Shalshelet alternate and unregistered phrase extra. This release preserves the existing warnings as source provenance; the app now supports the exported Siluk-clause Tipcha key.
