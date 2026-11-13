# Skills Catalog (OpenMausBot)

Katalog kapabilitas modular yang mendukung ekosistem `zbmaus`.

## System Skills
### `run-workflow`
- **Lokasi**: `skills/system/run-workflow/SKILL.md`
- **Fungsi**: Orkestrasi alur kerja dinamis multi-agen menggunakan skrip Python (`parallel`, `pipeline`, `phase`). Digunakan saat sebuah tugas terpecah menjadi banyak bagian independen atau bertahap, atau saat memerlukan konsolidasi data dari berbagai agen.

## Custom & Imported Skills
- **Status saat ini**: Tidak ada skill eksternal yang diimpor langsung ke ZB. Keterampilan fungsional dikelola melalui tupoksi agen spesialis (seperti AsnAdmin untuk naskah dinas ASN dan YouTubeGrowth untuk analitik YouTube).
- **Prosedur Penambahan**: Dikelola melalui perintah `/learn` atau alat `skills_list` dan `skill_manage` dengan persetujuan pengguna.
