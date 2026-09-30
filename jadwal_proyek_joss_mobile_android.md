# Jadwal & Rincian Output Pengembangan Aplikasi JOSS Mobile Android

## Proyek: Aplikasi JOSS Mobile Android — SSO Kabupaten Jombang (Fase 2)

---

## I. Informasi Proyek

| **Item**                    | **Detail**                                                                 |
| --------------------------- | -------------------------------------------------------------------------- |
| **Nama Proyek**             | JOSS Mobile Android (Jombang Smart Service)                                |
| **Klien**                   | Pemerintah Kabupaten Jombang                                               |
| **Fase**                    | Fase 2 — Pengembangan Aplikasi Mobile Android                              |
| **Durasi**                  | 3 Bulan (12 Minggu Efektif)                                               |
| **Estimasi Mulai**          | Pekan ke-2 s.d. ke-3 Oktober 2026 *(estimasi mundur 1–2 minggu dari 1 Oktober)* |
| **Estimasi Selesai**        | Pekan ke-2 s.d. ke-3 Januari 2027                                         |
| **Status Proyek Fase 1**    | [v] Selesai — Sistem SSO berbasis Web sudah *live* dan stabil              |

---

## II. Skenario & Asumsi Utama

### Asumsi

1. **Sistem backend SSO (Web) dari Fase 1 sudah berjalan stabil** — endpoint API autentikasi, manajemen user, dan role-based access sudah tersedia dan terdokumentasi.
2. **Dokumentasi API** dari Fase 1 sudah tersedia (Swagger/Postman Collection) sehingga tim Android dapat langsung melakukan integrasi.
3. **Infrastruktur server** (hosting, database, domain) sudah siap dan tidak perlu setup ulang.
4. **KAK (Kerangka Acuan Kerja)** sedang dalam proses finalisasi oleh tim Jombang dan diharapkan selesai sebelum kick-off.

### Fokus Utama Fase 2

- Pengembangan aplikasi **native/hybrid Android** yang terintegrasi penuh dengan layanan SSO Fase 1.
- Penambahan fitur spesifik mobile: **Push Notification, Biometric Authentication, Offline Caching, Secure Token Storage**.
- Penyesuaian UI/UX agar responsif dan *user-friendly* di perangkat mobile.

---

## III. Rincian Jadwal & Output per Minggu

---

### [FASE 1] BULAN 1 — Perencanaan, Integrasi API, & Autentikasi SSO Mobile

> **Fokus:** Menyiapkan pondasi aplikasi dan melakukan integrasi core SSO ke platform Android.

---

#### > Minggu 1 — Kick-off & Setup Proyek

| **Item**       | **Detail**                                                                                                                                                                  |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-2/ke-3 Oktober 2026                                                                                                                                               |
| **Aktivitas**  | - Koordinasi internal tim & kick-off meeting bersama klien Jombang <br> - Finalisasi KAK (Kerangka Acuan Kerja) <br> - Setup arsitektur proyek Android (repository, CI/CD pipeline, code convention) <br> - Review dan mapping endpoint API SSO dari Fase 1 <br> - Penyusunan wireframe awal |
| **Output**     | [v] Dokumen KAK Final yang disetujui kedua belah pihak <br> [v] Project Repository & Boilerplate Android (Kotlin/Java) <br> [v] Dokumen Mapping API Endpoint SSO <br> [v] Wireframe UI/UX (Low-Fidelity) |
| **PIC**        | Project Manager, Lead Developer, UI/UX Designer                                                                                                                             |

---

#### > Minggu 2 — Desain UI/UX & Prototyping

| **Item**       | **Detail**                                                                                                                                                                                            |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-3/ke-4 Oktober 2026                                                                                                                                                                         |
| **Aktivitas**  | - Finalisasi desain UI/UX di Figma (High-Fidelity) untuk seluruh halaman utama <br> - Desain halaman: Splash Screen, Onboarding, Login/Register, Lupa Password, Dashboard, Profil Pengguna <br> - Penyusunan Design System (warna, tipografi, komponen reusable) <br> - Review & approval desain oleh klien |
| **Output**     | [v] Dokumen Desain UI/UX Final (Figma Link) — disetujui klien <br> [v] Design System / Style Guide Aplikasi <br> [v] Prototype Interaktif (Clickable Prototype)                                          |
| **PIC**        | UI/UX Designer, Project Manager                                                                                                                                                                       |

---

#### > Minggu 3 — Integrasi Autentikasi SSO & API Core

