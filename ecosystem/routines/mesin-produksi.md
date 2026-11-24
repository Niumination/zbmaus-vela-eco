# Mesin Produksi Kitab Surgawi (ZB - inv. 24 Nov 2026)

Ringkasan mesin produksi seri Dokumenter Islami & Reels untuk channel YouTube @kitabsurgawi-1357 (agent YouTubeGrowth Kitab Surgawi, id 3bbb857a-0cdc-4849-898b-a135cf3bf78c).

## Produksi video utama (Dokumenter Islami)
- Engine utama: `produksi/engine-v3/` (rendering + QC gate `qc_gate.py` - LUFS -16, true peak, coverage, variasi frame, minimal 4 foto nyata, pass: true wajib sebelum upload).
- Encode: ffmpeg 2-pass; bitrate video (kbps) = `target_bytes*8/dur/1000 - 74`; preset pass 2 harus sama dengan pass 1.
- Sound/voice: backend `edge` (`voice_backend="edge"` wajib - backend eksperimen chirp3/azure/chatterbox/voxcpm2 masih ditahan per instruksi user 21 Nov 2026).

## Short harian (reel)
- Jadwal: 09:00 WIB (weekly). Topik dari rencana tayang mingguan; variasi visual otomatis (motion graphic, tipografi kinetik, elemen 3D/layered parallax).
- Hook: pinned komentar dengan tautan video utama; penyusunan jadwal mingguan via rutinitas Senin 07:00.

## Dokumenter Islami (2x seminggu)
- Tayang: Senin & Kamis 10:00 WIB (cron 0 10 * * 1,4 Asia/Jakarta). Episodes karena Nov 2026: EP-003 Rempah & Sutra (tayang lebih awal 22 Nov), EP-004 & EP-005 (tayang 23-29 Nov).
- Opsi distribusi via helper OAuth lokal /opt/yt-oauth/ (yt-upload.py, yt-manage.py, yt-playlist-add.py) - token Composio YouTube sudah ditiadakan (403) sejak 19 Nov 2026.

## Pengawas Kualitas
- Rutinitas Penjaga Kualitas (id 4fbc7fa4-03ca-4fa1, cron 45 15 * * * Asia/Jakarta, continuity: true) membandingkan perubahan mesin harian dari laporan Evaluasi 15:30; batalkan perubahan tanpa bukti lebih baik di `memory/kitab-surgawi-kualitas.md`; rincian di `CATATAN-MESIN-PRODUKSI.md`.

## Sumber fitur teknis
- Media hosting untuk upload: file Hosting (uguu.se/dl/* sudah tidak tayang - fallback uguu.se via curl -F "files[]=@f.mp4" https://uguu.se/upload?output=text -> d.uguu.se/<file>.mp4; verifikasi md5 sebelum upload).
- Rute upload: file (local/s3key) -> BOLDSIGN_FILE_UPLOAD (base64) -> s3key -> YOUTUBE_MULTIPART_UPLOAD_VIDEO.
- Manajemen playlist: Dokumenter Islami & Amalan 1 Menit via `yt-manage.py`.
- Cross-post FB & IG: video native vertikal ke Facebook Page 1467846356417352 & IG Reels @zhall_abstract otomatis tiap 3 jam; caption tanpa link keluar, link YouTube selalu di komentar pertama.
