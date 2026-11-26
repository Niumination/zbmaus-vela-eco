# Changelog ✨ zbmaus-vela-eco

Semua perubahan ekosistem OpenMausBot (zbmaus) dicatat di bawah ini.

---

## 2026-11-27

### 🔄 Sinkronisasi & Backup Harian (routine 23:00 WIB)
- **Inventarisasi live:** 8 bot + model terverifikasi, 15 routine (13 aktif / 2 once nonaktif), 4 skill, 0 room, 13 catatan tim, 5 repo zbmaus.
- **Diperbarui:** `ecosystem/bots.json` v1.3.0 (status trigger & model aktual), `ecosystem/routines/triggers.json` v2.2.0 (lastRun & failureStreak — Cek GitHub kembali ke 0 setelah sukses 26 Nov), `ecosystem/integrations/connected_apps.json` (catatan OAuth YouTube), `ecosystem/skills/catalog.md` (tambah `omb-bot-creation`, koreksi `omb-routine-scheduling`), `ecosystem/memory/team_memory.{md,json}` (inventarisasi 27 Nov).
- **Ditambahkan:** `ecosystem/mesin-produksi/CATATAN-MESIN-PRODUKSI.md` — salinan lengkap dokumentasi mesin (ffmpeg 2-pass, QC gate, edge-tts, aturan dalil, jalur upload, gate terbaru 26 Nov) agar prosedur tidak lagi hanya berupa ringkasan.
- **Verifikasi:** checkout lokal yang bercabang direkonsiliasi ke HEAD remote sebelum penulisan; credential scan tidak menemukan token/kata sandi/kunci privat di file publik; kredensial & `omb-state-*` tetap hanya di repo privat.
- **24 Nov — koreksi:** git push lokal gagal autentikasi (helper token tidak valid); penulisan remote dilakukan lewat koneksi GitHub terhubung.

---

## 2026-11-26

### 🤖 Onboarding Superpowers Engineer
- **Bot baru**: `Superpowers Engineer` (id `134f49fb-c860-41e9-a45e-13b00c8dac67`) — bot ke-8 ekosistem zbmaus.
- **Model**: `opencode/deepseek-v4.1-flash-free` (diverifikasi via daftar bot OMB).
- **Peran**: spesialis metodologi engineering — brainstorm → worktree → rencana 2–5 menit → TDD RED-GREEN-REFACTOR → review per tugas → verifikasi.
- **File baru**:
  - `ecosystem/souls/superpowers-engineer.md` — soul/profile bot.
  - `ecosystem/skills/catalog.md` — skill `superpowers-workflow` (obra/superpowers v7.0.2, MIT).
  - `ecosystem/architecture/overview.md` — node Superpowers Engineer di diagram.
  - `ecosystem/bots.json` — stats `bots=8`.

### 🔍 Koreksi Model Aktual (v1.2.1)
Diverifikasi langsung dari daftar bot OMB, bukan dari catatan lama:

| Bot | Sebelum | Sesudah |
|---|---|---|
| ZB | `tidepool-alpha-free` | `opencode/longcat-2.5-free` |
| IslamicEdu Kids | `agnes/agnes-2.5-flash` | `opencode/hy4-flash-free` |
| Kaggle-Qwen | `qwen/qwen3.8-flash-next-gyro-gyro-s` | `qwen3.8-flash-next-gyro-gyro-s` |
| Superpowers Engineer | `agnes/agnes-2.5-flash` | `opencode/deepseek-v4.1-flash-free` |

### 📚 Sinkronisasi Dokumentasi
- **README.md** — 8 bot, 13 catatan tim, tabel 6 repo resmi, struktur direktori diperbaiki.
- **`ecosystem/repos/`** — 5 catatan baru: `zbmaus-vela`, `zbmaus-vela-secrets`, `zbmaus-vela-eco`, `asn-admin`, `zbmaus-humanoid`.
- **`ecosystem/memory/team_memory.json`** — 11 → 13 catatan (tambah adopsi superpowers & repo zbmaus-kitab-surgawi).
- **`ecosystem/memory/team_memory.md`** — narasi dua catatan baru.
- **CHANGELOG.md** — perbaikan teks rusak pada entri 24 Nov dan entri 25 Nov yang hilang.

### 🔧 Status Ekosistem (26 Nov)
- **VPS sehat**: uptime 39 hari, disk 79% (11 GB bebas), RAM 4,6/7,4 GiB.
- **Kaggle Strata DOWN** (error 1033): session mati, perlu "Run All" manual.
- **Kaggle GPU Qwen3.8-27B v6**: notebook sudah push, masih antre debug — belum di-Run All.
- **Backup harian**: masih gagal sejak 22–23 Nov (`zb-backup.timer`, `zb-backup-full.timer`).
- **Superpowers plugin**: terpasang dan aktif.
- **Rekonsiliasi routine**: total 15 (13 enabled, 2 disabled) + 10 archived one-off. Angka 9 pada entri 24 Nov hanya menghitung trigger aktif per-bot saat itu.

---

## 2026-11-25

### 🗂️ Sinkronisasi Status Dini Hari
- `ECOSYSTEM-STATUS.md` disinkronkan ke kondisi 26 Nov (commit `d3382073`, 25 Nov 19:12 UTC).
- **Pembersihan storage VPS**: pemakaian disk turun dari 96% ke 79% (11 GB bebas).
- Tidak ada perubahan struktur repo.

---

## 2026-11-24

### 🔄 Sinkronisasi & Backup Harian Ekosistem zbmaus (routine otomatis 23:00 WIB)
- **Inventory bot**: `ecosystem/bots.json` diperbarui (7 bot saat itu, role/model/triggers terbaca).
- **Inventory trigger**: `ecosystem/routines/triggers.json` diperbarui (9 trigger aktif per-bot saat itu).
- **Apps**: `ecosystem/integrations/connected_apps.json` diperbarui (Gmail/Google Calendar/Slack/Notion tidak terhubung).
- **Mesin produksi**: `ecosystem/routines/mesin-produksi.md` ditulis (engine-v3, QC gate, jadwal upload).
- **Team memory**: `ecosystem/memory/team_memory.md` diperbarui dengan inventory ekosistem 24 Nov 2026.
- **GitHub (Niumination)**: 178 repo; routine "Cek perubahan GitHub harian" gagal (`failureStreak 8`).

---

## 2026-11-22

### 🛠️ Maintenance Harian (routine otomatis 23:00 WIB)
- `triggers.json` dinaikkan ke **v1.6.0**: routine baru `Penjaga Kualitas Kitab Surgawi — review harian` (cron 15:45 WIB, enabled).
- Routine Penjaga Kualitas berjalan normal (review 21 Nov).
- Morning Brief Nova gagal ke-5x (rate limit); perlu upgrade Token Plan.

---

## 2026-11-21

### 📦 Repo Proyek Spesifik
- `zbmaus-kitab-surgawi` (privat) didaftarkan resmi di ekosistem: `ecosystem/repos/zbmaus-kitab-surgawi.md`, README, dan `bots.json`.
