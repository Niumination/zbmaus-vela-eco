# Monitoring & Produksi Postingan Harian Kitab Surgawi

**Bot**: YouTubeGrowth Kitab Surgawi
**ID**: `aa2deb00-5c6a-4d99-b1b4-4e65231c0c5b`
**Kind**: schedule (cron)
**Cron**: `0 9 * * *` Asia/Jakarta
**Enabled**: true
**Continuity**: true
**Timeout**: 240 menit

## Instructions

PENTING (19 Nov 2026): Token Composio YouTube SUDAH DI-REVOKE (403) — jangan pakai tool YOUTUBE_* / Composio lagi. Semua operasi YouTube wajib lewat helper OAuth lokal. Baca panduan lengkap: /home/agentuser/.openmausbot-ombnew/workspaces/3bbb857a-0cdc-4849-898b-a135cf3bf78c/memory/yt-oauth-helpers.md . Semua perintah pakai sudo -n.

Tugas harian channel Kitab Surgawi (@kitabsurgawi-1357): cek performa, PRODUKSI 1 konten dakwah baru, unggah sampai TAYANG, laporkan.

LANGKAH:
1) PELAJARAN KUALITAS: baca memory/kitab-surgawi-kualitas.md, terapkan pelajaran terakhir.
2) CEK PERFORMA: yt-manage.py →统计 semua video. JANGAN pakai Composio YouTube.
3) SUSUN MATERI: 1 Short dakwah amalan 30-60 detik. Topik dari pola terbukti. Judul hook CTR>5%, deskripsi SEO + 15-20 tag.
4) PRODUKSI: render vertikal 720x1280 per skill high-retention-video-production. Suara edge-tts id-ID.
5) UNGGAH via helper OAuth lokal: sudo -n /opt/yt-oauth/yt-upload.py FILE.mp4 "Judul" "Deskripsi" "tag1,tag2,..."
6) THUMBNAIL untuk non-Shorts. PLAYLIST: tambah ke playlist yang sesuai.
7) LAPORKAN: videoId, link, playlist, view awal, 1 pelajaran kualitas.

Catatan: quota YouTube reset ±15:00 WIB; kalo kosong, dijadwalkan ulang.