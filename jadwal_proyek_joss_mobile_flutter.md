# Jadwal & Rincian Output Pengembangan Aplikasi JOSS Mobile (Flutter)

## Proyek: Aplikasi JOSS Mobile (Android & iOS) — SSO Kabupaten Jombang (Fase 2)

---

## I. Informasi Proyek

| **Item**                    | **Detail**                                                                 |
| --------------------------- | -------------------------------------------------------------------------- |
| **Nama Proyek**             | JOSS Mobile (Jombang One Stop Service)                             |
| **Klien**                   | Pemerintah Kabupaten Jombang — Dinas Komunikasi dan Informatika            |
| **Fase**                    | Fase 2 — Pengembangan Portal Aplikasi Mobile (Flutter: Android & iOS)      |
| **Durasi**                  | 3 Bulan (12 Minggu Efektif)                                               |
| **Estimasi Mulai**          | Pekan ke-2 s.d. ke-3 Oktober 2026 *(estimasi mundur 1–2 minggu dari 1 Oktober)* |
| **Estimasi Selesai**        | Pekan ke-2 s.d. ke-3 Januari 2027                                         |
| **Portal Web (Fase 1)**     | [v] Live — https://joss.jombangkab.go.id                                  |
| **SSO Server**              | Keycloak — https://sso-v2.jombangkab.go.id (Realm: `jombangkab`)          |
| **Protokol Autentikasi**    | OAuth2 / OpenID Connect (Authorization Code Flow)                          |

---

## II. Skenario & Asumsi Utama


### Arsitektur SSO Keycloak (Existing)

| **Komponen** | **Detail** |
| --- | --- |
| Keycloak Server | `https://sso-v2.jombangkab.go.id` |
| Realm | `jombangkab` |
| Client ID (Web) | `joss` |
| Client ID (Mobile) | `joss-mobile` *(perlu didaftarkan baru di Keycloak)* |
| Auth Flow | OAuth2 / OpenID Connect — Authorization Code + PKCE |
| Login Action URL | `/realms/jombangkab/login-actions/authenticate` |
| Token Endpoint | `/realms/jombangkab/protocol/openid-connect/token` |
| UserInfo Endpoint | `/realms/jombangkab/protocol/openid-connect/userinfo` |
| Logout Endpoint | `/realms/jombangkab/protocol/openid-connect/logout` |
| Tema Login | `joss-sso-theme` (custom theme) |

### Referensi Fitur Portal Web (Yang Harus Di-mirror ke Mobile)

Berdasarkan analisis portal https://joss.jombangkab.go.id:

| **No** | **Fitur Web** | **Adaptasi Mobile** |
| --- | --- | --- |
| 1 | Katalog layanan dengan kategori (Kepegawaian, Ketenagakerjaan, Layanan Publik) | Grid/List layanan dengan filter kategori |
| 2 | Pencarian layanan (`/api/layanan?search=...`) | Search bar dengan real-time search |
| 3 | Login via Keycloak SSO | Login via Keycloak OIDC + PKCE (Chrome Custom Tab / AppAuth) |
| 4 | Register akun baru | Register via Keycloak registration flow |
| 5 | Verifikasi KYC (Akun Belum Terverifikasi) | Status KYC di profil + notifikasi |
| 6 | Akses aplikasi/layanan instansi | Deep link / WebView ke layanan terkait |
| 7 | Placeholder "Unduh Aplikasi JOSS" di footer | Link langsung ke Google Play Store & Apple App Store |

### Fokus Utama Fase 2

- Membangun **portal mobile multi-platform (Android & iOS)** menggunakan framework **Flutter** sebagai mirror dari portal web JOSS yang sudah live.
- Integrasi autentikasi SSO via **Keycloak OIDC + PKCE** (menggunakan library AppAuth untuk Flutter).
- **Pengembangan API tambahan** di backend untuk mendukung fitur mobile yang belum tersedia.
- Penambahan fitur spesifik mobile: **Push Notification, Offline Caching**.
- Penyesuaian UI/UX agar responsif dan *user-friendly* di berbagai ukuran layar smartphone (Android/iOS).