| **Item**       | **Detail**                                                                                                                                                                                                                                |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-4 Oktober / Pekan ke-1 November 2026                                                                                                                                                                                            |
| **Aktivitas**  | - Implementasi modul autentikasi dasar (Login, Register, Lupa Password) <br> - Integrasi API SSO backend yang sudah ada ke aplikasi Android <br> - Implementasi **Token Handling (JWT)**: penyimpanan, parsing, dan validasi token <br> - Implementasi **OAuth2 / OpenID Connect** flow (jika digunakan) <br> - Setup **Retrofit/OkHttp** sebagai HTTP client dan interceptor untuk auto-attach token |
| **Output**     | [v] Modul Login & Register terintegrasi API SSO (Alpha) <br> [v] Mekanisme JWT Token Handling berjalan <br> [v] Network Layer (Retrofit + Interceptor) terkonfigurasi <br> [v] Unit Test untuk modul autentikasi                                 |
| **PIC**        | Lead Developer, Backend Developer (support)                                                                                                                                                                                                |

---

#### > Minggu 4 — Manajemen Sesi & Keamanan Akses

| **Item**       | **Detail**                                                                                                                                                                                                                    |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-1/ke-2 November 2026                                                                                                                                                                                                |
| **Aktivitas**  | - Implementasi **EncryptedSharedPreferences** untuk penyimpanan token & kredensial yang aman <br> - Implementasi fitur **Auto-Login** (persistent session) <br> - Implementasi fitur **Logout** (clear token, revoke session di server) <br> - Implementasi mekanisme **Refresh Token** otomatis <br> - Penanganan error & expired token (redirect ke halaman login) |
| **Output**     | [v] Modul Manajemen Sesi & Keamanan Akses lengkap <br> [v] Fitur Auto-Login & Persistent Session <br> [v] Mekanisme Refresh Token otomatis <br> [v] Secure Storage untuk data sensitif                                              |
| **PIC**        | Lead Developer, Security Reviewer                                                                                                                                                                                              |

---

### [FASE 2] BULAN 2 — Pengembangan Fitur Utama & Integrasi Layanan (Core Features)

> **Fokus:** Membangun fungsionalitas utama aplikasi dan mengintegrasikan modul-modul turunan SSO.

---

#### > Minggu 5 — Dashboard & Navigasi Utama

| **Item**       | **Detail**                                                                                                                                                                                                     |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-2/ke-3 November 2026                                                                                                                                                                                 |
| **Aktivitas**  | - Pengembangan halaman **Dashboard Utama** setelah login berhasil <br> - Implementasi **Bottom Navigation / Drawer Navigation** <br> - Integrasi data ringkasan (summary cards, statistik, atau quick-access menu) <br> - Implementasi **pull-to-refresh** dan loading state |
| **Output**     | [v] Halaman Dashboard Utama aplikasi <br> [v] Sistem Navigasi Aplikasi (Bottom Nav / Drawer) <br> [v] Komponen UI reusable (cards, lists, loading indicators)                                                       |
| **PIC**        | Android Developer, UI/UX Designer                                                                                                                                                                               |

---

#### > Minggu 6 — Modul Fitur Layanan Utama

| **Item**       | **Detail**                                                                                                                                                                                                                                                          |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-3/ke-4 November 2026                                                                                                                                                                                                                                      |
| **Aktivitas**  | - Pengembangan modul layanan utama sesuai kebutuhan Jombang, meliputi: <br> &nbsp;&nbsp;• **Profil Warga/Pengguna** (view & edit profil, upload foto) <br> &nbsp;&nbsp;• **Riwayat Akses/Aktivitas** pengguna <br> &nbsp;&nbsp;• **Integrasi Layanan Instansi** terkait (jika ada endpoint layanan publik) <br> - Integrasi API layanan dengan error handling yang proper |
| **Output**     | [v] Modul Profil Pengguna (View, Edit, Upload Foto) <br> [v] Modul Riwayat Akses / Log Aktivitas <br> [v] Modul Layanan Instansi (Versi 1) <br> [v] Integrasi API Layanan berjalan                                                                                       |
| **PIC**        | Android Developer, Backend Developer (support API)                                                                                                                                                                                                                   |

---

#### > Minggu 7 — Push Notification & Pengaturan Akun

