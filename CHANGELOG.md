# Changelog — zbmaus-vela-eco

Semua perubahan ekosistem OpenMausBot (zbmaus) dicatat di bawah ini.

---

## 2026-11-22

### Sinkronisasi Harian (routine otomatis pukul 23:00 WIB)
- **triggers.json** dinaikkan ke v1.6.0: menambah routine baru `4fbc7fa4` (“Penjaga Kualitas Kitab Surgawi — review harian”, cron 15:45 WIB, enabled). Total 15 routine (13 enabled, 2 disabled archived).
- **bots.json**: timestamp diperbarui, tidak ada perubahan model atau profil bot.
- Routine berjalan normal hari ini: Penjaga Kualitas ✅ (review 21 Nov — kualitas terjaga, gate foto dHash lulus, Short RLY9ykDBNOA tayang QC pass).
- Morning Brief Nova gagal ke-5x berturut (rate limit agnes/agnes-2.5-flash API gratis); failure streak meningkat. Perlu upgrade Token Plan.
- Routine Cek GitHub harian gagal ke-5x (tool failures) pada 21 Nov; failure streak 5.

### Audit & Sanitasi
- Repo publik eco 100% bebas kredensial sensitif.
- Tidak ada perubahan kredensial atau state internal OMB.
- Kredensial dan `omb-state-*.json` tetap hanya di secrets repo.

---

## 2026-11-21