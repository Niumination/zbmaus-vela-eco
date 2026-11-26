# CATATAN-MESIN-PRODUKSI — Kitab Surgawi
Update: 25 Nov 2026. Dibaca oleh routine produksi harian 09:00 WIB.

## STATUS: mesin aktif = v3
**Short harian wajib memakai** `produksi/engine-v3/`.
Panduan lengkap + alur wajib + bukti perbandingan:
`produksi/engine-v3/PANDUAN-MESIN-V3.md`

```
from render_short_v3 import build
result = build(spec, workdir)   # otomatis menjalankan QC GATE
# bila QC FAIL -> RuntimeError, JANGAN upload
```

Contoh spec siap pakai: `produksi/2026-11-22-istighfar-100x/build.py`.
Hasil uji 21 Nov: gate menolak Short 21 Nov (18 temuan) dan meloloskan
kandidat 22 Nov (0 temuan, -16,1 LUFS, foto nyata, glyph bersih).

## engine-v2 — DITUNDA untuk Short
`produksi/engine-v2/` (`visual_fx.py`, `sfx_generator.duck_mix`, `ambient_pad.py`,
`cinematic_luts.py`, `hook_titles.py`, `thumbnail_studio.py`) tidak dipakai untuk
Short harian mulai 21 Nov 2026. Penyebab: kombinasi background sintetis,
`noise`/grain, reverb berlapis pada klip Arab, dan sidechain `threshold=0,02
ratio=8` menurunkan kualitas secara terukur (lihat `qc_21nov.json`).
Modul ini masih boleh dipakai untuk dokumenter/eksperimen dengan QC manual.
`arabic_narration.py` dari v2 **tetap dipakai** v3 untuk `recite_ayah()`.

## Aturan yang kini ditegakkan mesin (bukan hanya dicatat)
- QC gate sebelum upload; without `"pass": true` tidak ada upload.
- ﷺ dan emoji tidak masuk burn-in; ayat Qur'an pakai reciter manusia.
- Minimal 4 foto nyata; durasi 42–62 dtk; caption ≤32 karakter/baris.
- Audio final `loudnorm I=-16 TP=-1.5 LRA=11`; tanpa reverb berlapis.
- Evaluasi 15:30 wajib menghasilkan perubahan kode/modul, bukan sekadar catatan.

## Tambahan 21 Nov — pelajaran voice MATA dari GitHub user
Voice MATA = suara manusia, dibaca natural, direkam per-adegan via OBS; TANPA
modul TTS di repo. Diadopsi ke v3: angka di narasi dieja (`100x` → `seratus kali`),
rate positif dilarang (jangan percepat), cache per-segmen = rekam ulang scene
tertentu saja. Detail + tautan sumber: `produksi/engine-v3/PANDUAN-MESIN-V3.md`.

## Tambahan 21 Nov (sesi 2) — humanizer & aset
- Pustaka 12 foto bertema: `produksi/engine-v3/assets/photos/` + CREDITS.md. Jangan pakai
  lagi 5 foto lama yang berulang; rotasi dari pustaka ini.
- Tiap segmen dinormalisasi ke −18 LUFS; gate menolak ketimpangan Arab vs narasi >2 LU.
- Jeda nafas bervariasi 0,22–0,38 dtk; caption Arab wajib warna ASS `&Hxxxxxxxx`.

## KEPUTUSAN 21 Nov 14:03 — tahan eksperimen, jaga yang sudah bagus
- Semua perbaikan v3 DISIMPAN & dipakai: renderer v3, QC gate, 12 foto bertema, normalisasi −18 LUFS, jeda nafas bervariasi, aturan MATA (angka dieja, rate positif dilarang, cache per-segmen), ayat Qur'an reciter manusia.
- Eksperimen backend suara (chirp3/azure/chatterbox/voxcpm2) DITAHAN: modul tetap ada di `engine-v3/voice_backends.py`, tapi Short harian tetap `voice_backend="edge"` sampai user memberi aba-aba.
- Pengawasan harian: setiap evaluasi 15:30 wajib satu perbaikan kecil dengan pembuktian `qc_gate.py` sebelum/sesudah. Gagal membuktikan perbaikan = perubahan dibatalkan.
- Routine lama masih memuat instruksi eksplorasi efek (ducking/riser/ambient) yang dulu merusak Short — abaikan bagian itu; ikuti aturan di atas.