---

## III. Rincian Jadwal & Output per Minggu

### Ringkasan Timeline (Gantt Chart Overview)

### Tabel Ringkasan per Fase

| **Fase** | **Indikator** | **Minggu** | **Durasi** | **Fokus Utama** |
| --- | --- | --- | --- | --- |
| Perencanaan & Integrasi API/SSO Mobile | <span style="background:#2563EB;color:#fff;padding:2px 10px;border-radius:4px;font-weight:bold;">FASE A</span> | 1 – 4 | 4 Minggu | Setup proyek, desain UI/UX, integrasi autentikasi SSO |
| Pengembangan Fitur Utama & Layanan | <span style="background:#16A34A;color:#fff;padding:2px 10px;border-radius:4px;font-weight:bold;">FASE B</span> | 5 – 8 | 4 Minggu | Dashboard, modul layanan, notifikasi, biometrik |
| Testing, ToT, & Deployment | <span style="background:#EA580C;color:#fff;padding:2px 10px;border-radius:4px;font-weight:bold;">FASE C</span> | 9 – 12 | 4 Minggu | Alpha/UAT testing, pelatihan, rilis & serah terima |

### Tabel Detail Gantt Chart — 12 Minggu

| **Minggu** | **Fase** | **Periode** | **Aktivitas Utama** | **Modul / Komponen Terkait** | **Output / Deliverable** | **Okt** | **Nov** | **Des** | **Jan** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **1** | <span style="background:#2563EB;color:#fff;padding:2px 8px;border-radius:4px;">A</span> Perencanaan | Okt Pekan 2–3 | Kick-off, finalisasi KAK, setup repo & arsitektur | Arsitektur Dasar & Boilerplate | KAK Final, Boilerplate Repo, Wireframe | <span style="background:#2563EB;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | | | |
| **2** | <span style="background:#2563EB;color:#fff;padding:2px 8px;border-radius:4px;">A</span> Perencanaan | Okt Pekan 3–4 | Desain UI/UX Figma (High-Fidelity), Design System | Design System & UI/UX | Desain UI/UX Final, Prototype Interaktif | <span style="background:#2563EB;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | | | |
| **3** | <span style="background:#2563EB;color:#fff;padding:2px 8px;border-radius:4px;">A</span> Integrasi SSO | Okt–Nov Pekan 4–1 | Integrasi API SSO, modul login/register, JWT Handling | Modul SSO (Keycloak, AppAuth) | Modul Login & SSO (Alpha), Network Layer | <span style="background:#2563EB;color:#fff;padding:2px 8px;border-radius:4px 0 0 4px;">■■</span> | <span style="background:#2563EB;color:#fff;padding:2px 8px;border-radius:0 4px 4px 0;">■■</span> | | |
| **4** | <span style="background:#2563EB;color:#fff;padding:2px 8px;border-radius:4px;">A</span> Integrasi SSO | Nov Pekan 1–2 | Manajemen sesi, EncryptedSharedPreferences, refresh token | Modul Keamanan Sesi & Token | Modul Sesi & Keamanan, Auto-Login | | <span style="background:#2563EB;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | | |
| **5** | <span style="background:#16A34A;color:#fff;padding:2px 8px;border-radius:4px;">B</span> Core Features | Nov Pekan 2–3 | Dashboard utama, navigasi (Bottom Nav/Drawer) | Modul Dashboard & Navigasi | Dashboard & Navigasi, Komponen UI | | <span style="background:#16A34A;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | | |
| **6** | <span style="background:#16A34A;color:#fff;padding:2px 8px;border-radius:4px;">B</span> Core Features | Nov Pekan 3–4 | Modul layanan utama: profil warga, riwayat akses, layanan instansi | Modul Profil, Riwayat, Layanan | Modul Profil, Riwayat Akses, Layanan v1 | | <span style="background:#16A34A;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | | |
| **7** | <span style="background:#16A34A;color:#fff;padding:2px 8px;border-radius:4px;">B</span> Core Features | Nov–Des Pekan 4–1 | Push notification (FCM), pengaturan akun & preferensi | Modul Notifikasi (FCM) & Akun | Modul Notifikasi & Pengaturan Akun | | <span style="background:#16A34A;color:#fff;padding:2px 8px;border-radius:4px 0 0 4px;">■■</span> | <span style="background:#16A34A;color:#fff;padding:2px 8px;border-radius:0 4px 4px 0;">■■</span> | |
| **8** | <span style="background:#16A34A;color:#fff;padding:2px 8px;border-radius:4px;">B</span> Core Features | Des Pekan 1–2 | Offline caching (Local DB), optimasi performa | Modul Cache Offline & Core | Local DB, Optimasi Performa | | | <span style="background:#16A34A;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | |
| **9** | <span style="background:#EA580C;color:#fff;padding:2px 8px;border-radius:4px;">C</span> Testing | Des Pekan 2–3 | Alpha testing internal, penyusunan test case, bug fixing | Alpha Release Build | Test Case (50+ skenario), APK Alpha, Laporan Bug | | | <span style="background:#EA580C;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | |
| **10** | <span style="background:#EA580C;color:#fff;padding:2px 8px;border-radius:4px;">C</span> Testing | Des Pekan 3–4 | UAT bersama klien Jombang, perbaikan dari feedback | Beta Release Build (UAT) | BA UAT, Evaluasi Perbaikan, APK Beta | | | <span style="background:#EA580C;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> | |
| **11** | <span style="background:#EA580C;color:#fff;padding:2px 8px;border-radius:4px;">C</span> Deployment | Des–Jan Pekan 4–1 | ToT (Training of Trainer), finalisasi build Release Candidate | Release Candidate Build | Laporan ToT, Panduan Penggunaan, APK RC | | | <span style="background:#EA580C;color:#fff;padding:2px 8px;border-radius:4px 0 0 4px;">■■</span> | <span style="background:#EA580C;color:#fff;padding:2px 8px;border-radius:0 4px 4px 0;">■■</span> |
| **12** | <span style="background:#EA580C;color:#fff;padding:2px 8px;border-radius:4px;">C</span> Deployment | Jan Pekan 1–2 | Submission Play Store, serah terima, BAST | Production Release | Aplikasi Live, Dokumentasi Akhir, BAST | | | | <span style="background:#EA580C;color:#fff;padding:2px 12px;border-radius:4px;">■■■</span> |

