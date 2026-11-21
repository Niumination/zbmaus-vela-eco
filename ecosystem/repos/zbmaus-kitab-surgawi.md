# zbmaus-kitab-surgawi

> Repo proyek spesifik — bot YouTubeGrowth Kitab Surgawi.
> Bagian dari ekosistem OpenMausBot (zbmaus). Diregistrasi di snapshot ini pada 21 Nov 2026.

## Identitas
| Field | Nilai |
|---|---|
| Repo | https://github.com/Niumination/zbmaus-kitab-surgawi |
| Visibilitas | Privat (branch main) |
| Bot pemilik | YouTubeGrowth Kitab Surgawi |
| Bot ID | 3bbb857a-0cdc-4849-898b-a135cf3bf78c |
| Channel | https://www.youtube.com/@kitabsurgawi-1357 |
| Dibuat | 21 Nov 2026 |

## Isi repo
- engine-v3/ — renderer Short harian, QC gate sebelum upload, backend suara (edge/chirp3/voxcpm2/azure/chatterbox), pustaka aset, panduan mesin, bukti QC.
- docs/ — catatan mesin produksi, riset suara, log kualitas harian.
- config/SOUL.md — salinan instruksi tetap bot (sumber resmi tetap di pengaturan OpenMausBot).
- README.md, .gitignore.

## Batasan
Tidak menyimpan kredensial, token OAuth YouTube, state runtime, atau file video produksi (~563 MB). Semua itu tetap berada di workspace/VPS lokal bot. Repo ini hanya cadangan kode dan dokumentasi.

## Status produksi (21 Nov 2026)
- Short harian memakai mesin v3 dengan voice_backend="edge"; eksperimen backend suara lain ditahan sampai ada aba-aba.
- QC gate wajib lolos sebelum upload; ayat Qur'an memakai reciter manusia.
- Pengawasan kualitas: evaluasi 15:30 WIB + review 15:45 WIB (Penjaga Kualitas).

## Hubungan dengan repo zbmaus lain
zbmaus-vela (infrastruktur VPS) · zbmaus-vela-secrets (kredensial) · zbmaus-vela-eco (snapshot ekosistem — file ini) · asn-admin (mesin administrasi ASN) · zbmaus-humanoid (antarmuka humanoid) · zbmaus-kitab-surgawi (mesin produksi konten dakwah).
