# Sinkronisasi Memori Tim Mingguan

> Routine `f6e4a8ca` — ZB — Senin 07:00 WIB.
> Diperbarui 28 November 2026.

## Tugas

1. Ambil 13 catatan tim `accepted` via `session_search scope=team` (limit <= 25).
2. Bandingkan dengan `.zbmaus/raw/team_memory.json` dan `.zbmaus/raw/team_memory.md`.
3. Perbarui yang berubah; ajukan koreksi untuk key berikut bila perlu:
   - `standar-model-tim-general-2026-11`
   - `jadwal-dokumenter-kitab-surgawi`
   - `fb_page_kitab_surgawi`
   - `arah-produksi-kitab-surgawi-2026-11`
4. Commit ke eco branch `main` setelah verifikasi filter kredensial.

## Aturan

Catatan tim berisi pengetahuan operasional, bukan secret. Tetap terapkan pemeriksaan token/password/cookie/private key sebelum push.