### Visualisasi Progress per Bulan

| **Bulan** | **W1** | **W2** | **W3** | **W4** | **Milestone Utama** |
| --- | --- | --- | --- | --- | --- |
| **Bulan 1** (Okt–Nov) | <span style="background:#2563EB;color:#fff;padding:2px 6px;border-radius:4px;">A</span> Kick-off & KAK | <span style="background:#2563EB;color:#fff;padding:2px 6px;border-radius:4px;">A</span> Desain UI/UX | <span style="background:#2563EB;color:#fff;padding:2px 6px;border-radius:4px;">A</span> Integrasi SSO | <span style="background:#2563EB;color:#fff;padding:2px 6px;border-radius:4px;">A</span> Manajemen Sesi | [v] Autentikasi SSO Mobile berjalan |
| **Bulan 2** (Nov–Des) | <span style="background:#16A34A;color:#fff;padding:2px 6px;border-radius:4px;">B</span> Dashboard | <span style="background:#16A34A;color:#fff;padding:2px 6px;border-radius:4px;">B</span> Modul Layanan | <span style="background:#16A34A;color:#fff;padding:2px 6px;border-radius:4px;">B</span> Notifikasi | <span style="background:#16A34A;color:#fff;padding:2px 6px;border-radius:4px;">B</span> Offline Cache | [v] Seluruh fitur utama selesai |
| **Bulan 3** (Des–Jan) | <span style="background:#EA580C;color:#fff;padding:2px 6px;border-radius:4px;">C</span> Alpha Test | <span style="background:#EA580C;color:#fff;padding:2px 6px;border-radius:4px;">C</span> UAT Klien | <span style="background:#EA580C;color:#fff;padding:2px 6px;border-radius:4px;">C</span> ToT & Build Final | <span style="background:#EA580C;color:#fff;padding:2px 6px;border-radius:4px;">C</span> Rilis & BAST | [v] Aplikasi live & proyek serah terima |