| **Item**       | **Detail**                                                                                                                                                                                                                                               |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-4 November / Pekan ke-1 Desember 2026                                                                                                                                                                                                           |
| **Aktivitas**  | - Integrasi **Firebase Cloud Messaging (FCM)** untuk push notification <br> - Implementasi notifikasi: pengumuman, update layanan, dan reminder <br> - Pengembangan halaman **Pengaturan Akun** (ubah password, pengaturan notifikasi, bahasa, tema) <br> - Implementasi **in-app notification center** (daftar notifikasi yang diterima) |
| **Output**     | [v] Modul Push Notification (FCM) terintegrasi dan berfungsi <br> [v] In-App Notification Center <br> [v] Halaman Pengaturan Akun Pengguna <br> [v] Pengaturan preferensi notifikasi                                                                            |
| **PIC**        | Android Developer, Backend Developer (FCM setup)                                                                                                                                                                                                          |

---

#### > Minggu 8 — Biometrik, Offline Caching, & Optimasi

| **Item**       | **Detail**                                                                                                                                                                                                                                                              |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-1/ke-2 Desember 2026                                                                                                                                                                                                                                          |
| **Aktivitas**  | - Implementasi **Biometric Authentication** (Fingerprint / Face ID) menggunakan AndroidX Biometric Library <br> - Implementasi **Local Database** (Room Database / SQLite) untuk offline caching data penting <br> - Optimasi performa aplikasi: memory, network call, dan battery usage <br> - Implementasi **connectivity checker** (online/offline mode) |
| **Output**     | [v] Fitur Autentikasi Biometrik (Sidik Jari / Wajah) <br> [v] Local Database & Offline Caching <br> [v] Connectivity-aware UX (indikator online/offline) <br> [v] Laporan optimasi performa aplikasi                                                                         |
| **PIC**        | Lead Developer, Android Developer                                                                                                                                                                                                                                        |

---

### [FASE 3] BULAN 3 — Testing, Bug Fixing, ToT, & Deployment

> **Fokus:** Pengujian menyeluruh, perbaikan bug, pelatihan pengguna, dan publikasi aplikasi.

---

#### > Minggu 9 — Alpha Testing & Bug Fixing

| **Item**       | **Detail**                                                                                                                                                                                                                                                    |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-2/ke-3 Desember 2026                                                                                                                                                                                                                                |
| **Aktivitas**  | - Pelaksanaan **Internal/Alpha Testing** oleh tim pengembang <br> - Penyusunan **Test Case Document** & skenario UAT <br> - Identifikasi dan perbaikan bug (critical & major) <br> - Testing kompatibilitas di berbagai perangkat Android (API level 24–34) <br> - Security testing dasar (token exposure, data leakage) |
| **Output**     | [v] Dokumen Test Case (minimal 50 skenario) <br> [v] Laporan Bug Fixing (Critical & Major resolved) <br> [v] APK Internal Build (Alpha) untuk distribusi testing <br> [v] Laporan Compatibility Testing                                                              |
| **PIC**        | QA Tester, Lead Developer, Seluruh Tim Dev                                                                                                                                                                                                                     |

---

#### > Minggu 10 — UAT & Penyempurnaan Aplikasi

| **Item**       | **Detail**                                                                                                                                                                                                                                                                       |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-3/ke-4 Desember 2026                                                                                                                                                                                                                                                   |
| **Aktivitas**  | - Pelaksanaan **User Acceptance Testing (UAT)** bersama tim/klien Jombang <br> - Pengumpulan feedback dan catatan evaluasi dari pengguna <br> - Penyempurnaan UI/UX berdasarkan hasil UAT <br> - Perbaikan bug minor yang ditemukan saat UAT <br> - Persiapan **materi ToT** (Training of Trainer): modul panduan, video tutorial singkat |
| **Output**     | [v] Berita Acara (BA) Pelaksanaan UAT — ditandatangani kedua pihak <br> [v] Dokumen Catatan Evaluasi & Perbaikan UAT <br> [v] APK Build (Beta — Post-UAT) <br> [v] Draft Modul Panduan Penggunaan Aplikasi                                                                             |
| **PIC**        | Project Manager, QA Tester, Tim Dev, Perwakilan Klien                                                                                                                                                                                                                            |

---

#### > Minggu 11 — Training of Trainer (ToT) & Finalisasi Build

