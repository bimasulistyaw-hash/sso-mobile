# Analisis Gap: Struktural & Delegasi Person
## Proyek SSO Kabupaten Jombang — Evaluasi Kesiapan Fase 2

**Tanggal:** 2 Oktober 2026
**Konteks:** Sistem SSO (Fase 1) sudah selesai dibangun dan di-training, namun belum berjalan optimal di sisi klien. Diperlukan analisis mendalam sebelum melanjutkan ke Fase 2 (Mobile).

---

## I. Hierarki Analisis — Dari Kebutuhan Hingga Keberlanjutan

```mermaid
flowchart TD
    L0["**LEVEL 0: VISI & TUJUAN**<br>SSO Jombang berjalan mandiri & berkelanjutan"]
    
    L1["**LEVEL 1: ANALISIS KEBUTUHAN**<br>Apa yang dibutuhkan?"]
    L2["**LEVEL 2: ANALISIS KESIAPAN**<br>Mampukah jalan?"]
    L3["**LEVEL 3: ANALISIS KEBERLANJUTAN**<br>Bisakah jalan tanpa vendor?"]

    L0 --> L1
    L0 --> L2
    L0 --> L3

    L1 --> Teknis["Teknis"]
    L1 --> Bisnis["Bisnis"]

    L2 --> SDM["SDM"]
    L2 --> Infra["Infra"]

    L3 --> Proses["Proses"]
    L3 --> Ownership["Ownership"]

    classDef level0 fill:#1e3a8a,stroke:#3b82f6,stroke-width:2px,color:#fff;
    classDef level1 fill:#047857,stroke:#10b981,stroke-width:2px,color:#fff;
    classDef level2 fill:#b45309,stroke:#f59e0b,stroke-width:2px,color:#fff;
    classDef level3 fill:#7e22ce,stroke:#a855f7,stroke-width:2px,color:#fff;
    classDef node fill:#334155,stroke:#64748b,stroke-width:1px,color:#fff;

    class L0 level0;
    class L1 level1;
    class L2 level2;
    class L3 level3;
    class Teknis,Bisnis,SDM,Infra,Proses,Ownership node;
```

---

## II. Level 1 — Analisis Kebutuhan (Apa yang Dibutuhkan?)

### A. Kebutuhan Teknis

| **No** | **Kebutuhan** | **Status Fase 1** | **Gap?** |
|---|---|---|---|
| 1 | Server Keycloak aktif & stabil | ✅ Sudah deploy | ⏳ Perlu cek uptime & health |
| 2 | Konfigurasi realm & client benar | ✅ Sudah setup | ⏳ Perlu audit konfigurasi |
| 3 | SSL/TLS certificate valid | ✅ Sudah pasang | ⏳ Perlu cek masa berlaku |
| 4 | Database backend stabil | ✅ Sudah setup | ⏳ Perlu cek kapasitas & backup |
| 5 | API endpoint berjalan | ✅ Sudah develop | ⏳ Perlu cek availability |
| 6 | Dokumentasi teknis lengkap | ❓ Belum dikonfirmasi | ⚠️ Kemungkinan gap besar |

### B. Kebutuhan Bisnis / Proses

| **No** | **Kebutuhan** | **Status** | **Gap?** |
|---|---|---|---|
| 1 | SOP operasional SSO harian | ❓ Belum dikonfirmasi | ⚠️ Kemungkinan belum ada |
| 2 | SOP troubleshooting & eskalasi | ❓ Belum dikonfirmasi | ⚠️ Kemungkinan belum ada |
| 3 | Integrasi OPD ke SSO | ❓ Parsial | ⚠️ Belum semua OPD terintegrasi |
| 4 | Alur pendaftaran user SSO | ✅ Sudah ada | ⏳ Perlu evaluasi |

---

## III. Level 2 — Analisis Kesiapan (Mampukah Jalan?)

### A. Kesiapan SDM — Hierarki Person & Delegasi

```mermaid
flowchart TD
    subgraph S["**STRUKTURAL (Pejabat)**"]
        direction TB
        Kadis["Kepala Dinas Kominfo"]
        Kabid["Kabid Aptika / Infrastruktur"]
        Kasi["Kasi Pengembangan Aplikasi"]
        Ops["??? (Siapa yang operasional?)"]

        Kadis --> Kabid --> Kasi --> Ops
        
        GapS1>⚠️ GAP: Apakah ada SK penunjukan PIC SSO?]
        GapS2>⚠️ GAP: Apakah pejabat memahami apa itu SSO?]
    end
    classDef gap fill:#fef3c7,stroke:#d97706,stroke-width:1px,color:#92400e;
    class GapS1,GapS2 gap;
```