---

> **Catatan Diskusi: Strategi Integrasi WebView & SSO Keycloak**
> Terkait mekanisme saat user mengklik icon layanan (misal: MKJU) dan diarahkan ke web-app, terdapat 2 opsi arsitektur agar sesi SSO tidak terputus (tidak perlu login ulang):
> 
> *   **Opsi 1 (Direkomendasikan) — Chrome Custom Tabs (CCT):** Alih-alih menggunakan WebView biasa, layanan dibuka menggunakan CCT. Karena berbagi *cookie jar* yang sama dengan Chrome (tempat login SSO di awal), sesi Keycloak otomatis terbaca. Ini adalah *best practice* keamanan standar tanpa perlu modifikasi backend layanan.
> *   **Opsi 2 (Alternatif) — Token Exchange / One-Time Ticket:** Jika tampilan diwajibkan menggunakan WebView murni (tanpa header address bar sama sekali), diperlukan pengembangan mekanisme pertukaran token. Backend JOSS akan menukar *Access Token* dengan URL tiket sekali pakai, yang kemudian di-load oleh WebView untuk membuat sesi baru di dalam layanan. Membutuhkan penyesuaian API tambahan.

---

### [FASE 1] BULAN 1 — Perencanaan, Integrasi API, & Autentikasi SSO Mobile

> **Fokus:** Menyiapkan pondasi aplikasi dan melakukan integrasi core SSO ke platform mobile (Android & iOS).

---

#### III.I — Minggu 1: Kick-off & Setup Proyek

| **Item**       | **Detail**                                                                                                                                                                  |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-2/ke-3 Oktober 2026                                                                                                                                               |
| **Aktivitas**  | - Koordinasi internal tim & kick-off meeting bersama klien Jombang <br> - Finalisasi KAK (Kerangka Acuan Kerja) <br> - Setup arsitektur proyek Flutter (Android & iOS, repository, CI/CD pipeline, code convention) <br> - Review dan mapping endpoint API dari portal web JOSS <br> - Registrasi client `joss-mobile` di Keycloak (realm `jombangkab`) <br> - Identifikasi API yang sudah ada vs API yang perlu dibangun baru <br> - Penyusunan wireframe awal |
| **Output**     | [v] Dokumen KAK Final yang disetujui kedua belah pihak <br> [v] Project Repository & Boilerplate Flutter (Dart) <br> [v] Client `joss-mobile` terdaftar di Keycloak <br> [v] Dokumen Gap Analysis API (existing vs required) <br> [v] Wireframe UI/UX (Low-Fidelity) |
| **PIC**        | Project Manager, Lead Developer, UI/UX Designer                                                                                                                             |

---

#### III.II — Minggu 2: Desain UI/UX & Prototyping

| **Item**       | **Detail**                                                                                                                                                                                            |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-3/ke-4 Oktober 2026                                                                                                                                                                         |
| **Aktivitas**  | - Finalisasi desain UI/UX di Figma (High-Fidelity) untuk seluruh halaman utama <br> - Desain halaman: Splash Screen, Onboarding, Login/Register, Lupa Password, Dashboard, Profil Pengguna <br> - Penyusunan Design System (warna, tipografi, komponen reusable) <br> - Review & approval desain oleh klien |
| **Output**     | [v] Dokumen Desain UI/UX Final (Figma Link) — disetujui klien <br> [v] Design System / Style Guide Aplikasi <br> [v] Prototype Interaktif (Clickable Prototype)                                          |
| **PIC**        | UI/UX Designer, Project Manager                                                                                                                                                                       |