| **Item**       | **Detail**                                                                                                                                                                                                                                                                     |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Periode**    | Pekan ke-4 Desember 2026 / Pekan ke-1 Januari 2027                                                                                                                                                                                                                            |
| **Aktivitas**  | - Pelaksanaan kegiatan **ToT (Training of Trainer)** untuk pengelola/admin di Jombang <br> - Materi ToT mencakup: cara instalasi, penggunaan fitur, troubleshooting dasar, dan pengelolaan akun <br> - Finalisasi build aplikasi untuk rilis (Release Candidate) <br> - Penyusunan **Dokumentasi Teknis** (arsitektur, API docs, deployment guide) |
| **Output**     | [v] Laporan Pelaksanaan ToT (daftar hadir, dokumentasi foto, materi) <br> [v] Modul Panduan Penggunaan Aplikasi (Final) <br> [v] Master APK / App Bundle (Release Candidate) <br> [v] Dokumentasi Teknis Aplikasi                                                                     |
| **PIC**        | Project Manager, Lead Developer, Trainer                                                                                                                                                                                                                                        |

---

#### > Minggu 12 — Deployment, Serah Terima, & Penutupan Proyek

| **Item**       | **Detail**                                                                                                                                                                                                                                                                                                             |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-1/ke-2 Januari 2027                                                                                                                                                                                                                                                                                          |
| **Aktivitas**  | - Proses **submission ke Google Play Store** (atau distribusi internal via APK/MDM instansi) <br> - Monitoring pasca-rilis (crash reporting via Firebase Crashlytics) <br> - Penyusunan dokumen penutupan proyek <br> - Penandatanganan **Berita Acara Serah Terima (BAST)** <br> - Handover source code, dokumentasi, dan akses repository ke pihak Jombang |
| **Output**     | [v] Aplikasi JOSS Mobile tayang di Google Play Store / terdistribusi <br> [v] Dokumentasi Teknis Akhir (Source Code, API Docs, Deployment Guide) <br> [v] Berita Acara Serah Terima (BAST) — ditandatangani kedua pihak <br> [v] Handover seluruh aset proyek                                                                  |
| **PIC**        | Project Manager, Lead Developer, Perwakilan Klien                                                                                                                                                                                                                                                                       |

---

## IV. Ringkasan Timeline (Gantt Chart Overview)

### Tabel Ringkasan per Fase

| **Fase** | **Indikator** | **Minggu** | **Durasi** | **Fokus Utama** |
| --- | --- | --- | --- | --- |
| Perencanaan & Integrasi API/SSO Mobile | <span style="background:#2563EB;color:#fff;padding:2px 10px;border-radius:4px;font-weight:bold;">FASE A</span> | 1 – 4 | 4 Minggu | Setup proyek, desain UI/UX, integrasi autentikasi SSO |
| Pengembangan Fitur Utama & Layanan | <span style="background:#16A34A;color:#fff;padding:2px 10px;border-radius:4px;font-weight:bold;">FASE B</span> | 5 – 8 | 4 Minggu | Dashboard, modul layanan, notifikasi, biometrik |
| Testing, ToT, & Deployment | <span style="background:#EA580C;color:#fff;padding:2px 10px;border-radius:4px;font-weight:bold;">FASE C</span> | 9 – 12 | 4 Minggu | Alpha/UAT testing, pelatihan, rilis & serah terima |

### Tabel Detail Gantt Chart — 12 Minggu

