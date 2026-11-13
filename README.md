# zbmaus-vela-eco

> **Repositori Sinkronisasi Ekosistem OpenMausBot (zbmaus)**  
> Snapshot terstruktur, transparan, dan lengkap untuk ekosistem OMB tanpa kredensial/rahasia apapun (*Zero-Credentials*).

---

## 🎯 Tujuan Repositori

Repositori ini dibuat untuk menjembatani dan melengkapi dua repositori yang sudah ada sebelumnya:
1. **`zbmaus-vela`** (Publik): Berisi instruksi instalasi, skrip deployment OS/VPS, unit systemd, dan panduan infrastruktur mentah.
2. **`zbmaus-vela-secrets`** (Privat): Berisi konfigurasi deployment, file env, kredensial, dan snapshot state tertentu.

### 🔍 Kesenjangan yang Diisi oleh `zbmaus-vela-eco`:
- **Team Memory**: Memuat seluruh catatan memori bersama (6 accepted team notes) yang krusial bagi seluruh agen OMB.
- **Roster & SOUL Bot Terkini**: Data lengkap 7 bot aktif, ID unik, alokasi model, deskripsi tupoksi, dan instruksi berdiri (SOUL).
- **Routines & Triggers Aktif**: Daftar rutinitas otomatis (jadwal harian GitHub, interval pemantauan harian, morning brief, dll).
- **Katalog Integrasi (Connected Apps)**: Pemetaan integrasi aplikasi ekosistem (GitHub, Vercel, YouTube, Kaggle, BoldSign, dsb) tanpa menyertakan token/kredensial.
- **Skills & Prosedur**: Katalog kemampuan kerja modular dan orkestrasi workflow subagen.
- **Topik Memori Personal & Kebijakan**: Rekaman preferensi bahasa, repositori kerja, dan aturan proyek ekosistem.

---

## 📂 Struktur Direktori

```text
zbmaus-vela-eco/
├── README.md                           # Dokumentasi utama dan panduan ekosistem
├── ecosystem/
│   ├── bots.json                       # Roster lengkap 7 bot beserta metadata dan status model
│   ├── architecture/
│   │   └── overview.md                 # Arsitektur koordinasi General department & hierarki agen
│   ├── souls/                          # Instruksi berdiri (SOUL) tiap agen
│   │   ├── zb.md                       # Chief of Staff (MausBot)
│   │   ├── asn-admin.md                # Spesialis Mesin Administrasi ASN Diskominfo
│   │   ├── zbmaus-humanoid-vercel.md   # Asisten humanoid interaktif web Vercel
│   │   ├── youtubegrowth-kitab-surgawi.md # Spesialis pertumbuhan channel dakwah
│   │   ├── islamicedu-kids.md          # Spesialis edukasi Islam usia 2-4 tahun
│   │   ├── kaggle-qwen.md              # Asisten inferensi ringan Kaggle T4 GPU
│   │   └── nova.md                     # Integrator tupoksi baru ekosistem (7 pattern)
│   ├── memory/
│   │   ├── team_memory.json            # 6 catatan memori bersama (format data terstruktur)
│   │   ├── team_memory.md              # Narasi dan konteks memori tim
│   │   └── zb_memory.md                # Long-term memory & topic notes (project, github, language)
│   ├── routines/
│   │   └── triggers.json               # Daftar trigger dan otomatisasi terjadwal
│   ├── integrations/
│   │   └── connected_apps.json         # Katalog aplikasi ekosistem yang terhubung
│   └── skills/
│       └── catalog.md                  # Katalog keterampilan modular (system & custom)
```

---

## 🛡️ Kebijakan Keamanan (Zero-Credentials)

Repositori ini mematuhi standar sanitasi data:
- **TIDAK ADA** token API, password, private key, token OAuth, atau credential ID sensitif.
- Menggunakan placeholder struktural atau referensi abstrak untuk menjaga keamanan penuh jika repositori dibagikan atau dipindahkan.
- Fokus eksklusif pada metadata operasional, logika orkestrasi agen, dan memori tim.

---

*Disinkronkan secara otomatis oleh ZB (Chief of Staff OpenMausBot) untuk ekosistem `zbmaus`.*
