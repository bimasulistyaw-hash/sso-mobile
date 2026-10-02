# Catatan Klarifikasi & Pertanyaan untuk Rakor
## Proyek: JOSS Mobile — SSO Kabupaten Jombang (Fase 2)

**Tanggal Penyusunan:** 1 Oktober 2026
**Tujuan:** Daftar pertanyaan dan poin klarifikasi yang perlu dibahas bersama pihak **MBO** sebelum kick-off proyek dimulai.
**Status:** ⏳ Menunggu Rakor

---

## I. Pertanyaan Umum Proyek

### 1. Usulan Prakondisi: Assessment Kesiapan SDM & Kebutuhan
> [!NOTE]
> **Konteks:** Menghindari masalah operasional seperti di Fase 1 (SSO sudah jadi tapi tidak berjalan optimal/terjadi gap struktural).
> **Usulan:** Kami akan melakukan *assessment awal* sebelum pengerjaan Fase 2 dimulai.

- ✏️ **Assessment Personil:** Mengecek secara langsung kesiapan, pemahaman, dan kapabilitas delegasi yang ditunjuk (baik struktural maupun teknis).
- ✏️ **Analisis Kebutuhan Lanjutan:** Memastikan kedua belah pihak (vendor & klien) memiliki pemahaman yang persis sama tentang *apa yang harus dikerjakan* (What needs to be done).
- ✏️ **Selling Service & Komunikasi:** Membangun komunikasi yang lebih intens (intimate) dengan pihak MBO/Jombang agar ekspektasi layanan terjaga, tidak ada barrier komunikasi, dan tidak menjadi isu/blocker di masa mendatang.

---

### 2. Rakor & Finalisasi KAK
> [!NOTE]
> Perlu dijadwalkan **Rapat Koordinasi (Rakor)** dengan pihak Jombang untuk finalisasi **Kerangka Acuan Kerja (KAK)**. Target output rakor adalah dokumen KAK Final yang disepakati kedua belah pihak.

- ✏️ **Kapan jadwal Rakor via Zoom dapat dilaksanakan?**
- ✏️ **Apakah KAK sudah dalam tahap draft final atau masih perlu revisi substansial?**
- ✏️ **Teknologi mobile yang disepakati: Flutter atau Kotlin native?** *(Saat ini dokumen jadwal menggunakan asumsi Flutter untuk cross-platform Android & iOS. Jika Kotlin, maka scope hanya Android dan timeline perlu disesuaikan.)*

---

### 3. Multi-Tema Aplikasi
> [!NOTE]
> Terkait tampilan/tema aplikasi mobile JOSS.

- ✏️ **Apakah aplikasi perlu mendukung multi-tema (light mode & dark mode)?**
- ✏️ **Atau apakah ada kebutuhan tema khusus sesuai branding Pemkab Jombang (warna, logo, dll)?**
- ✏️ **Apakah ada panduan branding / style guide resmi yang perlu diikuti?**

---

### 4. Mapping Person & Delegasi Penanggung Jawab
> [!NOTE]
> Perlu kejelasan struktur tim dan penanggung jawab dari kedua sisi (tim konsultan & pihak Jombang).

- ✏️ **Siapa PIC (Person in Charge) dari pihak Jombang untuk proyek ini?**
- ✏️ **Siapa delegasi yang berwenang memberikan approval desain, UAT, dan BAST?**
- ✏️ **Berapa jumlah programmer dari Dinas Kominfo Jombang yang akan terlibat dalam transfer knowledge?**

---

### 5. Presentasi Desain Mobile
> [!NOTE]
> Desain UI/UX (High-Fidelity di Figma) perlu dipresentasikan dan disetujui klien sebelum masuk fase development.

- ✏️ **Presentasi desain dijadwalkan di minggu ke berapa?** *(Saat ini di jadwal ada di Minggu 2, apakah realistis?)*
- ✏️ **Format presentasi: via Zoom atau perlu tatap muka langsung?**
- ✏️ **Berapa lama waktu review & approval yang dibutuhkan pihak Jombang?**

---

### 6. Modul Berita & Integrasi Portal
> [!NOTE]
> Berdasarkan referensi portal JSS Jogjakota, ada kebutuhan integrasi modul berita/informasi di aplikasi mobile.

- ✏️ **Apakah Pemkab Jombang sudah punya portal berita resmi yang bisa diintegrasikan via API?**
- ✏️ **Jika belum ada API berita, apakah perlu dibangun juga di sisi backend/web?**
- ✏️ **Apakah modul berita ini juga perlu ditambahkan di portal web JOSS (joss.jombangkab.go.id), atau cukup di mobile saja?**
- ✏️ **Konten berita bersumber dari mana? (Diskominfo, Humas Pemkab, atau agregasi dari website OPD?)**

---

### 7. Jadwal TOT (Training of Trainer)
> [!NOTE]
> TOT dijadwalkan di fase akhir proyek untuk transfer knowledge ke tim Jombang.

- ✏️ **Apakah ada permintaan TOT SSO (Keycloak) terpisah di bulan November?** *(Di luar TOT aplikasi mobile yang dijadwalkan di Minggu 11.)*
- ✏️ **Jika ya, materi TOT SSO mencakup apa saja? (Admin Keycloak, manajemen user, konfigurasi realm, dsb.)**