## Evaluasi 21 Nov 15:30 — perbaikan kecil yang DITERAPKAN: gate keragaman foto
- Modul baru: `produksi/engine-v3/visual_variety.py` (dHash 8x8 / 64 bit). Dipanggil otomatis dari `qc_gate.py` lewat `_check_photo_variety()` — tidak mengubah renderer, TTS, atau efek apa pun.
- Aturan baru: jarak dHash tiap pasangan `scene_photos` wajib **>= 10/64 bit**. Foto yang cuma beda nama tapi identik/near-duplicate ⇒ QC FAIL, upload dibatalkan.
- Kalibrasi & bukti: `produksi/engine-v3/qc_variety_21nov.json`. Kandidat 22 Nov (6 foto): min **23**, rata-rata **30,3**, PASS, metrik LUFS −16,22 / TP −1,44 tidak berubah. Kontrol `foto0.jpg` x4: min **0**, 6 pasangan duplikat, **FAIL**.
- Uji regresi: `py_compile` qc_gate/visual_variety/render_short_v3 OK; `voice_backends.py --selftest` PASS (5 backend).
- Cara pakai cepat: `python3 produksi/engine-v3/visual_variety.py --manifest <manifest.json>` (exit 0 = aman).
- Catatan evaluasi konten 21 Nov: dilembar ke `memory/kitab-surgawi-kualitas.md`. Insight utama: dua Short baru menembus ~130–140 views/jam — judul "Jangan … Tanpa/Nlupa … angka + janji" menyumbang CTR, bukan efek visual; tetap jaga QC untuk retensi.

## Tambahan 21 Nov (sesi 4) — adopsi Short referensi uDl7tGCEUN4
- Analisa lengkap: `ANALISA-SHORT-REFERENSI-UDL7.md`. Referensi = Short 61 dtk @ngotret4math tentang Al-Khawarizmi (499 views / 12 likes, 14 Nov 2026).
- Diadopsi: hook "Pernah pakai X? Tokohnya Muslim", reveal nama+abad ≤10 dtk, bukti asal kata, jembatan manuskrip→teknologi, typografi emas. TIDAK diadopsi: naskah/gambar/thumbnail orang lain, judul polos tanpa angka, 21 hashtag.
- Modul baru `produksi/engine-v3/series_tokoh.py` (templat 8 beat, 3 tokoh) + `build_tokoh_assets.py` (9 foto Wikimedia berkredit di `assets/photos/tokoh/`). Mesin v3, voice `edge`, QC gate tidak dilonggarkan.
- Kandidat `produksi/2026-11-23-alkhawarizmi/final.mp4`: 55,09 dtk, QC PASS, LUFS −15,99, TP −1,38, coverage 97,6%, dHash min 23/64. **Belum di-upload** (tunggu aba-aba).
- untuk hari biasa, pakai judul "Jangan [waktu] Tanpa [amalan] 7x! [janji]" seperti rencana 15:30; seri tokoh adalah jalur tambahan, bukan pengganti jadwal harian.

## Koreksi 21 Nov 23:20 — mode SLIDE EXPLAINER
- User menunjukkan isi video referensi adalah **gambar AI bergaya slide PowerPoint dengan animasi**, bukan satu foto. Saya unduh video 720p dan ekstrak frame tiap 3 dtk: benar — tiap beat punya ilustrasi/headline/panel/chip berbeda (TAHU KAH KAMU?, AL-JABR WAL-MUQABALA, ALGORITMA + flowchart, WARISAN AL-KHAWARIZMI + chip AI).
- Modul baru `produksi/engine-v3/slide_mode.py`: grade foto jadi latar slide + overlay ASS headline/sub/chip animasi. TIDAK mengubah renderer, audio, atau QC gate. Latar otomatis pakai `assets/photos/tokoh/ai/slide0..5.jpg` jika ada generator gambar terhubung; saat ini masih foto Wikimedia.
- Kandidat `produksi/2026-11-23-alkhawarizmi-slide/final_slide.mp4`: 55,09 dtk, QC dasar PASS + QC overlay PASS (0 temuan), LUFS −15,99 / TP −1,38. Perbaikan sebelum/sesudah: headline 56→46 px dan dipendekkan ≤18 karakter, sub 28→25 px ≤34 karakter, chip 26→23 px di MarginV 206 — menghilangkan tabrakan teks di kontak sheet. Belum di-upload.