---

#### III.III — Minggu 3: Integrasi Autentikasi SSO & API Core

| **Item**       | **Detail**                                                                                                                                                                                                                                |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-4 Oktober / Pekan ke-1 November 2026                                                                                                                                                                                            |
| **Aktivitas**  | - Implementasi autentikasi via **Keycloak OIDC + PKCE** menggunakan library **flutter_appauth** <br> - Flow: Login → In-App Browser → Keycloak → Redirect URI → Access Token <br> - Integrasi endpoint Keycloak realm `jombangkab` (token, userinfo, logout) <br> - Implementasi **JWT Token Handling**: penyimpanan, parsing, dan validasi token <br> - Setup **Dio/HTTP** + Interceptor untuk auto-attach Bearer token <br> - Pengembangan **API backend tambahan** yang belum tersedia untuk mobile |
| **Output**     | [v] Modul Login via Keycloak OIDC+PKCE berjalan <br> [v] Register & Lupa Password via Keycloak flow <br> [v] Network Layer (Dio / HTTP Interceptor) terkonfigurasi <br> [v] API backend tambahan untuk mobile (v1) <br> [v] Unit Test untuk modul autentikasi                                 |
| **PIC**        | Lead Developer, Backend Developer (support)                                                                                                                                                                                                |

---

#### III.IV — Minggu 4: Manajemen Sesi & Keamanan Akses

| **Item**       | **Detail**                                                                                                                                                                                                                    |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-1/ke-2 November 2026                                                                                                                                                                                                |
| **Aktivitas**  | - Implementasi **Flutter Secure Storage** untuk penyimpanan token & kredensial yang aman <br> - Implementasi fitur **Auto-Login** (persistent session) <br> - Implementasi fitur **Logout** (clear token, revoke session di server) <br> - Implementasi mekanisme **Refresh Token** otomatis <br> - Penanganan error & expired token (redirect ke halaman login) |
| **Output**     | [v] Modul Manajemen Sesi & Keamanan Akses lengkap <br> [v] Fitur Auto-Login & Persistent Session <br> [v] Mekanisme Refresh Token otomatis <br> [v] Secure Storage untuk data sensitif                                              |
| **PIC**        | Lead Developer, Security Reviewer                                                                                                                                                                                              |

---

### [FASE 2] BULAN 2 — Pengembangan Fitur Utama & Integrasi Layanan (Core Features)

> **Fokus:** Membangun fungsionalitas utama aplikasi dan mengintegrasikan modul-modul turunan SSO.

---

#### III.V — Minggu 5: Dashboard & Navigasi Utama

| **Item**       | **Detail**                                                                                                                                                                                                     |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-2/ke-3 November 2026                                                                                                                                                                                 |
| **Aktivitas**  | - Pengembangan halaman **Dashboard Utama** setelah login berhasil <br> - Implementasi **Bottom Navigation / Drawer Navigation** <br> - Integrasi data ringkasan (summary cards, statistik, atau quick-access menu) <br> - Implementasi **pull-to-refresh** dan loading state |
| **Output**     | [v] Halaman Dashboard Utama aplikasi <br> [v] Sistem Navigasi Aplikasi (Bottom Nav / Drawer) <br> [v] Komponen UI reusable (cards, lists, loading indicators)                                                       |
| **PIC**        | Flutter Developer, UI/UX Designer                                                                                                                                                                               |

---

#### III.VI — Minggu 6: Modul Fitur Layanan Utama

