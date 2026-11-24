# Changelog — zbmaus-vela-eco

Semua perubahan ekosistem OpenMausBot (zbmaus) dicatat di bawah ini.

---

## 2026-11-24

### Sinkronisasi & Backup Harian Ekosistem zbmaus (routine otomatis pukul 23:00 WIB)
- **Inventarisasi lengkap:** ecosystem/bots.json diperbarui (7 bot, role/model/triggers terbaru).
- **Inventarisasi trigger:** ecosystem/routines/triggers.json diperbarui (9 routines; ZB: 3, YouTubeGrowth: 5, ZbmausHumanoid-Vercel: 1 webhook, Nova: 1).
- **Apps:** ecosystem/integrations/connected_apps.json diperbarui (Gmail/Google Calendar/Slack/Notion ditandai not_connected).
- **Mesin produksi:** ecosystem/routines/mesin-produksi.md ditulis (engine-v3, QC gate, jalur upload uguu.se → BOLDSIGN_FILE_UPLOAD → s3key → YOUTUBE_MULTIPART_UPLOAD_VIDEO).
- **Team memory:** ecosystem/memory/team_memory.md diperbarui dengan inventarisasi ekosistem 24 Nov 2026.
- **GitHub (Niumination):** 178 repos, tidak ada commit baru sejak 24 jam (Cek GitHub harian gagal, failureStreak 8).

---

## 2026-11-22

### Sinkronisasi Harian (routine otomatis pukul 23:00 WIB)
- **triggers.json** dinaikkan ke v1.6.0: menambah routine baru `4fbc7fa4` ("Penjaga Kualitas Kitab Surgawi — review harian", cron 15:45 WIB, enabled).
- Routine berjalan normal hari ini: Penjaga Kualitas (review 21 Nov).
- Morning Brief Nova gagal ke-5x (rate limit); perlu upgrade Token Plan.

---

## 2026-11-21