```mermaid
flowchart TD
    subgraph T["**TEKNIS (Pelaksana)**"]
        direction TB
        Prog["Programmer / Developer Kominfo"]
        PA["Programmer A (ikut training?)<br>──→ Masih aktif?"]
        PB["Programmer B (ikut training?)<br>──→ Masih aktif?"]
        PC["Programmer C (baru?)<br>──→ Belum training?"]

        Prog --> PA
        Prog --> PB
        Prog --> PC

        GapT1>⚠️ GAP: Apakah yang di-training = yang mengoperasikan?]
        GapT2>⚠️ GAP: Apakah ada rotasi/mutasi sejak training?]
        GapT3>⚠️ GAP: Apakah ada serah terima knowledge internal?]
    end
    classDef gap fill:#fef3c7,stroke:#d97706,stroke-width:1px,color:#92400e;
    class GapT1,GapT2,GapT3 gap;
```

```mermaid
flowchart TD
    subgraph U["**PENGGUNA (OPD)**"]
        direction TB
        Admin["Admin OPD (tiap instansi)"]
        U1["Paham cara integrasi layanan ke SSO?"]
        U2["Paham cara manage user di realm masing-masing?"]
        U3["Ada SOP internal di OPD?"]

        Admin --> U1
        Admin --> U2
        Admin --> U3

        GapU1>⚠️ GAP: OPD mungkin belum paham kenapa harus pakai SSO]
        GapU2>⚠️ GAP: Tidak ada 'champion' SSO di tiap OPD]
    end
    classDef gap fill:#fef3c7,stroke:#d97706,stroke-width:1px,color:#92400e;
    class GapU1,GapU2 gap;
```

### B. Matriks Delegasi — Siapa Bertanggung Jawab Apa?

| **Fungsi** | **Seharusnya** | **Kondisi Saat Ini** | **Gap** |
|---|---|---|---|
| **Admin Keycloak** (manage realm, client, user) | Programmer Kominfo yang sudah training | ❓ Tidak jelas siapa | ⚠️ Kritis |
| **Monitoring Server** (uptime, health check) | Tim Infrastruktur / DevOps Kominfo | ❓ Tidak jelas siapa | ⚠️ Kritis |
| **Troubleshooting** (error login, token issue) | Programmer Kominfo | ❓ Tidak jelas siapa | ⚠️ Kritis |
| **Integrasi OPD Baru** (daftarkan client baru) | Programmer Kominfo + Admin OPD | ❓ Belum ada prosedur | ⚠️ Sedang |
| **Pengambil Keputusan** (approval, eskalasi) | Kabid/Kasi Aptika | ❓ Perlu dikonfirmasi | ⚠️ Sedang |
| **Koordinasi dengan Vendor** (jika ada masalah) | PIC Proyek dari Kominfo | ❓ Tidak jelas siapa | ⚠️ Sedang |

---

## IV. Level 3 — Analisis Keberlanjutan (Bisakah Jalan Tanpa Vendor?)

### Checklist Kemandirian

| **No** | **Kriteria Kemandirian** | **Indikator** | **Status** |
|---|---|---|---|
| 1 | **Bisa restart server sendiri** | Tim Kominfo tahu cara restart Keycloak jika down | ❓ Perlu cek |
| 2 | **Bisa troubleshoot error dasar** | Tim bisa baca log, identifikasi error umum (401, 403, token expired) | ❓ Perlu cek |
| 3 | **Bisa tambah client baru** | Tim bisa registrasi client baru di Keycloak tanpa bantuan vendor | ❓ Perlu cek |
| 4 | **Bisa manage user** | Tim bisa create/disable/reset password user di Keycloak | ❓ Perlu cek |
| 5 | **Bisa backup & restore** | Tim tahu cara backup database Keycloak dan restore jika perlu | ❓ Perlu cek |
| 6 | **Bisa update/patch** | Tim bisa update versi Keycloak jika ada security patch | ❓ Perlu cek |
| 7 | **Ada dokumentasi internal** | Ada catatan/wiki internal tentang konfigurasi SSO Jombang | ❓ Perlu cek |
| 8 | **Ada SOP eskalasi** | Ada prosedur jelas: siapa dihubungi jika sistem down | ❓ Perlu cek |

### Skala Kematangan (Maturity Level)

