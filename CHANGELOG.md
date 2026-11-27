# CHANGELOG — zbmaus-vela-eco

## 2026-11-28 — Sinkronisasi & Backup Harian (v1.4.0 / v2.3.0)

Sinkronisasi harian ekosistem zbmaus. Urutan: inventarisasi live -> audit -> tulis eco -> backup secrets -> verifikasi.

### Bot
- Perbarui model: ZB -> `opencode/longcat-2.5-free`, AsnAdmin & ZbmausHumanoid-Vercel -> `agnes/agnes-2.5-flash`, Kaggle-Qwen -> `qwen3.8-flash-next-gyro-gyro-s`, Superpowers Engineer -> `opencode/seaglass-alpha-free`.
- Tambah Superpowers Engineer sebagai bot ke-8.
- `bots.json` -> v1.4.0.

### Routine / Trigger
- Nonaktifkan `5af330ca` (status disabled).
- Tambah `b2e9a760` (dokumenter Kamis 10:00 WIB) dan `e71db9c1` (riset Senin 10:00 WIB).
- Koreksi stats: 15 -> 17 total, 13 -> 14 enabled, 2 -> 3 disabled.
- `triggers.json` -> v2.3.0.

### Instruksi routine
- Perbarui `15714d6a.md` (urutan sinkronisasi lengkap).
- Perbarui `61f30e61.md` (health check mencakup 8 bot, 17 trigger, 4 skill, 6 app).
- Perbarui `aa2deb00.md` (sinkronisasi 13 catatan tim).
- Perbarui `5af330ca.md` (pensiun; arahkan ke `b2e9a760`/`e71db9c1`).

### Dokumentasi
- `team_memory.json` / `.md` — snapshot 13 catatan tim.
- `connected_apps.json` — 6 app aktif; Slack/Notion/Gmail/Calendar tidak aktif.
- `mesin-produksi.md` dan `CATATAN-MESIN-PRODUKSI.md` — aturan terbaru 27 Nov 2026.
- `ECOSYSTEM-STATUS.md` — status ringkas ekosistem.
- `souls/superpowers-engineer.md` — soul baru.

### Keamanan
- Audit: tidak ada token/password/cookie/private key/env sensitif di repo ini.
- Kredensial hanya di `zbmaus-vela-secrets`.
