# Changelog ✨ zbmaus-vela-eco

Semua perubahan ekosistem OpenMausBot (zbmaus) dicatat di bawah ini.

---

## 2026-11-26

### 🤖 Onboarding Superpowers Engineer
- **Bot baru**: Tambah `Superpowers Engineer` (id: `134f49fb-c860-41e9-a45e-13b00c8dac67`) sebagai bot ke-8 di ekosistemzbmaus.
- **Model**: `agnes/agnes-2.5-flash` (standarisasi tim General).
- **Peran**: Spesialis metodologi engineering — menerapkan alur Superpowers pada tiap tugas coding.
- **File baru**:
  - `ecosystem/souls/superpowers-engineer.md` — soul/profile bot baru.
  - `ecosystem/skills/catalog.md` — tambahkan skill `superpowers-workflow` (diadopsi dari obra/superpowers v7.0.2 MIT).
  - `ecosystem/bots.json` — update stats: bots=8.
  - `ecosystem/architecture/overview.md` — update diagram mermaid dengan node Superpowers Engineer.

### 🔧 Status Ekosistem (26 Nov)
- **VPS sehat**: Uptime 39 hari, disk 79% (11 GB bebas), RAM 4.6/7.4 GiB.
- **Kaggle Strata DOWN** (error 1033): Session mati, perlu "Run All" manual.
- **Kaggle GPU Qwen3.8-27B v6**: Notebook sudah push, masih antre debug — belum di-Run All.
- **Backup harian**: Masih failed sejak 22–23 Nov (`zb-backup.timer`, `zb-backup-full.timer`).
- **Superpowers plugin**: Terpasang dan aktif.
- **Total routine**: 15 (13 enabled, 2 disabled, 10 archived one-off).

### 📊 Sinkronisasi Harian
- `bots.json` v1.2.0 — sinkronisasi state bot terbaru.
- `triggers.json` tetap v1.6.0 — belum ada perubahan routine.

---

## 2026-11-24

### 🔄 Sinkronisasi & Backup Harian Ekosistem zbmaus (routine otomatis pukul 23:00 WIB)
- **Inventory lengkap**: `ecosystem/bots.json` diperbarui (7 bot, role/model/triggers terbaca).
- **Inventory triggers**: `ecosystem/routines/triggers.json` diperbarui (9 routines; ZB: 3, YouTubeGrowth: 5, ZbmausHumanoid-Vercel: 1 webhook, Nova: 1).
- **Apps**: `ecosystem/integrations/connected_apps.json` diperbarui (Gmail/Google Calendar/Slack/Notion tidak_not_connected).
- **Mesin produksi**: `ecosystem/routines/mesin-produksi.md` ditulis (engine-v3, QC gate, jadwal uploaduggle.sé BOLD SIGN FILE UPLOAD_ID YouTube MULTIPART_UPLOAD_VIDEO).
- **Team memory**: `ecosystem/memory/team_memory.md` diperbarui dengan inventory ekosistem 24 Nov 2026. – **GitHub (Niumination)**: 178 repos, terbaru ada commit baru sehari 24 jam (Cek GitHub harian gagal, failureStreak 8).

---

## 2026-11-22

### 🛠️ Maintenance Harian (routine otomatis pukul 23:00 WIB)
- **`triggers.json`** dinalaikkan ke v1.6.0: menambahkan routine baru `"Penjaga Kualitas Kitab Surgawi → review harian"` (cron 15:45 WIB, enabled).
- Routine berjalan normal hari ini ini: Penjaga Kualitas (review 21 Nov).
- Morning Brief Nova gagal ke-5x (rate limit); perlu upgrade Token Plan.

---

## 2026-11-21