# Changelog — zbmaus-vela-eco

Semua perubahan ekosistem OpenMausBot (zbmaus) dicatat di bawah ini.

---

## 2026-11-21

### Sinkronisasi Harian (routine otomatis pukul 23:00 WIB)
- **bots.json** diperbarui: model YouTubeGrowth Kitab Surgawi dikoreksi dari `opencode/glm-5.3-flash-free` → `opencode/hy4-flash-free` (opencodeGo), sesuai standar tim General.
- **triggers.json** dinaikkan ke v1.5.0 (struktur berubah): instruksi lengkap routine dipisahkan ke `ecosystem/routines/instructions/<id>.md` agar menghindari batasan ukuran commit. File ini hanya indeks ringkas 14 routine (12 enabled, 2 disabled).
- **Soul files** dikoreksi model tidak sesuai:
  - `asn-admin.md`: `nous/reflection/beam-1.0-501b-a23b:free` → `agnes/agnes-2.5-flash`
  - `zbmaus-humanoid-vercel.md`: `nous/reflection/beam-1.0-501b-a23b:free` → `agnes/agnes-2.5-flash`
  - `youtubegrowth-kitab-surgawi.md`: `opencode/glm-5.3-flash-free` → `opencode/hy4-flash-free`
  - `nova.md`: `opencode/beam-free` → `agnes/agnes-2.5-flash`
- Routine berjalan normal hari ini: Monitoring Harian ✅, Cross-post FB&IG NOTHING NEW ✅, Balasan Komentar ✅, Evaluasi Kualitas ✅.
- Morning Brief Nova gagal ke-4x berturut (rate limit agnes/agnes-2.5-flash API gratis); perlu upgrade Token Plan.
- Routine Cek GitHub harian gagal ke-4x (tool failures) pada 20 Nov; failure streak 4.

### Audit & Sanitasi
- Repo publik eco 100% bebas kredensial sensitif.
- Full routine instructions kini terpisah per file MD di `ecosystem/routines/instructions/`.
- Kredensial dan `omb-state-*.json` tetap hanya di secrets repo.

### Commit History (eco)
- `e5e18b28` — bots.json model corrections
- `ee53c114` — triggers.json v1.5.0 compact index
- `715fdca5` — CHANGELOG.md Nov 21 entry
- `77e3ee49` — asn-admin.md model fix
- `3c2bd97a` — zbmaus-humanoid-vercel.md model fix
- `73866669` — youtubegrowth-kitab-surgawi.md model fix
- `05453068` — nova.md model fix
- `ce050c68` — e4394ce5 instruction file
- `a197adbfe` — aa2deb00 instruction file
- `107f6b64` — 6a5fd5fa instruction file
- `43b323de` — 35244f11 instruction file
- `1069c34d` — 3bdb8754 instruction file
- `2481f4b2` — 15714d6a instruction file
- `68978fa7` — 61f30e61 instruction file
- `875657df` — 5af330ca instruction file
- `7258c221` — a008e49f instruction file
- `6a094e55` — e0c1a6d9 instruction file
- `9a5ae595` — c80996f3 instruction file
- `0b5f1658` — 04522463 instruction file
- `b58dd32a` — 2f8d2271 archived instruction
- `82366be4` — 5630e281 archived instruction

---

## 2026-11-19

### Sinkronisasi Penuh (manual oleh ZB)
...

*File ini diperbarui oleh routine Sinkronisasi & Backup Harian Ekosistem zbmaus setiap pukul 23:00 WIB, dan sinkronisasi penuh manual bila diperlukan.*