# Mesin Produksi & Publikasi Otomatis — Kitab Surgawi

Dokumen ini merangkum konfigurasi teknis mesin produksi konten YouTube Kitab Surgawi (@kitabsurgawi-1357) agar tidak hilang saat sinkronisasi. Bersifat publik: tanpa kredensial. Sumber: instruksi routine Monitoring & Produksi Harian (aa2deb00), Produksi Dokumenter (5af330ca), Evaluasi Kualitas (6a5fd5fa), dan Penyusunan Jadwal Mingguan (61f30e61).

## 1. Identitas Channel & Akun
- Channel: @kitabsurgawi-1357, channelId UCs-1tjk6U6vMqqChpaR4j8w
- Akun Composio YouTube: "Zbmaus"
- Facebook Page: "Kitab Surgawi", Page ID 1467846356417352, akun Composio "AM"
- Instagram: @zhall_abstract, akun Composio "Abstract", ig_user_id "me"
- Target: YPP — 1.000 subscriber & 4.000 jam tayang
- Izin produksi & publish otomatis diberikan user 13 Nov 2026 (tanpa perlu approval per video)

## 2. Pipeline Produksi Short Harian
1. Baca pelajaran terakhir dari memory/kitab-surgawi-kualitas.md (sharedBotFolder) dan terapkan.
2. Cek performa via YOUTUBE_GET_VIDEO_DETAILS_BATCH + subscriber dari halaman publik.
3. Materi: 1 Short dakwah amalan 30-60 detik. Topik dari pola terbukti: amalan 1 menit / waktu mustajab / dalil sahih (HR. Bukhari-Muslim atau takhrij terverifikasi). JANGAN mengarang hadits; ragu → pakai sumber sudah dishahihkan + tulis takhrij di deskripsi. Judul hook target CTR > 5%; deskripsi SEO + 15-20 tag (total < 500 karakter); konsep thumbnail.
4. Render vertikal 720x1280 (standar skill high-retention-video-production): multi-scene Ken Burns, subtitle kinetik per frasa dengan timestamp mengikuti audio, kata kunci kuning emas, teks Arab pakai font khat bila ada ayat.
5. Suara: edge-tts id-ID (risiko lisensi abu-abu sudah disetujui user untuk konten dakwah).
6. Simpan hasil di folder kerja harian.

## 3. Jalur Upload YouTube (terbukti; JANGAN pakai YOUTUBE_UPLOAD_VIDEO resumable — menghasilkan video rusak)
1. Kompres 2-pass ffmpeg ke <= 3.2 MB:
   - vb_kbps = target_bytes*8/durasi_detik/1000 - 74
   - preset pass 2 HARUS sama dengan pass 1 (veryfast)
2. Stage file: curl -F "file=@file.mp4" https://tmpfiles.org/api/v1/upload → ambil link halaman → temukan link unduhan langsung berformat tmpfiles.org/dl/<token>/... → verifikasi file terunduh utuh (bytes cocok).
   - Alternatif yang dipakai: uguu.se → unduh di sandbox Composio (curl -L, verifikasi md5) → upload_local_file di workbench → s3key.
3. BOLDSIGN_FILE_UPLOAD bila diperlukan untuk mendapatkan s3key.
4. YOUTUBE_MULTIPART_UPLOAD_VIDEO dengan s3key; categoryId "27", privacyStatus "public".
5. Verifikasi tayang: oEmbed https://www.youtube.com/oembed?url=...&format=json harus HTTP 200 (public & playable).
6. Tambahkan ke playlist ("Amalan 1 Menit 🕌" / "Dokumenter Islami 🕌") via YOUTUBE_ADD_VIDEO_TO_PLAYLIST; hindari duplikat.

## 4. Dokumenter Islami (Netflix-style)
- Jadwal: 2 episode/minggu, Senin & Kamis 10:00 WIB (expression 0 10 * * 1,4).
- Riset: minimal 2 sumber independen per fakta sejarah utama; naskah Indonesia lugas, tanpa klaim kontroversial.
- Render horizontal 1080p: visual dokumen/peta/arsip klasik, narasi sinkron, musik syahdu bebas hak cipta.
- 2 segmen Shorts vertikal 45-60 detik sebagai hook, pinned komentar ke video penuh.
- Upload video utama + Shorts ke YouTube, lalu cross-post ke FB & IG.
- Antrean episode: EP-002 Ibnu Sina (VDAKHSEwtoU), EP-003 Rempah & Sutra (file lokal ep003_final.mp4), seterusnya.