## Riset 21 Nov 23:50 — generator gambar AI gratis (komersial)
- Laporan: `RISET-GAMBAR-AI-GRATIS.md`. Modul: `produksi/engine-v3/image_gen_free.py` + opsi `--kaggle-notebook`.
- Pilihan utama **Cloudflare Workers AI + FLUX.1 schnell**: Apache-2.0 (boleh komersial), gratis 10.000 Neuron/hari ≈ ±150 gambar/hari, zero data retention. Butuh akun CF gratis + API token (belum ada → belum bisa generate massal).
- Cadangan: notebook Kaggle GPU gratis (P100/T4×2, 12 jam/sesi, 20 GB) — akun sudah terhubung.
- Pollinations tanpa kunci teruji 1 gambar sukses (720×1280, 52 KB) lalu HTTP 402; watermark dipangkas adapter. Tidak untuk produksi.
- Ditolak: FLUX.1 dev (non-komersial), HF Inference (berbayar), Gemini (SynthID + data dipakai di tier gratis).
- Adapter menulis `assets/photos/tokoh/ai/slide0..5.jpg` yang otomatis dipakai `slide_mode.py`; belum ada file di sana, jadi kandidat slide masih memakai foto Wikimedia tergrade.

## Evaluasi 22 Nov 15:30 — perbaikan kecil yang DITERAPKAN: gate tema foto Arab
- Modul baru `produksi/engine-v3/thematic_fit.py`, dipanggil otomatis dari `qc_gate.py` lewat `_check_thematic_fit()`. Tidak menyentuh renderer/TTS/audio/efek.
- Aturan baru: scene yang memuat segmen `arabic=True` atau `kind=="quran"` WAJIB memakai foto khusyuk (mushaf, kaligrafi, masjid, kabah, seni islami, sajadah). Foto `11-ramadan.jpg` (iftar), `05-subuh.jpg`, `06-malam.jpg`, `12-gurun.jpg` ⇒ QC FAIL, upload dibatalkan.
- Identitas foto ditebak dari dHash 8x8 terhadap 12 foto di `assets/photos/` (ambang kecocokan 12/64), jadi tetap bekerja walau file disalin jadi `foto0..foto5.jpg`.
- Manifest kini menyimpan `scenes` (photo + segment ids) — `render_short_v3.py` baris ~447. Manifest lama tanpa `scenes` dilewati (kompatibel mundur).
- Bukti sebelum/sesudah: `produksi/2026-11-22-doa-wudhu/` (foto iftar pada doa Arab) QC **FAIL** 1 temuan; `produksi/2026-11-22-doa-wudhu-thematic/` (foto `07-kaligrafi.jpg`) QC **PASS** 0 temuan. LUFS −16,13 / TP −1,03 / durasi 58,8 dtk / coverage 97,8% / Arab–narasi 0,1 LU identik; dHash min 23/64, mean 32,6→31,9. `voice_backend="edge"` tetap, selftest 5 backend PASS. Kandidat render ulang untuk pembuktian, BUKAN untuk di-upload.
- Pemakaian cepat: `python3 produksi/engine-v3/thematic_fit.py --manifest MANIFEST.json` (exit 0 = aman). `thematic_fit.py --suggest SPEC.json` memberi usulan penukaran foto.
- Kesimpulan evaluasi konten: Short doa wudhu yC8mys3PJj4 = starter tercepat channel (~202 views/jam pada jam ke-6); subscriber 65→76 (+17%) dalam 24 jam. Tiga Short terbaru masih 0 komentar → besok tambah pertanyaan konkret di CTA. Detail: `memory/kitab-surgawi-kualitas.md`.

