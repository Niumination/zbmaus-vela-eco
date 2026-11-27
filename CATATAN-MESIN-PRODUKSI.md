# CATATAN-MESIN-PRODUKSI

> Diperbarui 28 November 2026 oleh routine Sinkronisasi & Backup Harian Ekosistem zbmaus.
> Sumber: dokumentasi produksi Kitab Surgawi per 27 November 2026.

## Aturan terbaru (27 Nov 2026)

1. **Dokumenter Kitab Surgawi**: 1x per minggu, **Kamis 10:00 WIB** — routine `b2e9a760`.
2. **Senin 10:00 WIB**: **hanya riset konten** — routine `e71db9c1`. Tidak produksi.
3. Routine lama `5af330ca` **dinonaktifkan**; digantikan `e71db9c1` + `b2e9a760`.
4. `voice_backend="edge"` — **jangan diubah** tanpa persetujuan.
5. `motionmaxxing` **hanya untuk uji A/B**, bukan produksi final.
6. Akses YouTube wajib via **helper OAuth lokal** — tidak ada token di repo publik.
7. Distribusi utama: halaman Facebook Kitab Surgawi.

## Daftar aset produksi

- Sumber dokumentasi: `CATATAN-MESIN-PRODUKSI.md` (workspace produksi).
- Rencana tayang mingguan: `rencana-tayang-mingguan.md`.
- Helper OAuth: `memory/yt-oauth-helpers.md` (referensi internal, bukan kredensial).

## Pemeriksaan

- [x] Jadwal routine diverifikasi terhadap data live.
- [x] Status `5af330ca` = disabled.
- [x] `b2e9a760` dan `e71db9c1` = enabled.
- [x] Tidak ada token/kredensial dalam dokumen ini.
