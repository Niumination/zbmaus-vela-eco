# Skills Catalog (OpenMausBot)

Katalog kapabilitas modular yang mendukung ekosistem `zbmaus`.

## System Skills
### `run-workflow`
- **Lokasi**: `skills/system/run-workflow/SKILL.md`
- **Fungsi**: Orkestrasi alur kerja dinamis multi-agen menggunakan skrip Python (`parallel`, `pipeline`, `phase`). Digunakan saat sebuah tugas terpecah menjadi banyak bagian independen atau bertahap, atau saat memerlukan konsolidasi data dari berbagai agen.

## Imported / Learned Skills (terpasang di ZB, status enabled)
- **`omb-ecosystem-sync`** — Prosedur sinkronisasi state ekosistem zbmaus (bot, routine, memory, apps, skills, souls) ke `zbmaus-vela-eco` dan cadangan `zbmaus-vela-secrets`, lengkap dengan sanitasi kredensial dan verifikasi commit.
- **`omb-routine-scheduling`** — Prosedur pembuatan, pembaruan, dan verifikasi automation/routine OpenMausBot (schedule, interval, webhook, app-event), termasuk konversi jadwal ke cron dan timezoneAsia/Jakarta.

- **Prosedur Penambahan**: Dikelola melalui perintah `/learn` atau alat `skills_list` dan `skill_manage` dengan persetujuan pengguna.
- Keterampilan fungsional lain dikelola melalui tupoksi agen spesialis (seperti AsnAdmin untuk naskah dinas ASN dan YouTubeGrowth untuk analitik YouTube).
