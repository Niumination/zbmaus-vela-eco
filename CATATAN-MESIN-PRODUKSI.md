# CATATAN-MESIN-PRODUKSI

> Diperbarui 28 November 2026 berdasarkan data trigger live. Versi sebelumnya keliru menamai `b2e9a760` dan `e71db9c1`.

## Fakta trigger (data live)

| ID | Routine | Jadwal | Status |
|----|---------|--------|--------|
| 61f30e61-c25a-49e9-86bb-7f5cbf3f5296 | Penyusunan Jadwal & Materi Tayang Mingguan (Senin = riset saja) | Senin 07:00 WIB | enabled |
| e71db9c1-84d6-482a-b40b-e7d193322a78 | Produksi & Publikasi Dokumenter Islami (Kamis 10:00, 8-12 menit) | Kamis 10:00 WIB | enabled |
| 5af330ca-15f2-41f8-8c83-a2cf1dd9e1d6 | Produksi & Publikasi Dokumenter Islami (lama, Senin+Kamis 10:00) | — | **disabled** |
| b2e9a760-67bf-4fe2-9c40-7b7da725a0b4 | Bersih-bersih Storage Produksi | harian 03:00 WIB | enabled |
| 4fbc7fa4-03ca-4fa1-aec0-5a8025fc8514 | Penjaga Kualitas — review harian | 15:45 WIB | enabled |
| 6a5fd5fa-6aca-4ca5-812c-a8e62d1b8daa | Evaluasi Kualitas & Peningkatan Mesin | 15:30 WIB | enabled |

## Aturan produksi

1. Dokumenter 1 episode/minggu: **Kamis 10:00 WIB** (`e71db9c1`), durasi 8-12 menit.
2. **Senin 07:00 WIB** (`61f30e61`): riset, jadwal, kurasi aset — bukan produksi.
3. `5af330ca` **disabled** (digantikan `e71db9c1`).
4. `b2e9a760` hanya **bersih-bersih storage**, bukan produksi konten.
5. `voice_backend="edge"` (edge-tts id-ID); backend lain ditahan.
6. YouTube wajib via helper OAuth lokal `/opt/yt-oauth/` (token Composio revoked 403).
7. `motionmaxxing` hanya uji A/B, bukan produksi final.
8. Distribusi: Short harian 09:00 FB/IG, cross-post 12:00 & 21:00 (`15714d6a`).

## Pemeriksaan

- [x] 17 trigger diverifikasi terhadap data live.
- [x] Tidak ada kredensial dalam dokumen ini.
