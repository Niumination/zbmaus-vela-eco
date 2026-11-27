# Ekosistem zbmaus — Status Saat Ini

> Generated 28 November 2026. Sumber kebenaran: data live tool agents. Repo ini artefak turunan.

| Item | Jumlah | Keterangan |
|------|--------|------------|
| Bot | 8 | Semua aktif, department General |
| Routine/trigger | 17 | 15 enabled, 2 disabled |
| Skill | 4 | omb-bot-creation, omb-ecosystem-sync, omb-routine-scheduling, superpowers-workflow |
| App terhubung | 7 | GitHub, YouTube, Facebook, Instagram, Vercel, Kaggle, Boldsign |
| Room | 0 | Belum ada |
| Catatan tim | 13 | accepted |
| Repo zbmaus | 6 | eco, secrets, vela, asn-admin, zbmaus-humanoid, zbmaus-kitab-surgawi |

## Koreksi penting

- Versi 2.3.0 triggers.json salah menamai `b2e9a760` (sebenarnya bersih-bersih storage 03:00) dan `e71db9c1` (produksi Kamis 10:00). Sudah dikoreksi di v2.4.0.
- `bots.json` v1.4.0 memuat ID buatan; v1.5.0 memakai UUID asli dari data live.
- `team_memory` v1.2.0 memuat kunci buatan; v1.3.0 memakai 13 kunci asli dari `session_search scope=team`.

## Tool yang bermasalah

- `session_search`: butuh query atau `since`; limit maksimal 25.
- `COMPOSIO_SEARCH_TOOLS`: maksimal 7 query; argumen `queries` berupa objek `{use_case}`.
- Endpoint app-event/template tidak tersedia di sesi ini.
- Hasil `list_triggers` YouTube besar; dibaca bertahap via `tool_result_read`.
- Dua percobaan commit awal gagal karena escaping JS; diatasi dengan payload gzip+base64.
