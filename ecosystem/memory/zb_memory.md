# ZB Long-Term & Topic Memory

## MEMORY.md (Long-term Facts)
- **2026-11-02** (dari obrolan 'integrasikan ini ke ekosistem kita saat ini'): Dibuat bot spesialis **Nova** (ID `8217c1f3-e5da-4872-b68f-7dc645123226`) di departemen General untuk menangani tupoksi baru & integrasi ekosistem berdasarkan pola dari 7 repositori: ZimZilla, google/elephant-goldfish-model, aicodeking/leanrea, morluto/rea, multica-ai/andrej-karpathy-skills, NandhaKishorM/laya, ipenywis/laya-ultrafast.

## Topic Notes

### 1. `memory/project.md` (Project & Platform Policies)
- **2026-10-29**: Pengguna memiliki ekosistem bernama `zbmaus` (OpenMausBot) yang dibangun di atas GitHub.
- **2026-10-29**: Pengguna lebih memilih mengadaptasi isi konten dan pola dari repositori daripada menduplikasi mentah repositori itu sendiri.
- **2026-10-30**: Pengguna tidak ingin bergantung pada `ecosystem-omb` dan memilih membangun arsitektur baru. Repositori `ecosystem-omb` diabaikan.
- **2026-10-30**: Repositori `lightvela`, `ecosystem-config`, dan `mirai` diabaikan sebagai referensi proyek langsung.
- **2026-11-03**: Pengguna memutuskan memindahkan model chatbot `zbmaus-humanoid` dari Kaggle ke model Beam via OpenRouter (`nous/reflection/beam-1.0-501b-a23b`).
- **2026-11-03**: Bot `zbmaus-humanoid` sukses di-deploy ulang dengan model Beam via OpenRouter.

### 2. `memory/language.md` (Bahasa Percakapan)
- **2026-10-29**: Pengguna menetapkan Bahasa Indonesia sebagai bahasa utama/default dalam seluruh percakapan, kecuali secara eksplisit meminta bahasa lain.

### 3. `memory/github.md` (GitHub Workspace)
- **2026-10-29**: Pengguna memiliki workspace privat GitHub bernama OMB.
- **2026-10-29**: Akun GitHub (`Niumination`) terhubung aktif ke ekosistem.


### 4. Pembaruan MEMORY.md (Long-term Facts, 2026-11-18)
- **2026-11-16**: Ringkasan insiden routine: Evaluasi Kualitas Harian Kitab Surgawi gagal 3x (rate limit); Cross-post FB&IG gagal 2x; Balasan Komentar gagal 3x (rate limit API agnes gratis) — perlu upgrade Token Plan atau tunggu reset kuota.
- **2026-11-18**: Routine Sinkronisasi Harian zbmaus-vela-eco mulai berjalan sesuai jadwal 23:00 WIB (run pertama mengalami failure streak due truncated tool calls).
- **2026-11-18**: Preferensi user: perintah sangat pendek ('lanjutkan', 'jawaban singkat') dan mengharapkan ringkasan harian seluruh routine yang berjalan/gagal/retry.
- **2026-11-18**: User menjalankan maintenance ekosistem larut malam ~23:00 WIB dan memantau async.

### Pembaruan 2026-11-27 (dari MEMORY.md live)
- Model ZB aktif: `opencode/longcat-2.5-free` (bukan gemini-3.8-flash / agnes seperti catatan lama).
- Routine rutin: Sinkronisasi & Backup Harian 23:00 WIB dan Cek perubahan GitHub 09:00 WIB; Cek GitHub sukses 26 Nov dengan 15 repo aktif dan 136 commit dalam 24 jam, failureStreak kembali 0.
- Pola kerja user: instruksi sangat singkat ("lanjutkan", "jawaban singkat"), ingin update bertahap, dan ringkasan akhir hari untuk semua routine yang berjalan/gagal/dicoba ulang.