| **Minggu** | **Fase** | **Periode** | **Aktivitas Utama** | **Output / Deliverable** | **Okt** | **Nov** | **Des** | **Jan** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **1** | <span style="background:#2563EB;color:#fff;padding:2px 8px;border-radius:4px;">A</span> Perencanaan | Okt Pekan 2–3 | Kick-off, finalisasi KAK, setup repo & arsitektur | KAK Final, Boilerplate Repo, Wireframe | <span style="background:#2563EB;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | | | |
| **2** | <span style="background:#2563EB;color:#fff;padding:2px 8px;border-radius:4px;">A</span> Perencanaan | Okt Pekan 3–4 | Desain UI/UX Figma (High-Fidelity), Design System | Desain UI/UX Final, Prototype Interaktif | <span style="background:#2563EB;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | | | |
| **3** | <span style="background:#2563EB;color:#fff;padding:2px 8px;border-radius:4px;">A</span> Integrasi SSO | Okt–Nov Pekan 4–1 | Integrasi API SSO, modul login/register, JWT Handling | Modul Login & SSO (Alpha), Network Layer | <span style="background:#2563EB;color:#fff;padding:2px 8px;border-radius:4px 0 0 4px;">■■</span> | <span style="background:#2563EB;color:#fff;padding:2px 8px;border-radius:0 4px 4px 0;">■■</span> | | |
| **4** | <span style="background:#2563EB;color:#fff;padding:2px 8px;border-radius:4px;">A</span> Integrasi SSO | Nov Pekan 1–2 | Manajemen sesi, EncryptedSharedPreferences, refresh token | Modul Sesi & Keamanan, Auto-Login | | <span style="background:#2563EB;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | | |
| **5** | <span style="background:#16A34A;color:#fff;padding:2px 8px;border-radius:4px;">B</span> Core Features | Nov Pekan 2–3 | Dashboard utama, navigasi (Bottom Nav/Drawer) | Dashboard & Navigasi, Komponen UI | | <span style="background:#16A34A;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | | |
| **6** | <span style="background:#16A34A;color:#fff;padding:2px 8px;border-radius:4px;">B</span> Core Features | Nov Pekan 3–4 | Modul layanan utama: profil warga, riwayat akses, layanan instansi | Modul Profil, Riwayat Akses, Layanan v1 | | <span style="background:#16A34A;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | | |
| **7** | <span style="background:#16A34A;color:#fff;padding:2px 8px;border-radius:4px;">B</span> Core Features | Nov–Des Pekan 4–1 | Push notification (FCM), pengaturan akun & preferensi | Modul Notifikasi & Pengaturan Akun | | <span style="background:#16A34A;color:#fff;padding:2px 8px;border-radius:4px 0 0 4px;">■■</span> | <span style="background:#16A34A;color:#fff;padding:2px 8px;border-radius:0 4px 4px 0;">■■</span> | |
| **8** | <span style="background:#16A34A;color:#fff;padding:2px 8px;border-radius:4px;">B</span> Core Features | Des Pekan 1–2 | Biometrik (Fingerprint/Face ID), offline caching (Room DB) | Fitur Biometrik, Local DB, Optimasi Performa | | | <span style="background:#16A34A;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | |
| **9** | <span style="background:#EA580C;color:#fff;padding:2px 8px;border-radius:4px;">C</span> Testing | Des Pekan 2–3 | Alpha testing internal, penyusunan test case, bug fixing | Test Case (50+ skenario), APK Alpha, Laporan Bug | | | <span style="background:#EA580C;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | |
| **10** | <span style="background:#EA580C;color:#fff;padding:2px 8px;border-radius:4px;">C</span> Testing | Des Pekan 3–4 | UAT bersama klien Jombang, perbaikan dari feedback | BA UAT, Evaluasi Perbaikan, APK Beta | | | <span style="background:#EA580C;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | |
| **11** | <span style="background:#EA580C;color:#fff;padding:2px 8px;border-radius:4px;">C</span> Deployment | Des–Jan Pekan 4–1 | ToT (Training of Trainer), finalisasi build Release Candidate | Laporan ToT, Panduan Penggunaan, APK RC | | | <span style="background:#EA580C;color:#fff;padding:2px 8px;border-radius:4px 0 0 4px;">■■</span> | <span style="background:#EA580C;color:#fff;padding:2px 8px;border-radius:0 4px 4px 0;">■■</span> |
| **12** | <span style="background:#EA580C;color:#fff;padding:2px 8px;border-radius:4px;">C</span> Deployment | Jan Pekan 1–2 | Submission Play Store, serah terima, BAST | Aplikasi Live, Dokumentasi Akhir, BAST | | | | <span style="background:#EA580C;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> |

### Visualisasi Progress per Bulan

| **Bulan** | **W1** | **W2** | **W3** | **W4** | **Milestone Utama** |
| --- | --- | --- | --- | --- | --- |
| **Bulan 1** (Okt–Nov) | <span style="background:#2563EB;color:#fff;padding:2px 6px;border-radius:4px;">A</span> Kick-off & KAK | <span style="background:#2563EB;color:#fff;padding:2px 6px;border-radius:4px;">A</span> Desain UI/UX | <span style="background:#2563EB;color:#fff;padding:2px 6px;border-radius:4px;">A</span> Integrasi SSO | <span style="background:#2563EB;color:#fff;padding:2px 6px;border-radius:4px;">A</span> Manajemen Sesi | [v] Autentikasi SSO Mobile berjalan |
| **Bulan 2** (Nov–Des) | <span style="background:#16A34A;color:#fff;padding:2px 6px;border-radius:4px;">B</span> Dashboard | <span style="background:#16A34A;color:#fff;padding:2px 6px;border-radius:4px;">B</span> Modul Layanan | <span style="background:#16A34A;color:#fff;padding:2px 6px;border-radius:4px;">B</span> Notifikasi | <span style="background:#16A34A;color:#fff;padding:2px 6px;border-radius:4px;">B</span> Biometrik & Cache | [v] Seluruh fitur utama selesai |
| **Bulan 3** (Des–Jan) | <span style="background:#EA580C;color:#fff;padding:2px 6px;border-radius:4px;">C</span> Alpha Test | <span style="background:#EA580C;color:#fff;padding:2px 6px;border-radius:4px;">C</span> UAT Klien | <span style="background:#EA580C;color:#fff;padding:2px 6px;border-radius:4px;">C</span> ToT & Build Final | <span style="background:#EA580C;color:#fff;padding:2px 6px;border-radius:4px;">C</span> Rilis & BAST | [v] Aplikasi live & proyek serah terima |