---

### 8. Format Pelaksanaan TOT
> [!NOTE]
> Perlu kejelasan format pelaksanaan TOT agar persiapan materi dan logistik bisa disiapkan.

- ✏️ **TOT dilaksanakan secara online (Zoom) atau offline (tatap muka di Jombang)?**
- ✏️ **Jika offline, apakah pihak Jombang menyediakan ruangan, proyektor, dan koneksi internet?**
- ✏️ **Berapa jumlah peserta TOT yang akan diikutsertakan?**

---

### 9. Delegasi Penanggung Jawab Mobile Development
> [!NOTE]
> Terkait pembagian tanggung jawab pengembangan antara tim konsultan dan programmer Kominfo Jombang.

- ✏️ **Apakah ada penunjukan resmi programmer dari Kominfo Jombang yang akan di-assign untuk mobile development?**
- ✏️ **Apakah programmer tersebut sudah memiliki pengalaman Flutter/mobile development, atau perlu pelatihan dari awal?**
- ✏️ **Mekanisme kolaborasi pengembangan: parallel development atau mentoring/shadowing?**

---

## II. Klarifikasi Teknis dengan MBO

> [!NOTE]
> Poin-poin berikut merupakan hal teknis yang perlu diklarifikasi terkait pembagian kerja dan mekanisme transfer knowledge.

### A. Setup Repository & Infrastruktur Dasar
- ✏️ **Project repository `joss-mobile` sudah disiapkan?** Atau perlu dibuat dari awal oleh tim konsultan?
- ✏️ **Dependency management dan CI/CD dasar** — apakah menggunakan GitHub Actions, GitLab CI, atau platform lain?
- ✏️ **Environment staging/development** sudah tersedia atau perlu setup?

### B. Pengembangan Modul Layanan Publik Utama (Pertama)
- ✏️ Modul layanan publik utama pertama — yaitu **konsumsi API JOSS untuk pengajuan/permohonan layanan terintegrasi** — akan **dikerjakan penuh oleh tim konsultan**.
- ✏️ **Konfirmasi:** Apakah API endpoint untuk pengajuan layanan sudah tersedia dari portal web, atau perlu dikembangkan baru?
- ✏️ **Format data pengajuan layanan** sudah terdefinisi? (Field apa saja yang perlu diisi user saat mengajukan permohonan?)

### C. Pengembangan Modul Layanan Publik Kedua & Notifikasi
- ✏️ Modul layanan publik **kedua** dan **modul notifikasi** dalam aplikasi — mekanisme pengerjaannya bagaimana?
- ✏️ Apakah dikerjakan **bersama** (tim konsultan + programmer Kominfo) atau **didelegasikan** ke programmer Kominfo dengan supervisi?

### D. Workshop Testing & Debugging
- ✏️ Akan diadakan **workshop teknik testing dan debugging** aplikasi mobile.
- ✏️ **Programmer Kominfo diharapkan menulis test case bersama** tim konsultan.
- ✏️ **Konfirmasi:** Apakah programmer Kominfo sudah familiar dengan konsep unit testing / integration testing?
- ✏️ **Tools testing** yang akan digunakan: Flutter Test, Integration Test, atau ada preferensi lain?

### E. Evaluasi Kompetensi Programmer Kominfo
- ✏️ Di akhir proyek, akan dilakukan **evaluasi/uji kompetensi** programmer Kominfo atas seluruh materi transfer knowledge yang telah diberikan.
- ✏️ **Format evaluasi:** ujian tertulis, praktik coding, atau assessment project?
- ✏️ **Kriteria kelulusan/kompetensi minimum** yang diharapkan apa saja?
- ✏️ **Output evaluasi:** sertifikat, laporan kompetensi, atau rekomendasi?

---

## III. Ringkasan Aksi yang Dibutuhkan

| **No** | **Aksi** | **PIC** | **Target** |
|---|---|---|---|
| 1 | Jadwalkan Rakor via Zoom untuk finalisasi KAK | PM + Klien | Segera |
| 2 | Konfirmasi teknologi: Flutter vs Kotlin | PM + Klien | Rakor |
| 3 | Mapping PIC & delegasi dari pihak Jombang | Klien | Rakor |
| 4 | Tentukan jadwal presentasi desain UI/UX | PM | Rakor |
| 5 | Klarifikasi ketersediaan API berita Jombang | Klien + Backend | Rakor |
| 6 | Konfirmasi jadwal & format TOT SSO (Nov) | PM + Klien | Rakor |
| 7 | Konfirmasi format TOT: online vs offline | PM + Klien | Rakor |
| 8 | Penunjukan programmer Kominfo untuk mobile dev | Klien | Rakor |
| 9 | Klarifikasi setup repo, CI/CD, dan environment | Lead Dev + Klien | Minggu 1 |
| 10 | Konfirmasi ketersediaan API layanan publik | Backend + Klien | Minggu 1 |

---

> [!IMPORTANT]
> **Dokumen ini akan dibawa sebagai bahan diskusi pada Rakor berikutnya. Setiap poin yang sudah terjawab akan di-update statusnya menjadi ✅ Terjawab.**