| **Item**       | **Detail**                                                                                                                                                                                                                                                          |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-3/ke-4 November 2026                                                                                                                                                                                                                                      |
| **Aktivitas**  | - Pengembangan modul layanan utama sesuai kebutuhan Jombang, meliputi: <br> &nbsp;&nbsp;• **Profil Warga/Pengguna** (view & edit profil, upload foto) <br> &nbsp;&nbsp;• **Riwayat Akses/Aktivitas** pengguna <br> &nbsp;&nbsp;• **Integrasi Layanan Instansi** terkait (jika ada endpoint layanan publik) <br> - Integrasi API layanan dengan error handling yang proper |
| **Output**     | [v] Modul Profil Pengguna (View, Edit, Upload Foto) <br> [v] Modul Riwayat Akses / Log Aktivitas <br> [v] Modul Layanan Instansi (Versi 1) <br> [v] Integrasi API Layanan berjalan                                                                                       |
| **PIC**        | Flutter Developer, Backend Developer (support API)                                                                                                                                                                                                                   |

---

#### III.VII — Minggu 7: Push Notification & Pengaturan Akun

| **Item**       | **Detail**                                                                                                                                                                                                                                               |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-4 November / Pekan ke-1 Desember 2026                                                                                                                                                                                                           |
| **Aktivitas**  | - Integrasi **Firebase Cloud Messaging (FCM)** untuk push notification <br> - Implementasi notifikasi: pengumuman, update layanan, dan reminder <br> - Pengembangan halaman **Pengaturan Akun** (ubah password, pengaturan notifikasi, bahasa, tema) <br> - Implementasi **in-app notification center** (daftar notifikasi yang diterima) |
| **Output**     | [v] Modul Push Notification (FCM) terintegrasi dan berfungsi <br> [v] In-App Notification Center <br> [v] Halaman Pengaturan Akun Pengguna <br> [v] Pengaturan preferensi notifikasi                                                                            |
| **PIC**        | Flutter Developer, Backend Developer (FCM setup)                                                                                                                                                                                                          |

---

#### III.VIII — Minggu 8: Offline Caching & Optimasi

| **Item**       | **Detail**                                                                                                                                                                                                                                                              |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-1/ke-2 Desember 2026                                                                                                                                                                                                                                          |
| **Aktivitas**  | - Implementasi **Local Database** (sqflite / Hive) untuk offline caching data penting <br> - Optimasi performa aplikasi: memory, network call, dan battery usage <br> - Implementasi **connectivity checker** (online/offline mode) |
| **Output**     | [v] Local Database & Offline Caching <br> [v] Connectivity-aware UX (indikator online/offline) <br> [v] Laporan optimasi performa aplikasi                                                                         |
| **PIC**        | Lead Developer, Flutter Developer                                                                                                                                                                                                                                        |

---

### [FASE 3] BULAN 3 — Testing, Bug Fixing, ToT, & Deployment

> **Fokus:** Pengujian menyeluruh, perbaikan bug, pelatihan pengguna, dan publikasi aplikasi.

---

#### III.IX — Minggu 9: Alpha Testing & Bug Fixing

| **Item**       | **Detail**                                                                                                                                                                                                                                                    |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-2/ke-3 Desember 2026                                                                                                                                                                                                                                |
| **Aktivitas**  | - Pelaksanaan **Internal/Alpha Testing** oleh tim pengembang <br> - Penyusunan **Test Case Document** & skenario UAT <br> - Identifikasi dan perbaikan bug (critical & major) <br> - Testing kompatibilitas di berbagai perangkat Android & iOS <br> - Security testing dasar (token exposure, data leakage) |
| **Output**     | [v] Dokumen Test Case (minimal 50 skenario) <br> [v] Laporan Bug Fixing (Critical & Major resolved) <br> [v] APK/IPA Internal Build (Alpha) untuk distribusi testing <br> [v] Laporan Compatibility Testing                                                              |
| **PIC**        | QA Tester, Lead Developer, Seluruh Tim Dev                                                                                                                                                                                                                     |

---

#### III.X — Minggu 10: UAT & Penyempurnaan Aplikasi

