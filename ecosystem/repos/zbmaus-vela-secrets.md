# zbmaus-vela-secrets

**Visibilitas:** Privat · **Branch:** `main` · **Push terakhir:** 24 Nov 2026 · **Ukuran:** ~150 KB

## Peran
Backup kredensial, env, dan snapshot state VPS zbmaus. **Tidak pernah dicerminkan ke `zbmaus-vela-eco`.**

## Isi Pokok
- `bots/`, `bots.json`, `config.json`
- `credentials/`, `env/`, `vault/`
- `omb-state-*` — snapshot state OMB
- `routines/`
- Catatan sinkronisasi: `SYNC-2026-11-19/21/22.md`, `sync-notes/sync-2026-11-24.md`

## Aturan
- Jangan pernah memindahkan isi `credentials/`, `env/`, atau `vault/` ke repo publik/eco.
- Sync terakhir 24 Nov 2026 — tertinggal 2 hari per 26 Nov; perlu sync ulang.
