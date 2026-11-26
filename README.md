# Tamanina packs

Downloadable audio and Mushaf pages for the Tamanina app. The app verifies every
file against the SHA-256 listed in its catalog before using it. Tags are
immutable: publish changes under a new tag (`v2`, ...).

- `adhan/` – adhan recordings (mono MP3 for Android, short CAF clips for iOS notifications)
- `mushaf/` – Mushaf pages, packed 100 per file (see `tool/make_mushaf_pack.py` in the app repo)
- `packs.json` – the catalog entries for these files

See [LICENSES.md](LICENSES.md) for attribution.