| **Item**       | **Detail**                                                                                                                                                                                                                                                                       |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-3/ke-4 Desember 2026                                                                                                                                                                                                                                                   |
| **Aktivitas**  | - Pelaksanaan **User Acceptance Testing (UAT)** bersama tim/klien Jombang <br> - Pengumpulan feedback dan catatan evaluasi dari pengguna <br> - Penyempurnaan UI/UX berdasarkan hasil UAT <br> - Perbaikan bug minor yang ditemukan saat UAT <br> - Persiapan **materi ToT** (Training of Trainer): modul panduan, video tutorial singkat |
| **Output**     | [v] Berita Acara (BA) Pelaksanaan UAT — ditandatangani kedua pihak <br> [v] Dokumen Catatan Evaluasi & Perbaikan UAT <br> [v] APK/IPA Build (Beta — Post-UAT) <br> [v] Draft Modul Panduan Penggunaan Aplikasi                                                                             |
| **PIC**        | Project Manager, QA Tester, Tim Dev, Perwakilan Klien                                                                                                                                                                                                                            |

---

#### III.XI — Minggu 11: Training of Trainer (ToT) & Finalisasi Build

| **Item**       | **Detail**                                                                                                                                                                                                                                                                     |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Periode**    | Pekan ke-4 Desember 2026 / Pekan ke-1 Januari 2027                                                                                                                                                                                                                            |
| **Aktivitas**  | - Pelaksanaan kegiatan **ToT (Training of Trainer)** untuk pengelola/admin di Jombang <br> - Materi ToT mencakup: cara instalasi, penggunaan fitur, troubleshooting dasar, dan pengelolaan akun <br> - Finalisasi build aplikasi untuk rilis (Release Candidate) <br> - Penyusunan **Dokumentasi Teknis** (arsitektur, API docs, deployment guide) |
| **Output**     | [v] Laporan Pelaksanaan ToT (daftar hadir, dokumentasi foto, materi) <br> [v] Modul Panduan Penggunaan Aplikasi (Final) <br> [v] Master App Bundle (AAB) & Master IPA (Release Candidate) <br> [v] Dokumentasi Teknis Aplikasi                                                                     |
| **PIC**        | Project Manager, Lead Developer, Trainer                                                                                                                                                                                                                                        |

---

#### III.XII — Minggu 12: Deployment, Serah Terima, & Penutupan Proyek

| **Item**       | **Detail**                                                                                                                                                                                                                                                                                                             |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-1/ke-2 Januari 2027                                                                                                                                                                                                                                                                                          |
| **Aktivitas**  | - Proses **submission ke Google Play Store & Apple App Store** (atau distribusi internal MDM instansi) <br> - Monitoring pasca-rilis (crash reporting via Firebase Crashlytics) <br> - Penyusunan dokumen penutupan proyek <br> - Penandatanganan **Berita Acara Serah Terima (BAST)** <br> - Handover source code, dokumentasi, dan akses repository ke pihak Jombang |
| **Output**     | [v] Aplikasi JOSS Mobile tayang di Play Store & App Store <br> [v] Dokumentasi Teknis Akhir (Source Code, API Docs, Deployment Guide) <br> [v] Berita Acara Serah Terima (BAST) — ditandatangani kedua pihak <br> [v] Handover seluruh aset proyek                                                                  |
| **PIC**        | Project Manager, Lead Developer, Perwakilan Klien                                                                                                                                                                                                                                                                       |

---

## IV. Ruang Lingkup Teknis — Apa yang Harus Dikerjakan Tim

Mengingat **portal web JOSS dan SSO Keycloak dari Fase 1 sudah live**, berikut adalah fokus teknis untuk Fase 2:

### 1. Keycloak SSO Integration (Mobile)
- Registrasi client baru `joss-mobile` di Keycloak realm `jombangkab` (public client, PKCE enabled)
- Implementasi **OAuth2 Authorization Code + PKCE** flow menggunakan **flutter_appauth**
- Login via **Chrome Custom Tab** → Keycloak login page → redirect URI → access token
- Endpoint yang digunakan:
  - Token: `https://sso-v2.jombangkab.go.id/realms/jombangkab/protocol/openid-connect/token`
  - UserInfo: `https://sso-v2.jombangkab.go.id/realms/jombangkab/protocol/openid-connect/userinfo`
  - Logout: `https://sso-v2.jombangkab.go.id/realms/jombangkab/protocol/openid-connect/logout`