## Evaluasi 23 Nov 15:30 — perbaikan kecil yang DITERAPKAN: gate CTA interaksi
- Modul baru: `produksi/engine-v3/cta_gate.py`, dipanggil otomatis dari `qc_gate.py` lewat `_check_cta()` (jalur `render_short_v3.build()` → `run_qc`, baris 454) — TIDAK menyentuh renderer, TTS, warna, atau efek.
- Aturan: cue CTA terakhir wajib `?` + pilihan murah (≥2 angka dengan `/`, A/B, atau "atau") + kata "komentar"/"tulis" + `AAMIIN` + `subscribe`, dengan hold ≥5,0 dtk diukur sampai video benar-benar berakhir (bukan sekadar end-time ASS).
- Alasan data: 4 Short terbaru 1.2-1.3K views tapi 0 komentar; antrean `heldForReview` juga 0 → bukan komentar tersembunyi. Pertanyaan terbuka yang sudah dipakai 23 Nov ("Amalan mana yang kamu lewatkan?") masih 0, jadi need pilihan ber-angka yang murah dijawab.
- Bukti sebelum/sesudah (`produksi/engine-v3/qc_cta_23nov.json`, `produksi/2026-11-23-cta-gate-test/`):
  - doa wudhu 22 Nov → FAIL, 3 temuan (tanpa `?`, tanpa pilihan, tanpa instruksi komentar).
  - Al-Ikhlas 23 Nov → FAIL, 1 temuan (tanpa pilihan) — ini yang baru saja tayang, tidak diubah/di-upload ulang.
  - CTA baru "1 Wudhu / 2 Shalat / 3 Dzikir? Tulis nomornya di komentar!" → PASS, 0 temuan, hold 7,63 dtk.
  - QC penuh video uji: FAIL→PASS; LUFS −16,17→−16,16, TP −1,47→−1,36, durasi 59,0→57,27 dtk, coverage 97,6%→100%, dHash min 15/64 tetap, 0 near-duplicate.
- Uji regresi: `py_compile` cta_gate + qc_gate OK. Aturan penjaga dipatuhi: `voice_backend="edge"` tetap, tidak ada backend suara/noise/reverb/ducking baru yang diaktifkan. Video uji HANYA pembuktian, tidak di-upload.
- Pemakaian cepat: `python3 produksi/engine-v3/cta_gate.py SUBS.ass [DURASI]` (exit 0 = aman). Saat menulis naskah besok, CTA wajib berbentuk "Ketik AAMIIN + subscribe. 1 X / 2 Y / 3 Z? Tulis nomornya di komentar!".
- Evaluasi konten: channel 83 subs (+7/+9,2% per hari); starter tercepat hari ini Al-Ikhlas 894 views/6,3 jam (~141/jam). Detail: `memory/kitab-surgawi-kualitas.md`.