## 5. Aturan Dalil (ketat)
- Dalil hanya dari sumber sahih primer: HR. Bukhari, Muslim, Tirmidzi, Abu Dawud — dengan takhrij.
- Dilarang mengarang hadits/tafsir di luar sumber.
- Pertanyaan hukum/fatwa di luar isi video → arahkan ke ustadz/ulama terpercaya, tanpa memvonis.
- Contoh takhrij terpakai: doa keluar rumah HR. Abu Dawud 5095 & Tirmidzi 3426 (shahih Al-Albani); doa maghrib 7x HR. Abu Dawud 5015 (shahih, Sahih al-Jami' 6172); Ayat Kursi + 3 Qul (al-Hakim/Al-Albani, HR. Bukhari 5017, Abu Dawud 5082, Tirmidzi 3575); dzikir 33x HR. Muslim 597; doa sebelum tidur HR. Bukhari 6320.

## 6. Cross-post Facebook & Instagram
- Interval 180 menit, window 08:00-23:00.
- Video native, bukan link. Download via yt-dlp (kualitas tertinggi); gagal atau > 1 GB → lewati & catat.
- FB: FACEBOOK_CREATE_VIDEO_POST (akun AM, published=true). Caption: 1-2 kalimat hook + #KitabSurgawi + hashtag topik. Tanda '#' apa adanya, BUKAN '%23'. Tanpa link keluar. Komentar pertama: link YouTube + link subscribe.
- IG Reels: INSTAGRAM_POST_IG_USER_MEDIA (akun Abstract, REELS, share_to_feed true). Sumber: video_file via upload_local_file (paling andal). Link YouTube di komentar pertama.
- Dilewati: video > 90 detik / 16:9 (dokumenter) dari IG Reels; 4 video teknologi (MATA ×3, 9Router) tidak disebar (bukan dakwah, tetap public di YouTube).

## 7. Balasan Komentar
- Interval 120 menit, window 08:00-23:00. Balas komentar tanpa balasan yang umurnya > 2 jam.
- YOUTUBE_LIST_COMMENT_THREADS2 (akun Zbmaus, part snippet,replies, allThreadsRelatedToChannelId UCs-1tjk6U6vMqqChpaR4j8w, order time, maxResults 50, moderationStatus published).
- Balas via YOUTUBE_CREATE_COMMENT_REPLY. Spam → heldForReview. Nada hangat, 1-3 kalimat, atas nama channel, tanpa klaim keulamaan.
- Catatan 19 Nov: OAuth YouTube mengembalikan 403 pada endpoint komentar (token ter-revoke) — perlu reconnect akun di Composio.

## 8. Evaluasi Kualitas Harian (15:30 WIB)
- Statistik via YOUTUBE_GET_VIDEO_DETAILS_BATCH; hitung laju views harian; analisis hook/topik/durasi/gaya visual.
- Tulis 1-3 pelajaran ke memory/kitab-surgawi-kualitas.md.
- Kembangkan mesin produksi (motion graphic, tipografi kinetik, 3D/parallax 2.5D, filter film/vintage, FFmpeg filters, audio ducking, riser/whoosh, ambient) → catat ke CATATAN-MESIN-PRODUKSI.md.

## 9. Penyusunan Jadwal Mingguan (Senin 07:00 WIB)
- 7 Short harian (09:00 WIB) + 2 dokumenter (Senin & Kamis 10:00 WIB) dan 2 klip hook.
- Riset dalil + 2 referensi sejarah; kurasi aset grafis/font khat/palet/tekstur.
- Simpan ke rencana-tayang-mingguan.md dan laporkan tabel ke chat.

## 10. Catatan Operasional
- Model default bot YouTubeGrowth saat ini: opencode/glm-5.3-flash-free pada opencodeGo (per 19 Nov bermasalah: "model not found" — perlu diganti, mis. agnes/agnes-2.5-flash sesuai standar tim).
- Kuota YouTube Data API harianreset ±15:00 WIB; bila habis, pekerjaan dijadwalkan ulang via routine sekali-jalan.
- File video lokal persisten di workspace bot: .../3bbb857a-0cdc-4849-898b-a135cf3bf78c/produksi/ dan .../ks19-doa-keluar-rumah.mp4.