- Implementasi mekanisme **Refresh Token** otomatis
- Setup **Retrofit + OkHttp Interceptor** untuk auto-attach Bearer token

### 2. Pengembangan API Backend Tambahan (Baru)
API berikut **belum tersedia** dari portal web dan **perlu dibangun baru** untuk mendukung aplikasi mobile:

| **No** | **API Endpoint** | **Method** | **Fungsi** |
| --- | --- | --- | --- |
| 1 | `/api/v1/mobile/profile` | GET, PUT | Data profil pengguna (nama, email, foto, NIK) |
| 2 | `/api/v1/mobile/profile/photo` | POST | Upload foto profil |
| 3 | `/api/v1/mobile/layanan` | GET | Daftar layanan (mirror dari `/api/layanan` web) |
| 4 | `/api/v1/mobile/layanan/{id}` | GET | Detail layanan spesifik |
| 5 | `/api/v1/mobile/kategori` | GET | Daftar kategori layanan |
| 6 | `/api/v1/mobile/riwayat` | GET | Riwayat akses/aktivitas pengguna |
| 7 | `/api/v1/mobile/notifikasi` | GET, PUT | Daftar notifikasi & tandai sudah dibaca |
| 8 | `/api/v1/mobile/notifikasi/register` | POST | Register FCM token untuk push notification |
| 9 | `/api/v1/mobile/kyc/status` | GET | Cek status verifikasi KYC akun |
| 10 | `/api/v1/mobile/app-version` | GET | Cek versi terbaru aplikasi (force update) |


### 3. Mobile Security
- **EncryptedSharedPreferences** untuk penyimpanan token & data sensitif
- **Certificate Pinning** (opsional, untuk keamanan komunikasi HTTPS)
- **ProGuard/R8** obfuscation untuk proteksi APK

### 4. Mobile-Specific Features
- **Push Notification** via Firebase Cloud Messaging (FCM)
- **Offline Caching** menggunakan Room Database / SQLite
- **Connectivity Checker** untuk mode online/offline
- **Deep Linking** untuk navigasi dari notifikasi atau link eksternal
- **In-App WebView** untuk membuka layanan instansi yang belum punya native screen

### 5. UI/UX Adaptation (Mirror Portal Web)
- Adaptasi layout portal web JOSS ke mobile-friendly design
- Implementasi **Material Design 3** guidelines
- Halaman utama: Katalog layanan dengan kategori (Kepegawaian, Ketenagakerjaan, Layanan Publik)
- Search layanan dengan debounce (seperti di web)
- Animasi transisi halaman yang smooth
- Dark Mode support (opsional)

---

## V. Daftar Deliverables / Output Utama Proyek

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

## VI. Catatan & Risiko

| **Risiko**                                     | **Mitigasi**                                                                  |
| ---------------------------------------------- | ----------------------------------------------------------------------------- |
| Keterlambatan finalisasi KAK                   | Paralel dengan setup teknis di Minggu 1                                       |
| Perubahan requirement di tengah proyek         | Change Request formal dengan impact analysis                                  |
| Kompatibilitas perangkat Android & iOS beragam       | Testing di minimal 5 perangkat berbeda (iOS & Android)                            |
| Kendala submission Play Store & App Store           | Persiapan akun developer & compliance sejak Minggu 9                          |
| Ketergantungan pada stabilitas API SSO Fase 1  | Monitoring uptime API & koordinasi rutin dengan tim backend                   |

---

> **Dokumen ini disusun sebagai acuan jadwal dan output pengembangan aplikasi JOSS Mobile (Fase 2) untuk Proyek SSO Kabupaten Jombang. Jadwal bersifat fleksibel dan dapat disesuaikan berdasarkan kesepakatan bersama antara tim pengembang dan pihak Kabupaten Jombang.**

---

*Disusun oleh: Tim Pengembang SSO Jombang*
*Tanggal: September 2026*