## Evaluasi 24 Nov 15:30 — perbaikan kecil yang DITERAPKAN: gate dalil terlihat
- Modul baru `produksi/engine-v3/dalil_gate.py`, dipanggil otomatis dari `qc_gate.py` lewat `_check_dalil()` (jalur `render_short_v3.build()` → `run_qc()`) — TIDAK menyentuh renderer, TTS, warna, atau efek.
- Alasan data: Short doa makan MZorTpAPP6Y dapat komentar PERTAMA setelah 5 Short 0 komentar (950 views/6,3 jam, ~150/jam), tapi isinya meragukan klaim "setan muntah" — dalil hanya ada di deskripsi, tidak di frame. CTA bernomor memancing interaksi; klaim gaib tanpa sumber di layar memancing keraguan.
- Aturan: setiap cue dengan klaim gaib ber-efek konkret (`setan/syaitan/jin/iblis` + `ikut makan/muntah/lari/pergi/terusir/menggoda/mengganggu`) WAJIB memuat penanda sumber (`HR.`, `riwayat`, `Riyad`, `Bukhari`, `Muslim`, `Abu Dawud`, `An-Nasa'i`, `Tirmidzi`, `Q.S.`, `sunnah.com`, dll.) pada cue itu atau cue bersebelahan. Judul yang memuat klaim ditandai `title_has_claim` (advisory, bukan blocker — judul tidak dibakar ke video).
- Bukti sebelum/sesudah (`produksi/2026-11-24-doa-makan/` vs `produksi/2026-11-24-doa-makan-dalil/`):
  - SEBELUM: QC **FAIL**, 3 temuan dalil (klaim di 0,3s / 32,3s / 43,1s tanpa sumber di subtitle), semua check lain lolos.
  - SESUDAH: caption hook ditambah `\N(HR. Abu Dawud)`, caption kisah ditambah `\N(HR. Abu Dawud & An-Nasa'i)`, render ulang dari `visual.mp4` + `audio/final.m4a` → QC **PASS**, 0 temuan, 3 klaim semuanya bertemu sumber (`source: HR`).
  - Metrik IDENTIK: LUFS −16,09; TP −1,40; durasi 59,2 dtk; coverage 97,8%; dHash min 23/64; Arab–narasi 0,0 LU; CTA hold 8,64 dtk. Uji regresi: doa wudhu & Al-Ikhlas tetap PASS (0 klaim terdeteksi), `py_compile` OK, selftest 5 backend PASS.
- Video uji HANYA pembuktian, TIDAK di-upload. Aturan penjaga dipatuhi: `voice_backend="edge"` tetap, chirp3/azure/chatterbox/voxcpm2 tidak diaktifkan, tanpa noise/reverb berlapis/ducking agresif.
- Pemakaian cepat: `python3 produksi/engine-v3/dalil_gate.py SUBS.ass [MANIFEST.json]` (exit 0 = aman). Saat menulis naskah besok: klaim gaib wajib disertai `(HR. ...)` di caption scene yang sama/bersebelahan, dan pinned komentar menjawab sumber sebelum bertanya pilihan nomor.
- Evaluasi konten: channel 86 subs (+3/+3,6% per hari); agregat 26 video = 17.812 views. Detail: `memory/kitab-surgawi-kualitas.md`.

## 25 Nov 2026 — opsi A ditolak, opsi B: renderer dokumenter tanpa VPS
- Opsi A (buka backend suara) DITOLAK terukur: Azure/Chirp3 tanpa kredensial; Chatterbox torch butuh ≈5,3 GB vs 3,8 GB free; Chatterbox GGUF+CrispASR jalan tapi >10 mnt per kalimat di CPU 2-core. Modul `voice_backends.py` kini 6 backend dengan penanda DITOLAK untuk `chatterbox_gguf`; model 1,5 GB dihapus. `voice_backend="edge"` tidak berubah, tidak ada upload.
- Opsi B SELESAI: modul baru `produksi/engine-doc/render_doc_v1.py` (ffmpeg+PIL+ASS, TANPA skia/GPU/VPS/Wikimedia) menggantikan `engine.py`+skia untuk dokumenter. Pakai 18 foto lokal berkredit, diagram vektor, tipografi emas, Ken Burns, xfade, pad 0,05, loudnorm, QC gate mandiri.
- Cara pakai: `python3 produksi/engine-doc/render_doc_v1.py produksi/2026-11-21-ep004-al-biruni/beats.json <WORKDIR>`. Spec beat ada di `beats.json` (18 beat, narasi + typed + photo/diagram + motion + keywords).
- Hasil EP-004: `produksi/2026-11-21-ep004-al-biruni/render-v2/final.mp4` — 154,52 dtk, 1280×720/30, 40 MB, QC PASS 0 temuan (LUFS −16,24; TP −1,33; jeda 0,0 dtk; coverage 95,8%; 18 scene; 4 frame mean 27–84/std 42–69).
- Perbaikan kecil yang DITERAPKAN: render v1 lolos QC otomatis TAPI pemeriksaan 4 frame manual menemukan badge tanggal di kiri-atas menimpa brand baris atas. Brand dipindah ke kanan (ASS Alignment 9, font 22, MarginR 55), badge PIL turun y=52→96 & font 46→40. Render v2 QC PASS, metrik audio identik (LUFS −16,25→−16,24; TP −1,35→−1,33), tidak ada tabrakan teks (`preview2.jpg`).
- Video final BELUM di-upload — disiapkan untuk slot dokumenter Kamis 10:00 WIB + 2 Short potongan ber-hook tahun+tempat+angka. Laporan lengkap: `LAPORAN-OPSI-AB-25NOV.md`.