---

## V. Ruang Lingkup Teknis — Apa yang Harus Dikerjakan Tim

Mengingat **SSO Web dari Fase 1 sudah selesai**, berikut adalah fokus teknis untuk Fase 2:

### 1. API Integration Layer
- Menghubungkan seluruh endpoint autentikasi SSO web ke aplikasi Android
- Mengatur flow **OAuth2 / OpenID Connect** (jika digunakan)
- Implementasi mekanisme **Refresh Token** otomatis
- Setup **Retrofit + OkHttp Interceptor** untuk auto-attach Authorization header

### 2. Mobile Security
- **EncryptedSharedPreferences** untuk penyimpanan token & data sensitif
- **Certificate Pinning** (opsional, untuk keamanan komunikasi HTTPS)
- **ProGuard/R8** obfuscation untuk proteksi APK
- **Biometric Authentication** (AndroidX Biometric Library)

### 3. Android-Specific Features
- **Push Notification** via Firebase Cloud Messaging (FCM)
- **Offline Caching** menggunakan Room Database / SQLite
- **Connectivity Checker** untuk mode online/offline
- **Deep Linking** (opsional, untuk navigasi dari notifikasi atau link eksternal)

### 4. UI/UX Adaptation
- Desain responsif untuk berbagai ukuran layar Android
- Implementasi **Material Design 3** guidelines
- Animasi transisi halaman yang smooth
- Dark Mode support (opsional)

---

## VI. Daftar Deliverables / Output Utama Proyek

| **No** | **Deliverable**                                  | **Target Minggu** |
| ------ | ------------------------------------------------ | ------------------ |
| 1      | Dokumen KAK Final                                | Minggu 1           |
| 2      | Dokumen Desain UI/UX (Figma)                     | Minggu 2           |
| 3      | Modul Login & Integrasi SSO                      | Minggu 3           |
| 4      | Modul Manajemen Sesi & Keamanan                  | Minggu 4           |
| 5      | Halaman Dashboard & Navigasi                     | Minggu 5           |
| 6      | Modul Fitur Layanan Utama                        | Minggu 6           |
| 7      | Modul Push Notification & Pengaturan Akun        | Minggu 7           |
| 8      | Fitur Biometrik & Local Database                 | Minggu 8           |
| 9      | Dokumen Test Case & APK Alpha                    | Minggu 9           |
| 10     | Berita Acara UAT & Modul Panduan                 | Minggu 10          |
| 11     | Laporan ToT & Master APK Final                   | Minggu 11          |
| 12     | Aplikasi Live + BAST + Dokumentasi Teknis Akhir  | Minggu 12          |

---

## VII. Catatan & Risiko

| **Risiko**                                     | **Mitigasi**                                                                  |
| ---------------------------------------------- | ----------------------------------------------------------------------------- |
| Keterlambatan finalisasi KAK                   | Paralel dengan setup teknis di Minggu 1                                       |
| Perubahan requirement di tengah proyek         | Change Request formal dengan impact analysis                                  |
| Kompatibilitas perangkat Android beragam       | Testing di minimal 5 perangkat berbeda (API 24–34)                            |
| Kendala submission Google Play Store           | Persiapan akun developer & compliance sejak Minggu 9                          |
| Ketergantungan pada stabilitas API SSO Fase 1  | Monitoring uptime API & koordinasi rutin dengan tim backend                   |

---

> **Dokumen ini disusun sebagai acuan jadwal dan output pengembangan aplikasi JOSS Mobile Android (Fase 2) untuk Proyek SSO Kabupaten Jombang. Jadwal bersifat fleksibel dan dapat disesuaikan berdasarkan kesepakatan bersama antara tim pengembang dan pihak Kabupaten Jombang.**

---

*Disusun oleh: Tim Pengembang SSO Jombang*
*Tanggal: September 2026*
