# Cantor traditions for Trope on the Go

Versioned runtime packs for the app's tradition picker. The app pins each tradition to an immutable Git commit through jsDelivr.

`Torah-Binder/` contains Binder's Torah notes, recording manifest, 1,102 normalized AAC recordings, and the normalization report. Audio paths mirror the app's Default assets.

Audio normalization uses the original Trope on the Go two-pass FFmpeg loudnorm method: −27 LUFS integrated, −2 dBTP peak, LRA 11, AAC 160 kbps, fast-start metadata. Sample rate is not forced, matching the original process. The original scripts are in app commits `3a1aae8a0` and `83eec4cdb`.

Source WAVs and portal save files are preserved in the original app-workspace archive and are not included here. The portal-only custom Shalshelet alternate is excluded.

Import future packs using the app repository's `tools/import-tradition`. Validate required audio slots against the live app before publishing a release, then add its commit-pinned root to `Assets/Traditions/traditions.json`.