```mermaid
flowchart LR
    L0["**Level 0: TIDAK JALAN**<br>Sistem deploy tapi tidak dipakai<br>Tidak ada yang tahu operasikan<br>⚠️ Kemungkinan kondisi saat ini?"]
    L1["**Level 1: BERGANTUNG VENDOR**<br>Semua operasional bergantung vendor<br>Jika vendor lambat → sistem lumpuh<br>❌ Harus dihindari"]
    L2["**Level 2: BISA OPERASIONAL DASAR**<br>Tim bisa handle operasional harian<br>Perlu vendor untuk hal kompleks<br>✅ Target minimum sebelum Fase 2"]
    L3["**Level 3: MANDIRI PENUH**<br>Tim handle semua aspek SSO<br>Ada SOP, dokumentasi, backup person<br>🚀 Target jangka panjang"]

    L0 --> L1 --> L2 --> L3

    classDef l0 fill:#7f1d1d,stroke:#ef4444,stroke-width:2px,color:#fff;
    classDef l1 fill:#9a3412,stroke:#f97316,stroke-width:2px,color:#fff;
    classDef l2 fill:#065f46,stroke:#10b981,stroke-width:2px,color:#fff;
    classDef l3 fill:#1e3a8a,stroke:#3b82f6,stroke-width:2px,color:#fff;

    class L0 l0;
    class L1 l1;
    class L2 l2;
    class L3 l3;
```

---

## V. Rekomendasi Tindakan Sebelum Fase 2

### Prioritas Tinggi (Harus Selesai Sebelum Kick-off Mobile)

| **No** | **Aksi** | **Tujuan** | **PIC** |
|---|---|---|---|
| 1 | **Audit teknis SSO** — cek server, Keycloak, database, SSL | Pastikan fondasi Fase 1 berjalan baik | Lead Dev + Kominfo |
| 2 | **Mapping person** — identifikasi siapa yang di-training dulu vs siapa yang pegang sekarang | Identifikasi knowledge loss | PM + Kominfo |
| 3 | **Assessment kompetensi** — tes singkat kemampuan programmer Kominfo soal Keycloak | Ukur level kesiapan SDM | Lead Dev |
| 4 | **Penunjukan PIC SSO resmi** — minta SK dari Kadis Kominfo | Pastikan ada ownership yang jelas | Kadis Kominfo |
| 5 | **Buat SOP Operasional SSO** — minimal: monitoring, troubleshooting, eskalasi | Pastikan ada prosedur standar | PM + Kominfo |

### Prioritas Sedang (Bisa Paralel dengan Minggu 1–2 Fase 2)

| **No** | **Aksi** | **Tujuan** | **PIC** |
|---|---|---|---|
| 6 | **Refresh training Keycloak** (1–2 sesi) | Tutup gap knowledge yang hilang | Lead Dev |
| 7 | **Dokumentasi ulang** — update/lengkapi docs teknis SSO | Buat reference yang bisa dipakai mandiri | Lead Dev + Kominfo |
| 8 | **Tentukan "SSO Champion"** di tiap OPD | Pastikan ada contact person per instansi | Kominfo + OPD |

---

## VI. Pertanyaan Kunci untuk Rakor

> Pertanyaan-pertanyaan ini **wajib dijawab** sebelum Fase 2 dimulai:

1. **"Siapa yang saat ini bertanggung jawab atas operasional SSO sehari-hari?"**
   → Jika jawabannya *"tidak ada"* atau *"tidak jelas"*, ini red flag utama.

2. **"Apakah orang yang mengikuti training SSO dulu masih menjabat di posisi yang sama?"**
   → Jika sudah mutasi, perlu identifikasi siapa pengganti dan apakah sudah ada transfer knowledge.

3. **"Apa yang terjadi ketika SSO down? Siapa yang handle?"**
   → Jika jawabannya *"hubungi vendor"*, berarti masih di Level 1 (bergantung vendor).

4. **"Apakah sudah ada SK penunjukan PIC SSO dari Kadis Kominfo?"**
   → Tanpa SK formal, ownership akan selalu abu-abu.

5. **"Berapa persen OPD yang sudah aktif menggunakan SSO untuk layanan mereka?"**
   → Jika rendah, masalahnya bukan cuma teknis tapi juga adopsi/sosialisasi.

---

> **Kesimpulan:** Sebelum melangkah ke Fase 2 (Mobile), kita perlu memastikan fondasi Fase 1 (SSO) benar-benar kokoh — bukan hanya dari sisi teknis, tapi juga dari sisi **struktural, person, dan proses**. Tanpa ini, aplikasi mobile yang dibangun di atas SSO yang rapuh hanya akan menambah masalah baru.
