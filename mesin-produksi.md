# Mesin Produksi — Kitab Surgawi

> Ringkasan operasional mesin produksi. Detail: `CATATAN-MESIN-PRODUKSI.md`.

## Status

| Item | Nilai |
|------|-------|
| Konten | Dokumenter Kitab Surgawi |
| Jadwal produksi | Kamis 10:00 WIB (`b2e9a760`) |
| Jadwal riset | Senin 10:00 WIB (`e71db9c1`) |
| Routine lama | `5af330ca` disabled |
| Voice backend | `edge` |
| Motionmaxxing | Uji A/B saja |
| OAuth YouTube | helper lokal |
| Distribusi | Facebook Kitab Surgawi |

## Alur

Riset (Senin) -> produksi (Kamis) -> uji A/B bila perlu -> distribusi via Facebook.

Semua kredensial terkait mesin ini disimpan hanya di `zbmaus-vela-secrets`, bukan di repo publik ini.