## Evaluasi 25 Nov 15:30 — perbaikan kecil yang DITERAPKAN: hook gate + pemotong Short vertikal
- **Akses YouTube lokal diperbaiki.** `yt-manage.py --videos` kena HTTP 400 karena `videos.list` tidak lagi menerima filter `channelId`. Helper kini mengambil daftar video dari uploads playlist (`playlistItems`, 1 halaman) lalu statistik via `videos.list id=<50 id per batch>`. Backup: `/opt/yt-oauth/yt-manage.py.bak-20261125`. Statistik harian kembali berjalan: `sudo -n /opt/yt-oauth/yt-manage.py --videos > /tmp/yt-eval.json`.
- **Modul baru** `produksi/engine-doc/clip_vertical_v1.py` — memotong episode dokumenter menjadi Short vertikal 720x1280/30. Memakai scene JPG + audio per-beat dari `render_doc_v1.py` (edge-tts cache, TTS tidak diubah), latar blur + foto utama + tipografi emas, caption ASS 5 baris, CTA bernomor dengan slot 7,4 dtk, dan QC mandiri (resolusi, durasi 42-62 dtk, LUFS, true peak, jeda diam, 4 frame, coverage, CTA, HOOK GATE). Tidak menyentuh renderer v3 maupun QC gate v3.
- **Aturan hook gate:** 3 detik pertama wajib memuat tahun 4 digit/Masehi + tempat konkret (Kath, Khwarazm, Nandana, Indus, Bukhara, Ghazni, ...) + angka/ukuran (jari-jari, sudut, km, mengukur). Hook generik ditolak — revisi dari pelajaran lama bahwa klip dokumenter generik mati di feedShorts.
- **Cara pakai:**
  ```
  python3 produksi/engine-doc/clip_vertical_v1.py MANIFEST.json 0 6 WORKDIR \
    --scenes .../render-v2/scenes \
    --hook "Tahun 1000 Masehi, dari Kath: jari-jari Bumi diukur tanpa GPS" \
    --title "1000 M: Ukur Jari-jari Bumi Tanpa GPS! 🕌 #Shorts"
  # exit 0 = QC PASS; --hook dihapus/--generic = uji kontrol yang HARUS FAIL
  ```
- **Bukti sebelum/sesudah** (`produksi/2026-11-25-ep004-klip-{generik,hook}/qc_report.json`): generik QC **FAIL** 3 temuan hook; hook ber-angka QC **PASS** 0 temuan. Semua metrik lain identik: 60,87 dtk; LUFS −16,23; TP −1,39; jeda 0,0; coverage 0,84; frame mean 55-64 / std 50-59; CTA hold 7,41 dtk (lolos `cta_gate`). Kontak sheet: `.../klip-hook/contact-v2.jpg`.
- Perbaikan visual saat uji: hook auto-shrink 50→34 px agar 3 baris tidak terpotong; scene dipangkas 170 px atas supaya badge bawaan tidak dobel; frame ekor +7,6 dtk supaya CTA tidak menimpa narasi. `py_compile` OK, `voice_backend="edge"`, tidak ada eksperimen suara/efek, tidak ada upload.
- Kandidat siap: `produksi/2026-11-25-ep004-klip-hook/final.mp4` (60,87 dtk, judul "1000 M: Ukur Jari-jari Bumi Tanpa GPS!"). **Belum di-upload** — dipakai untuk potongan Short mendampingi EP-004 (slot Kamis 10:00 WIB) jika user memberi aba-aba.
- Evaluasi konten: channel 92 subs (+6/+7,0% per hari); starter tercepat cNzJHJY1j0k 1.025 views/6,4 jam (~161/jam); `commentCount` doa makan 1→6 setelah komentar takhrij dipasang. Detail: `memory/kitab-surgawi-kualitas.md`.

