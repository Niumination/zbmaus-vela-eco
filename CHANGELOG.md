# Changelog — zbmaus-vela-eco

Semua perubahan ekosistem OpenMausBot (zbmaus) dicatat di bawah ini.

---

## 2026-11-19

### Sinkronisasi Penuh (manual oleh ZB)
- **Sinkronisasi menyeluruh** ke `zbmaus-vela-eco` dan `zbmaus-vela-secrets`: seluruh state ekosistem diperbarui tanpa komponen tertinggal, tetap 100% bebas kredensial sensitif di repo publik.
- `ecosystem/routines/triggers.json` dinaikkan ke v1.3.0: **14 routine aktif** dengan instruksi lengkap + **10 routine sekali-jalan terarsip**.
  - Routine baru 19 Nov yang sebelumnya tertinggal: **Upload EP-003 to YouTube after quota reset** (2f8d2271) dan **Kitab Surgawi: tambah Short ke playlist & cek status** (5630e281).
  - Dua instruksi produksi (Monitoring aa2deb00, Cross-post 15714d6a) ditandai `instructions_truncated_in_source` karena teks aslinya terpotong batas sistem.
- File baru `ecosystem/routines/mesin-produksi.md`: dokumentasi lengkap pipeline produksi (ffmpeg 2-pass, jalur upload tmpfiles/uguu→BOLDSIGN→multipart, edge-tts, aturan dalil, cross-post, balasan komentar, evaluasi, jadwal mingguan) — sebelumnya hanya tersimpan sebagai ringkasan 1-3 kalimat.

### Routine & Performa
- **Monitoring & Produksi Harian Kitab Surgawi** (19 Nov): short "Doa Keluar Rumah" tayang (1CViKufzdmQ, oEmbed 200), kuota YouTube habis setelah upload → playlist/EP-003 dijadwalkan otomatis. Run ditandai failed karena model `opencode/glm-5.3-flash-free` tidak ditemukan.
- **Produksi Dokumenter EP-003 "Rempah & Sutra"** (19 Nov): render selesai; upload YouTube ditunda kuota, Short A/B sudah tayang di Facebook & Instagram.
- **Balasan Komentar Kitab Surgawi** (19 Nov): tidak dapat dijalankan — OAuth YouTube mengembalikan 403 (token ter-revoke); perlu reconnect akun di Composio.
- **Cross-post FB&IG** (19 Nov): berjalan normal, tidak ada konten baru yang perlu disebar.

### Perubahan Bot & Model
- Model default YouTubeGrowth saat ini `opencode/glm-5.3-flash-free` (opencodeGo) bermasalah di runtime; disarankan kembali ke `agnes/agnes-2.5-flash` sesuai standar tim.
- Soul `youtubegrowth-kitab-surgawi.md` diselaraskan dengan model aktual.

### Backup Ekosistem
- `zbmaus-vela-secrets` diperbarui: indeks bot dan state routine disinkronkan ke kondisi aktual 19 Nov.
- **Automation backup penuh kini aktif**: routine `Sinkronisasi & Backup Harian Ekosistem zbmaus` (cron `0 23 * * *`, Asia/Jakarta) menggabungkan sinkronisasi eco + cadangan secrets dalam satu jalur. Urutan: kumpulkan seluruh state (7 bot, semua routine 4 bot, 11 memory, 12 apps, 2 skill, 5 repo, mesin produksi) → audit/sanitasi → tulis eco → backup secrets → verifikasi. Kredensial & `omb-state-*.json` dikecualikan.

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

*File ini diperbarui oleh routine Sinkronisasi & Backup Harian Ekosistem zbmaus setiap pukul 23:00 WIB, dan sinkronisasi penuh manual bila diperlukan.*
