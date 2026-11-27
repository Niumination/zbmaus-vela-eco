# Ekosistem zbmaus — Status Saat Ini

> Generated 28 November 2026 — Sinkronisasi & Backup Harian Ekosistem zbmaus.
> Sumber kebenaran: data live tool agents. Repo ini adalah artefak turunan.

## Ringkasan

| Item | Jumlah | Keterangan |
|------|--------|------------|
| Bot | 8 | Semua aktif |
| Routine/trigger | 17 | 14 enabled, 3 disabled |
| Skill | 4 | Semua enabled |
| App terhubung | 6 | GitHub, YouTube, Facebook, Instagram, Vercel, Kaggle |
| Room | 0 | Belum ada |
| Catatan tim | 13 | Semua accepted |
| Repo zbmaus | 5 | Termasuk eco & secrets |

## Repositori zbmaus

1. `Niumination/zbmaus-vela-eco` — artefak publik (repo ini).
2. `Niumination/zbmaus-vela-secrets` — kredensial & state privat.
3. `Niumination/zbmaus-agent-studio`
4. `Niumination/zbmaus-content-lab`
5. `Niumination/zbmaus-infra`

Repo di luar zbmaus (LightVela, mirai, hermes, apex, ecosystem-config) tidak disentuh.

## Tool yang bermasalah

- `session_search`: limit harus <= 25 (berhasil setelah koreksi).
- `COMPOSIO_SEARCH_TOOLS`: maksimal 7 query per panggilan.
- Endpoint app-event/template tidak tersedia di sesi ini.
- Routine `5af330ca` tidak bisa dihapus via tool yang tersedia; dinonaktifkan dengan mengubah status dan instruksi.