## Evaluasi 26 Nov 15:30 — perbaikan kecil yang DITERAPKAN: gate caption 3 detik pertama
- Modul `produksi/engine-doc/clip_vertical_v1.py` diperluas: fungsi baru `caption_check(subs, limit=3.0)` membaca caption ASS yang benar-benar muncul di 3 detik pertama (tag `{\...}` dibuang, `\N` jadi spasi) dan menolak caption generik. `qc_vertical()` kini menerima `caption_verdict`, menulis `checks.caption_hook` ke `qc_report.json`; `build()` memanggil `caption_check()` otomatis dan menyimpan `caption_3s` ke manifest. Backup: `clip_vertical_v1.py.bak-20261126-1530`. TIDAK menyentuh renderer v3, TTS, audio, warna, efek, atau klip yang sudah tayang.
- Alasan data: gate hook lama hanya memeriksa field `hook` di manifest, bukan teks yang dibaca penonton. Manifest ber-hook bagus + caption "Kisah seorang ilmuwan Muslim yang sangat pintar." tetap lolos QC — gate tidak mencerminkan layar.
- Aturan baru: caption 3 detik pertama wajib memuat MINIMAL SATU sinyal konkret — tahun 4 digit/Masehi/`abad ke`, tempat (Kath, Khwarazm, Nandana, Indus, Bukhara, ...), atau angka/ukuran (`jari-jari`, `radius`, `km`, `sudut`, `mengukur`, `N karya/judul/bahasa/usia`). Tiga sekalian tidak diwajibkan supaya klip yang sudah tayang tidak gugur.
- Bukti sebelum/sesudah (`produksi/2026-11-26-eval-hook-caption/qc_{old,new}-generic.json`, `qc_new-good.json`), memakai video `2026-11-26-ep004-klip-sains/final.mp4` yang sudah dirender:
  - SEBELUM (gate lama): hook bagus + caption generik → QC **PASS**, 0 temuan (bug).
  - SESUDAH (gate baru): hook bagus + caption generik → QC **FAIL**, 1 temuan `caption hook: caption 3 detik pertama generik ...`.
  - KONTROL: caption asli "Di abad ke-11 ... mengukur radius Bumi ..." → QC **PASS**, sinyal `tahun` + `angka/ukuran`.
  - Regresi: klip tokoh 26 Nov (`103 judul`, `100 karya`), klip hook 25 Nov, dan klip generik 25 Nov (tetap FAIL di hook gate karena hook generik) semuanya bersikap seperti semula.
  - Metrik IDENTIK di tiga uji: 60,80 dtk; LUFS −16,16; TP −1,71; jeda 0,0; coverage 0,84; 4 frame mean/std 55,6/46,8 · 52,4/47,9 · 63,4/53,5 · 54,5/60,9. `py_compile` OK.
- Cara pakai tidak berubah: `python3 produksi/engine-doc/clip_vertical_v1.py MANIFEST.json START END WORKDIR --scenes SCENEDIR --hook "..."`. Saat menulis naskah klip: 3 detik pertama narasi wajib menyebut tahun/abad ATAU tempat ATAU angka konkret — jangan hanya mengandalkan teks hook di gambar.
- Aturan penjaga dipatuhi: `voice_backend="edge"`, tidak ada backend suara/noise/reverb berlapis/ducking agresif yang diaktifkan, tidak ada upload. Perbaikan kecil besok: gate ini juga dipakai saat menulis naskah Short harian (cek 3 detik pertama `subs.ass` v3) agar caption generik tidak lolos hanya karena judulnya kuat.
- Evaluasi konten: subscriber 92→102 (+10/+10,9% per hari); Short FQ5res0u1Z8 888 views/6,5 jam (~137/jam); EP-004 0 views sementara 2 klipnya 108 & 65 views. Detail: `memory/kitab-surgawi-kualitas.md`.
