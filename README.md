# zbmaus-vela-eco

> **Repositori Sinkronisasi Ekosistem OpenMausBot (zbmaus)**  
> Snapshot terstruktur, transparan, dan lengkap untuk ekosistem OMB tanpa kredensial/rahasia apapun (*Zero-Credentials*).

---

## 🎯 Tujuan Repositori

Repositori ini menjembatani dan melengkapi dua repositori sebelumnya:
1. **`zbmaus-vela`** (Publik): instruksi instalasi, skrip deployment OS/VPS, unit systemd, dan panduan infrastruktur mentah.
2. **`zbmaus-vela-secrets`** (Privat): konfigurasi deployment, file env, kredensial, dan snapshot state tertentu.

### 🔍 Kesenjangan yang Diisi oleh `zbmaus-vela-eco`
- **Team Memory**: 13 catatan memori bersama yang krusial bagi seluruh agen OMB.
- **Roster & SOUL Bot Terkini**: data lengkap **8 bot** aktif, ID unik, alokasi model, deskripsi tupoksi, dan instruksi berdiri (SOUL).
- **Routines & Triggers Aktif**: rutinitas otomatis (sinkronisasi harian, pemantauan interval, morning brief, produksi Kitab Surgawi, dll).
- **Katalog Integrasi (Connected Apps)**: pemetaan aplikasi ekosistem (GitHub, Vercel, YouTube, Kaggle, BoldSign, dsb) tanpa token/kredensial.
- **Skills & Prosedur**: katalog kemampuan modular dan orkestrasi workflow subagen, termasuk `superpowers-workflow`.
- **Topik Memori Personal & Kebijakan**: preferensi bahasa, repositori kerja, dan aturan proyek ekosistem.

---

## 📂 Struktur Direktori

```text
zbmaus-vela-eco/
├── README.md                           # Dokumentasi utama dan panduan ekosistem
├── CHANGELOG.md                        # Riwayat perubahan ekosistem
├── ecosystem/
│   ├── bots.json                       # Roster lengkap 8 bot beserta metadata dan status model
│   ├── architecture/
│   │   └── overview.md                 # Arsitektur koordinasi General department & hierarki agen
│   ├── souls/                          # Instruksi berdiri (SOUL) tiap agen
│   │   ├── zb.md                       # Chief of Staff (MausBot)
│   │   ├── asn-admin.md                # Spesialis Mesin Administrasi ASN Diskominfo
│   │   ├── zbmaus-humanoid-vercel.md   # Asisten humanoid interaktif web Vercel
│   │   ├── youtubegrowth-kitab-surgawi.md # Spesialis pertumbuhan channel dakwah
│   │   ├── islamicedu-kids.md          # Spesialis edukasi Islam usia 2-4 tahun
│   │   ├── kaggle-qwen.md              # Asisten inferensi ringan Kaggle T4 GPU
│   │   ├── nova.md                     # Integrator tupoksi baru ekosistem
│   │   └── superpowers-engineer.md     # Spesialis metodologi engineering (Superpowers)
│   ├── memory/
│   │   ├── team_memory.json            # 13 catatan memori bersama (data terstruktur)
│   │   ├── team_memory.md              # Narasi dan konteks memori tim
│   │   └── zb_memory.md                # Long-term memory & topic notes
│   ├── routines/
│   │   ├── triggers.json               # Daftar trigger dan otomatisasi terjadwal
│   │   └── mesin-produksi.md           # Jadwal & pipeline produksi Kitab Surgawi
│   ├── integrations/
│   │   └── connected_apps.json         # Katalog aplikasi ekosistem yang terhubung
│   ├── skills/
│   │   └── catalog.md                  # Katalog keterampilan modular (system & custom)
│   └── repos/                          # Catatan repo proyek spesifik zbmaus
│       ├── zbmaus-vela.md
│       ├── zbmaus-vela-secrets.md
│       ├── zbmaus-vela-eco.md
│       ├── asn-admin.md
│       ├── zbmaus-humanoid.md
│       └── zbmaus-kitab-surgawi.md
```

---

## 📦 Repo Ekosistem zbmaus

| Repo | Visibilitas | Peran |
|---|---|---|
| `zbmaus-vela` | Publik | Blueprint & skrip instalasi VPS |
| `zbmaus-vela-secrets` | Privat | Kredensial, env, snapshot state (tidak pernah dicerminkan ke repo ini) |
| `zbmaus-vela-eco` | Publik | Snapshot arsitektur, bot, memory, routine (repo ini) |
| `asn-admin` | Privat | Mesin Produksi Administrasi ASN Diskominfo Aceh Tengah |
| `zbmaus-humanoid` | Publik | Antarmuka humanoid web (Vercel) |
| `zbmaus-kitab-surgawi` | Privat | Mesin produksi bot YouTubeGrowth Kitab Surgawi |

Detail per repo: `ecosystem/repos/`.

## 🛡️ Kebijakan Keamanan (Zero-Credentials)

Repositori ini mematuhi standar sanitasi data:
- **TIDAK ADA** token API, password, private key, token OAuth, atau credential ID sensitif.
- Menggunakan placeholder struktural atau referensi abstrak untuk menjaga keamanan penuh jika repositori dibagikan atau dipindahkan.
- Fokus eksklusif pada metadata operasional, logika orkestrasi agen, dan memori tim.

---

*Disinkronkan secara otomatis oleh ZB (Chief of Staff OpenMausBot) untuk ekosistem `zbmaus`.*
