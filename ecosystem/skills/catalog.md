# Skills Catalog (OpenMausBot)

Katalog kapasitas modular yang digunakan ekosistem `zbmaus`.

## System Skills

### `run-workflow`
- **Lokasi**: `skills/system/run-workflow/SKILL.md`
- **Fungsi**: Orkestrasi alur kerja dinamika multi-agent menggunakan skrip Python (`parallel`, `pipelined`, `phase`). Digunakan untuk setiap tugas terpecah banyak bagian independen atas bertahap, atas satuan konsolidasi data dari berbagai agen.

## Imported / Learned Skills (terdaftar di ZB, status enabled)

### `omb-ecosystem-sync` 👥 Prosedur sinkronisasi state ekosistem zbmaus (bot, routing, memory, apps, skills, souls) ke `zbmaus-vela-eco` dan cadangan `zbmaus-vela-secrets`, dilengkapi deskripsi kredensial dan verifikasi commit.

### `omb-routine-scheduling` 👥 Prosedur pemantauan, pembaruan, dan verifikasi automasi/routing OpenMausBot (schedule, interval, webhook, app-event), termasuk konversi jadwal ke cron dan timezone Asia/Jakarta.

### `omb-bot-creation` 👥 Prosedur pembuatan dan konfigurasi bot spesialis di OpenMausBot (peran, model, skill, dan profil melalui alat resmi). Digunakan untuk menambah spesialis baru tanpa computer control.

### `superpowers-workflow` 👥 Metodologi engineering tim General (diadopsi 26 Nov 2026). Berdasarkan obra/superpowers v7.0.2 (MIT, https://github.com/obra/superpowers). Langkah wajib: brainstorm → isolasi worktree → rencana tugas kecil 2-5 menit di docs/superpowers/plans/ dengan path file dan tes pasti → eksekusi satu tugas per thread coordinate_bots disertai review → TDD RED-GREEN-REFACTOR → verifikasi penuh sebelum klaim selesai. Bot berjalan di opencode/seaglass-alpha-free (diverifikasi 29 Nov 2026).

## Procedure Notes
- Diutamakan melewati `skills_list` dan `skill_manage` untuk pengelolaan.
- Keunggulan fungsional dikelompokkan topik agen spesialis (khusus AsnAdmin khusus dinas ASN dan YouTubeGrowth khusus analitik YouTube).
