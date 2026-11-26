# Tamanina packs

Downloadable audio and Mushaf pages for the Tamanina app. The app verifies every
file against the SHA-256 listed in its catalog before using it. Tags are
immutable: publish changes under a new tag (`v2`, ...).

- `adhan/` – adhan recordings (mono MP3 for Android, short CAF clips for iOS notifications)
- `mushaf/` – Mushaf pages, packed 100 per file (see `tool/make_mushaf_pack.py` in the app repo)
- `packs.json` – the catalog entries for these files

See [LICENSES.md](LICENSES.md) for attribution.

## Adding a voice (no app update needed)

```
python3 tool/make_adhan_pack.py <id> recording.mp3 --out /tmp/pack \
  --url-prefix https://cdn.jsdelivr.net/gh/AbdalluhEssam/tamanina-packs@vN/adhan/ \
  --name-ar "…" --name-en "…" --credit "Who, license" --no-phrases \
  --packs packs.json
cp /tmp/pack/<id>*.mp3 /tmp/pack/<id>*.caf adhan/
git add -A && git commit -m "Add <id>" && git tag vN && git push origin main vN
```

Installed apps read `packs.json` from `main` and show the new voice within minutes. Only add recordings
you have the right to redistribute.
