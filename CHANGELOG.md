# Changelog — zbmaus-vela-eco

Semua perubahan ekosistem OpenMausBot (zbmaus) dicatat di bawah ini.

---

## 2026-11-18

### Routine & Performa
- **Sinkronisasi Harian zbmaus-vela-eco**: berjalan pertama kalinya sesuai jadwal pukul 23:00 WIB.
- **Evaluasi Kualitas Harian Kitab Surgawi**: gagal 3x berturut-turut (rate limit + tool failure), retry habis dipakai.
- **Cross-post FB&IG Kitab Surgawi**: gagal 2x (tool failures), thread kedua retry masih berjalan.
- **Balasan Komentar Kitab Surgawi**: gagal 3x berturut-turut (rate limit API gratis agnes/agnes-2.5-flash), retry habis dipakai. User perlu upgrade Token Plan atau tunggu reset kuota.

### Perubahan Bot & Model
- Semua bot spesialis (YouTubeGrowth, AsnAdmin, Nova, ZbmausHumanoid-Vercel, IslamicEdu Kids) sudah distandarisasi ke model `agnes/agnes-2.5-flash` pada openaiCompat.
- ZB tetap menggunakan `gemini-3.8-flash` pada Antigravity untuk thread utama.
- Kaggle-Qwen tetap berjalan di model `qwen3.8-flash-next-gyro-gyro-s` via Kaggle T4 GPU.

### Struktur Repositori
- Folder `ecosystem/` berisi: `architecture/`, `bots.json`, `integrations/`, `memory/`, `routines/`, `skills/`, `souls/`.
- File `bots.json` diperbarui menambahkan entri ZB sebagai chief bot.
- Triggers tercatat lengkap 12 item (9 schedule, 2 interval, 1 webhook).

### Tim Memory Terbaru
- Standar model AI tim General.
- Prinsip isolasi ekosistem zbmaus (larangan sentuh repo LightVela dll).
- Pemetaan repositori ekosistem zbmaus.
- Arah produksi konten & mesin Kitab Surgawi.
- Jadwal rilis dokumenter 2x seminggu (Senin & Kamis 10:00 WIB).
- Facebook Page Kitab Surgawi (Page ID: 1467846356417352).
- Keputusan karantina video teknologi diurungkan (video tetap public).

---

*File ini diperbarui secara otomatis oleh routine Sinkronisasi Harian zbmaus-vela-eco setiap pukul 23:00 WIB.*
