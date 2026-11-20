# Changelog — zbmaus-vela-eco

Semua perubahan ekosistem OpenMausBot (zbmaus) dicatat di bawah ini.

---

## 2026-11-21

### Sinkronisasi Harian (routine otomatis pukul 23:00 WIB)
- **bots.json** diperbarui: model YouTubeGrowth Kitab Surgawi dikoreksi dari `opencode/glm-5.3-flash-free` → `opencode/hy4-flash-free` (opencodeGo), sesuai standar tim General. Versi tetap v1.1.0, updated_at=2026-11-21.
- **triggers.json** dinaikkan ke v1.5.0: dua routine sekali-jalan (Upload EP-003 id `2f8d2271`, tambah Short ke playlist id `5630e281`) dinonaktifkan (`enabled=false`) karena sudah selesai dan jadwalnya lewat. Total routine tercatat 14 (12 enabled, 2 disabled).
- **Soul files** dikoreksi model tidak sesuai:
  - `asn-admin.md`: `nous/reflection/beam-1.0-501b-a23b:free` → `agnes/agnes-2.5-flash`
  - `zbmaus-humanoid-vercel.md`: `nous/reflection/beam-1.0-501b-a23b:free` → `agnes/agnes-2.5-flash`
  - `youtubegrowth-kitab-surgawi.md`: `opencode/glm-5.3-flash-free` → `opencode/hy4-flash-free`
  - `nova.md`: `opencode/beam-free` → `agnes/agnes-2.5-flash`
- Routine berjalan normal hari ini: Monitoring Harian ✅, Cross-post FB&IG NOTHING NEW ✅, Balasan Komentar ✅, Evaluasi Kualitas ✅. Morning Brief Nova gagal ke-4x (rate limit API gratis); perlu upgrade Token Plan atau tunggu reset kuota.
- Routine Cek perubahan GitHub harian gagal ke-4x (tool failures) pada 20 Nov; failure streak 4.

### Audit & Sanitasi
- Repo publik eco 100% bebas kredensial sensitif (token API, password, cookie, private key, env). Tidak ada perubahan struktur folder.
- Kredensial dan `omb-state-*.json` dikecualikan dari sinkronisasi (tetap hanya di secrets).

---

## 2026-11-19

### Sinkronisasi Penuh (manual oleh ZB)
...

*File ini diperbarui oleh routine Sinkronisasi & Backup Harian Ekosistem zbmaus setiap pukul 23:00 WIB, dan sinkronisasi penuh manual bila diperlukan.*