# Arsitektur Ekosistem zbmaus

```mermaid
graph TD
    User([Pengguna / Niumination]) <--> ZB[ZB / MausBot - Chief of Staff]
    
    subgraph General Department
        ZB <--> AsnAdmin[AsnAdmin<br/>Mesin Administrasi ASN]
        ZB <--> Humanoid[ZbmausHumanoid-Vercel<br/>Web Interface Vercel]
        ZB <--> YTG[YouTubeGrowth Kitab Surgawi<br/>YouTube & FB Distribution]
        ZB <--> IslamicEdu[IslamicEdu Kids<br/>Edukasi Anak 2-4 Thn]
        ZB <--> KaggleQwen[Kaggle-Qwen<br/>Inferensi Ringan T4 GPU]
        ZB <--> Nova[Nova<br/>Tupoksi Baru & Integrator]
    end

    subgraph Infrastruktur & Penyimpanan
        ZB --- DuckDB[(DuckDB Data Engine)]
        ZB --- Routines[Automasi / Triggers]
        ZB --- TeamMemory[(Team Memory)]
    end

    subgraph Eksternal Integrasi
        AsnAdmin --- RepoASN[Repo: Niumination/asn-admin]
        Humanoid --- VercelApp[zbmaus-humanoid.vercel.app]
        YTG --- YouTubeChannel[YouTube @kitabsurgawi-1357]
        YTG --- FBPage[Facebook Page 1467846356417352]
    end
```

## Prinsip Koordinasi
1. **Single Point of Contact**: Pengguna berinteraksi langsung melalui ZB.
2. **Spesialis Mandiri**: Setiap agen memegang ranah domain tertentu (ASN, Media/Dakwah, Web frontend, Edukasi, Riset/Tupoksi).
3. **Koordinasi Peer**: ZB mendelegasikan tugas menggunakan `coordinate_bots` tanpa mengambil alih otoritas internal spesialis.
4. **Penanganan Insiden Terpusat**: Kegagalan agen (seperti limit kuota token atau perubahan status model gratis) dilaporkan ke ZB untuk ditangani atau dikomunikasikan secara transparan ke pengguna.
