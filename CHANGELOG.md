# CHANGELOG — zbmaus-vela-eco

## 28 November 2026 — Koreksi sinkronisasi harian (v1.5.0 / v2.4.0)

Seteco ter-push, verifikasi menemukan ketidaksesuaian dengan data live. Koreksi berikut di-commit sebelum backup secrets:

- `bots.json` v1.5.0: seluruh ID bot diganti UUID asli dari `agents_list_bots`; nama lengkap YouTubeGrowth Kitab Surgawi; department General; 8 bot aktif.
- `triggers.json` v2.4.0: 17 trigger dengan UUID penuh. `b2e9a760` = bersih-bersih storage harian 03:00 (bukan dokumenter); `e71db9c1` = produksi dokumenter Kamis 10:00 (bukan riset Senin); riset Senin = `61f30e61` 07:00. Stats 17 total / 15 enabled / 2 disabled.
- `team_memory` v1.3.0: 13 kunci asli dari `session_search scope=team`, menggantikan kunci buatan pada v1.2.0.
- Instruksi routine diperbaiki: `15714d6a` cross-post FB/IG, `61f30e61` riset mingguan, `aa2deb00` monitoring harian, `5af330ca` arsip disabled, `b2e9a760` storage cleanup, `e71db9c1` produksi Kamis.
- Instruksi baru untuk routine ZB/Nova/humanoid: `e4394ce5`, `a008e49f`, `e0c1a6d9`, `c80996f3`, `04522463`, `3bdb8754`, `6a5fd5fa`, `35244f11`, `4fbc7fa4`, `arsip-once`.
- `mesin-produksi.md` & `CATATAN-MESIN-PRODUKSI.md`: aturan produksi dikoreksi.
- `connected_apps.json`: Boldsign ditambahkan; catatan token YouTube Composio revoked.

## 28 November 2026 — Sinkronisasi awal (v1.4.0 / v2.3.0)

- Inventarisasi 8 bot, 17 routine, 4 skill, 13 catatan tim, 5+ repo zbmaus, mesin produksi Kitab Surgawi.
- Commit eco: 8f5a94b, d9a8631, 7b2996c.
- Audit kredensial eco: PASS.
