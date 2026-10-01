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
| **Portal Web (Fase 1)**     | ✅ Live — https://joss.jombangkab.go.id                                  |
| **SSO Server**              | Keycloak — https://sso-v2.jombangkab.go.id (Realm: `jombangkab`)          |
| **Protokol Autentikasi**    | OAuth2 / OpenID Connect (Authorization Code Flow)                          |

---
---




## II. Rincian Jadwal & Output per Minggu

### Ringkasan Timeline (Gantt Chart Overview)

### Tabel Ringkasan per Fase

| **Fase** | **Minggu (Durasi)** | **Fokus Utama** |
| --- | --- | --- |
| **FASE A:** Perencanaan & Integrasi API/SSO | 1–4 (4 Minggu) | Setup proyek, desain UI/UX, integrasi autentikasi SSO |
| **FASE B:** Pengembangan Fitur Utama & Layanan | 5–8 (4 Minggu) | Dashboard, modul layanan, notifikasi, offline cache |
| **FASE C:** Testing, ToT, & Deployment | 9–12 (4 Minggu) | Alpha/UAT testing, pelatihan, rilis & serah terima |

### Tabel Detail Gantt Chart — 12 Minggu

| **Fase / Periode** | **Aktivitas & Modul** | **Okt** | **Nov** | **Des** | **Jan** |
| --- | --- | --- | --- | --- | --- |
| <span style="color:#2563EB;">**[A]**</span><br>Okt Pekan 2–3 | Kick-off, finalisasi KAK, setup repo & arsitektur <br> *(Arsitektur Dasar & Boilerplate)* | <span style="color:#2563EB;">███</span> |  |  |  |
| <span style="color:#2563EB;">**[A]**</span><br>Okt Pekan 3–4 | Desain UI/UX Figma (High-Fidelity), Design System <br> *(Design System & UI/UX)* | <span style="color:#2563EB;">███</span> |  |  |  |
| <span style="color:#2563EB;">**[A]**</span><br>Okt–Nov Pekan 4–1 | Integrasi API SSO, modul login/register, JWT Handling <br> *(Modul SSO (Keycloak, AppAuth))* | <span style="color:#2563EB;">██</span> | <span style="color:#2563EB;">██</span> |  |  |
| <span style="color:#2563EB;">**[A]**</span><br>Nov Pekan 1–2 | Manajemen sesi, EncryptedSharedPreferences, refresh token <br> *(Modul Keamanan Sesi & Token)* <br> <span style="color:#2563EB;">**• Review Progress Akhir Fase A**</span> |  | <span style="color:#2563EB;">███</span> |  |  |
| <span style="color:#16A34A;">**[B]**</span><br>Nov Pekan 2–3 | Dashboard utama, navigasi (Bottom Nav/Drawer) <br> *(Modul Dashboard & Navigasi)* |  | <span style="color:#16A34A;">███</span> |  |  |
| <span style="color:#16A34A;">**[B]**</span><br>Nov Pekan 3–4 | Modul layanan utama: profil warga, riwayat akses, layanan instansi <br> *(Modul Profil, Riwayat, Layanan)* |  | <span style="color:#16A34A;">███</span> |  |  |
| <span style="color:#16A34A;">**[B]**</span><br>Nov–Des Pekan 4–1 | Push notification (FCM), pengaturan akun & preferensi <br> *(Modul Notifikasi (FCM) & Akun)* |  | <span style="color:#16A34A;">██</span> | <span style="color:#16A34A;">██</span> |  |
| <span style="color:#16A34A;">**[B]**</span><br>Des Pekan 1–2 | Offline caching (Local DB), optimasi performa <br> *(Modul Cache Offline & Core)* <br> <span style="color:#16A34A;">**• Review Progress Akhir Fase B**</span> |  |  | <span style="color:#16A34A;">███</span> |  |
| <span style="color:#EA580C;">**[C]**</span><br>Des Pekan 2–3 | Alpha testing internal, penyusunan test case, bug fixing <br> *(Alpha Release Build)* |  |  | <span style="color:#EA580C;">███</span> |  |
| <span style="color:#EA580C;">**[C]**</span><br>Des Pekan 3–4 | UAT bersama klien Jombang, perbaikan dari feedback <br> *(Beta Release Build (UAT))* |  |  | <span style="color:#EA580C;">███</span> |  |
| <span style="color:#EA580C;">**[C]**</span><br>Des–Jan Pekan 4–1 | ToT (Training of Trainer), finalisasi build Release Candidate <br> *(Release Candidate Build)* |  |  | <span style="color:#EA580C;">██</span> | <span style="color:#EA580C;">██</span> |
| <span style="color:#EA580C;">**[C]**</span><br>Jan Pekan 1–2 | Submission Play Store, serah terima, BAST <br> *(Production Release)* <br> <span style="color:#EA580C;">**• Final Review & Penutupan Proyek**</span> |  |  |  | <span style="color:#EA580C;">███</span> |

### Visualisasi Progress per Bulan

| **Bulan** | **W1** | **W2** | **W3** | **W4** | **Milestone Utama** |
| --- | --- | --- | --- | --- | --- |
| **Bulan 1** (Okt–Nov) | <span style="color:#2563EB; font-weight:bold;">[A]</span> Kick-off & KAK | <span style="color:#2563EB; font-weight:bold;">[A]</span> Desain UI/UX | <span style="color:#2563EB; font-weight:bold;">[A]</span> Integrasi SSO | <span style="color:#2563EB; font-weight:bold;">[A]</span> Manajemen Sesi | ✅ Autentikasi SSO Mobile berjalan |
| **Bulan 2** (Nov–Des) | <span style="color:#16A34A; font-weight:bold;">[B]</span> Dashboard | <span style="color:#16A34A; font-weight:bold;">[B]</span> Modul Layanan | <span style="color:#16A34A; font-weight:bold;">[B]</span> Notifikasi | <span style="color:#16A34A; font-weight:bold;">[B]</span> Offline Cache | ✅ Seluruh fitur utama selesai |
| **Bulan 3** (Des–Jan) | <span style="color:#EA580C; font-weight:bold;">[C]</span> Alpha Test | <span style="color:#EA580C; font-weight:bold;">[C]</span> UAT Klien | <span style="color:#EA580C; font-weight:bold;">[C]</span> ToT & Build Final | <span style="color:#EA580C; font-weight:bold;">[C]</span> Rilis & BAST | ✅ Aplikasi live & proyek serah terima |

---

### [FASE 1] BULAN 1 — Perencanaan, Integrasi API, & Autentikasi SSO Mobile

> **Fokus:** Menyiapkan pondasi aplikasi dan melakukan integrasi core SSO ke platform mobile (Android & iOS).

---

#### II.I — Minggu 1: Kick-off & Setup Proyek

| **Item**       | **Detail**                                                                                                                                                                  |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-2/ke-3 Oktober 2026                                                                                                                                               |
| **Aktivitas**  | 🔹 Koordinasi internal tim & kick-off meeting bersama klien Jombang <br> 🔹 Finalisasi KAK (Kerangka Acuan Kerja) <br> 🔹 Setup arsitektur proyek Flutter (Android & iOS, repository, CI/CD pipeline, code convention) <br> 🔹 Review dan mapping endpoint API dari portal web JOSS <br> 🔹 Registrasi client `joss-mobile` di Keycloak (realm `jombangkab`) <br> 🔹 Identifikasi API yang sudah ada vs API yang perlu dibangun baru <br> 🔹 Penyusunan wireframe awal |
| **Output**     | ✅ Dokumen KAK Final yang disetujui kedua belah pihak <br> ✅ Project Repository & Boilerplate Flutter (Dart) <br> ✅ Client `joss-mobile` terdaftar di Keycloak <br> ✅ Dokumen Gap Analysis API (existing vs required) <br> ✅ Wireframe UI/UX (Low-Fidelity) |
| **PIC**        | Project Manager, Lead Developer, UI/UX Designer                                                                                                                             |

---

#### II.II — Minggu 2: Desain UI/UX & Prototyping

| **Item**       | **Detail**                                                                                                                                                                                            |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-3/ke-4 Oktober 2026                                                                                                                                                                         |
| **Aktivitas**  | 🔹 Finalisasi desain UI/UX di Figma (High-Fidelity) untuk seluruh halaman utama <br> 🔹 Desain halaman: Splash Screen, Onboarding, Login/Register, Lupa Password, Dashboard, Profil Pengguna <br> 🔹 Penyusunan Design System (warna, tipografi, komponen reusable) <br> 🔹 Review & approval desain oleh klien |
| **Output**     | ✅ Dokumen Desain UI/UX Final (Figma Link) — disetujui klien <br> ✅ Design System / Style Guide Aplikasi <br> ✅ Prototype Interaktif (Clickable Prototype)                                          |
| **PIC**        | UI/UX Designer, Project Manager                                                                                                                                                                       |

---

#### II.III — Minggu 3: Integrasi Autentikasi SSO & API Core

| **Item**       | **Detail**                                                                                                                                                                                                                                |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-4 Oktober / Pekan ke-1 November 2026                                                                                                                                                                                            |
| **Aktivitas**  | 🔹 Implementasi autentikasi via **Keycloak OIDC + PKCE** menggunakan library **flutter_appauth** <br> 🔹 Flow: Login → In-App Browser → Keycloak → Redirect URI → Access Token <br> 🔹 Integrasi endpoint Keycloak realm `jombangkab` (token, userinfo, logout) <br> 🔹 Implementasi **JWT Token Handling**: penyimpanan, parsing, dan validasi token <br> 🔹 Setup **Dio/HTTP** + Interceptor untuk auto-attach Bearer token <br> 🔹 Pengembangan **API backend tambahan** yang belum tersedia untuk mobile |
| **Output**     | ✅ Modul Login via Keycloak OIDC+PKCE berjalan <br> ✅ Register & Lupa Password via Keycloak flow <br> ✅ Network Layer (Dio / HTTP Interceptor) terkonfigurasi <br> ✅ API backend tambahan untuk mobile (v1) <br> ✅ Unit Test untuk modul autentikasi                                 |
| **PIC**        | Lead Developer, Backend Developer (support)                                                                                                                                                                                                |

---

#### II.IV — Minggu 4: Manajemen Sesi & Keamanan Akses

| **Item**       | **Detail**                                                                                                                                                                                                                    |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-1/ke-2 November 2026                                                                                                                                                                                                |
| **Aktivitas**  | 🔹 Implementasi **Flutter Secure Storage** untuk penyimpanan token & kredensial yang aman <br> 🔹 Implementasi fitur **Auto-Login** (persistent session) <br> 🔹 Implementasi fitur **Logout** (clear token, revoke session di server) <br> 🔹 Implementasi mekanisme **Refresh Token** otomatis <br> 🔹 Penanganan error & expired token (redirect ke halaman login) <br> 🔹 **Review Progress Akhir Fase A bersama Klien** |
| **Output**     | ✅ Modul Manajemen Sesi & Keamanan Akses lengkap <br> ✅ Fitur Auto-Login & Persistent Session <br> ✅ Mekanisme Refresh Token otomatis <br> ✅ Secure Storage untuk data sensitif <br> ✅ Laporan Review Progress Fase A |
| **PIC**        | Lead Developer, Security Reviewer                                                                                                                                                                                              |

---

### [FASE 2] BULAN 2 — Pengembangan Fitur Utama & Integrasi Layanan (Core Features)

> **Fokus:** Membangun fungsionalitas utama aplikasi dan mengintegrasikan modul-modul turunan SSO.

---

#### II.V — Minggu 5: Dashboard & Navigasi Utama

| **Item**       | **Detail**                                                                                                                                                                                                     |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-2/ke-3 November 2026                                                                                                                                                                                 |
| **Aktivitas**  | 🔹 Pengembangan halaman **Dashboard Utama** setelah login berhasil <br> 🔹 Implementasi **Bottom Navigation / Drawer Navigation** <br> 🔹 Integrasi data ringkasan (summary cards, statistik, atau quick-access menu) <br> 🔹 Implementasi **pull-to-refresh** dan loading state |
| **Output**     | ✅ Halaman Dashboard Utama aplikasi <br> ✅ Sistem Navigasi Aplikasi (Bottom Nav / Drawer) <br> ✅ Komponen UI reusable (cards, lists, loading indicators)                                                       |
| **PIC**        | Flutter Developer, UI/UX Designer                                                                                                                                                                               |

---

#### II.VI — Minggu 6: Modul Fitur Layanan Utama

| **Item**       | **Detail**                                                                                                                                                                                                                                                          |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-3/ke-4 November 2026                                                                                                                                                                                                                                      |
| **Aktivitas**  | 🔹 Pengembangan modul layanan utama sesuai kebutuhan Jombang, meliputi: <br> &nbsp;&nbsp;• **Profil Warga/Pengguna** (view & edit profil, upload foto) <br> &nbsp;&nbsp;• **Riwayat Akses/Aktivitas** pengguna <br> &nbsp;&nbsp;• **Integrasi Layanan Instansi** terkait (jika ada endpoint layanan publik) <br> 🔹 Integrasi API layanan dengan error handling yang proper |
| **Output**     | ✅ Modul Profil Pengguna (View, Edit, Upload Foto) <br> ✅ Modul Riwayat Akses / Log Aktivitas <br> ✅ Modul Layanan Instansi (Versi 1) <br> ✅ Integrasi API Layanan berjalan                                                                                       |
| **PIC**        | Flutter Developer, Backend Developer (support API)                                                                                                                                                                                                                   |

---

#### II.VII — Minggu 7: Push Notification & Pengaturan Akun

| **Item**       | **Detail**                                                                                                                                                                                                                                               |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-4 November / Pekan ke-1 Desember 2026                                                                                                                                                                                                           |
| **Aktivitas**  | 🔹 Integrasi **Firebase Cloud Messaging (FCM)** untuk push notification <br> 🔹 Implementasi notifikasi: pengumuman, update layanan, dan reminder <br> 🔹 Pengembangan halaman **Pengaturan Akun** (ubah password, pengaturan notifikasi, bahasa, tema) <br> 🔹 Implementasi **in-app notification center** (daftar notifikasi yang diterima) |
| **Output**     | ✅ Modul Push Notification (FCM) terintegrasi dan berfungsi <br> ✅ In-App Notification Center <br> ✅ Halaman Pengaturan Akun Pengguna <br> ✅ Pengaturan preferensi notifikasi                                                                            |
| **PIC**        | Flutter Developer, Backend Developer (FCM setup)                                                                                                                                                                                                          |

---

#### II.VIII — Minggu 8: Offline Caching & Optimasi

| **Item**       | **Detail**                                                                                                                                                                                                                                                              |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-1/ke-2 Desember 2026                                                                                                                                                                                                                                          |
| **Aktivitas**  | 🔹 Implementasi **Local Database** (sqflite / Hive) untuk offline caching data penting <br> 🔹 Optimasi performa aplikasi: memory, network call, dan battery usage <br> 🔹 Implementasi **connectivity checker** (online/offline mode) <br> 🔹 **Review Progress Akhir Fase B bersama Klien** |
| **Output**     | ✅ Local Database & Offline Caching <br> ✅ Connectivity-aware UX (indikator online/offline) <br> ✅ Laporan optimasi performa aplikasi <br> ✅ Laporan Review Progress Fase B |
| **PIC**        | Lead Developer, Flutter Developer                                                                                                                                                                                                                                        |

---

### [FASE 3] BULAN 3 — Testing, Bug Fixing, ToT, & Deployment

> **Fokus:** Pengujian menyeluruh, perbaikan bug, pelatihan pengguna, dan publikasi aplikasi.

---

#### II.IX — Minggu 9: Alpha Testing & Bug Fixing

| **Item**       | **Detail**                                                                                                                                                                                                                                                    |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-2/ke-3 Desember 2026                                                                                                                                                                                                                                |
| **Aktivitas**  | 🔹 Pelaksanaan **Internal/Alpha Testing** oleh tim pengembang <br> 🔹 Penyusunan **Test Case Document** & skenario UAT <br> 🔹 Identifikasi dan perbaikan bug (critical & major) <br> 🔹 Testing kompatibilitas di berbagai perangkat Android & iOS <br> 🔹 Security testing dasar (token exposure, data leakage) |
| **Output**     | ✅ Dokumen Test Case (minimal 50 skenario) <br> ✅ Laporan Bug Fixing (Critical & Major resolved) <br> ✅ APK/IPA Internal Build (Alpha) untuk distribusi testing <br> ✅ Laporan Compatibility Testing                                                              |
| **PIC**        | QA Tester, Lead Developer, Seluruh Tim Dev                                                                                                                                                                                                                     |

---

#### II.X — Minggu 10: UAT & Penyempurnaan Aplikasi

| **Item**       | **Detail**                                                                                                                                                                                                                                                                       |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-3/ke-4 Desember 2026                                                                                                                                                                                                                                                   |
| **Aktivitas**  | 🔹 Pelaksanaan **User Acceptance Testing (UAT)** bersama tim/klien Jombang <br> 🔹 Pengumpulan feedback dan catatan evaluasi dari pengguna <br> 🔹 Penyempurnaan UI/UX berdasarkan hasil UAT <br> 🔹 Perbaikan bug minor yang ditemukan saat UAT <br> 🔹 Persiapan **materi ToT** (Training of Trainer): modul panduan, video tutorial singkat |
| **Output**     | ✅ Berita Acara (BA) Pelaksanaan UAT — ditandatangani kedua pihak <br> ✅ Dokumen Catatan Evaluasi & Perbaikan UAT <br> ✅ APK/IPA Build (Beta — Post-UAT) <br> ✅ Draft Modul Panduan Penggunaan Aplikasi                                                                             |
| **PIC**        | Project Manager, QA Tester, Tim Dev, Perwakilan Klien                                                                                                                                                                                                                            |

---

#### II.XI — Minggu 11: Training of Trainer (ToT) & Finalisasi Build

| **Item**       | **Detail**                                                                                                                                                                                                                                                                     |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Periode**    | Pekan ke-4 Desember 2026 / Pekan ke-1 Januari 2027                                                                                                                                                                                                                            |
| **Aktivitas**  | 🔹 Pelaksanaan kegiatan **ToT (Training of Trainer)** untuk pengelola/admin di Jombang <br> 🔹 Materi ToT mencakup: cara instalasi, penggunaan fitur, troubleshooting dasar, dan pengelolaan akun <br> 🔹 Finalisasi build aplikasi untuk rilis (Release Candidate) <br> 🔹 Penyusunan **Dokumentasi Teknis** (arsitektur, API docs, deployment guide) |
| **Output**     | ✅ Laporan Pelaksanaan ToT (daftar hadir, dokumentasi foto, materi) <br> ✅ Modul Panduan Penggunaan Aplikasi (Final) <br> ✅ Master App Bundle (AAB) & Master IPA (Release Candidate) <br> ✅ Dokumentasi Teknis Aplikasi                                                                     |
| **PIC**        | Project Manager, Lead Developer, Trainer                                                                                                                                                                                                                                        |

---

#### II.XII — Minggu 12: Deployment, Serah Terima, & Penutupan Proyek

| **Item**       | **Detail**                                                                                                                                                                                                                                                                                                             |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Periode**    | Pekan ke-1/ke-2 Januari 2027                                                                                                                                                                                                                                                                                          |
| **Aktivitas**  | 🔹 Proses **submission ke Google Play Store & Apple App Store** (atau distribusi internal MDM instansi) <br> 🔹 Monitoring pasca-rilis (crash reporting via Firebase Crashlytics) <br> 🔹 Penyusunan dokumen penutupan proyek <br> 🔹 Penandatanganan **Berita Acara Serah Terima (BAST)** <br> 🔹 Handover source code, dokumentasi, dan akses repository ke pihak Jombang <br> 🔹 **Pelaksanaan Final Review Proyek** |
| **Output**     | ✅ Aplikasi JOSS Mobile tayang di Play Store & App Store <br> ✅ Dokumentasi Teknis Akhir (Source Code, API Docs, Deployment Guide) <br> ✅ Berita Acara Serah Terima (BAST) — ditandatangani kedua pihak <br> ✅ Handover seluruh aset proyek <br> ✅ Laporan Final Review Proyek |
| **PIC**        | Project Manager, Lead Developer, Perwakilan Klien                                                                                                                                                                                                                                                                       |

---
## III. Daftar Modul Aplikasi JOSS Mobile


Berikut adalah daftar lengkap modul yang akan dikembangkan dalam aplikasi JOSS Mobile (Fase 2):

### Autentikasi & Keamanan

| **No** | **Kode** | **Nama Modul** | **Fitur Utama** |
|---|---|---|---|
| 1 | `AUTH-01` | **Splash Screen & Onboarding** | Splash screen dengan logo JOSS, onboarding slider (first-time user) |
| 2 | `AUTH-02` | **Login** | Login via username + password, integrasi Keycloak OIDC+PKCE |
| 3 | `AUTH-03` | **Registrasi** | Form registrasi (Nama, Email, No. HP, NIK, Password), submit ke Keycloak |
| 4 | `AUTH-04` | **Verifikasi Akun** | Verifikasi email setelah registrasi, halaman status verifikasi |
| 5 | `AUTH-05` | **Lupa Password / Reset Password** | Input email → Keycloak kirim link reset → form ganti password baru |
| 6 | `AUTH-06` | **Manajemen Sesi & Token** | Auto-login, refresh token otomatis, logout (revoke session), secure storage |

### Halaman Utama

| **No** | **Kode** | **Nama Modul** | **Fitur Utama** |
|---|---|---|---|
| 7 | `HOME-01` | **Dashboard** | Halaman utama setelah login, summary cards, quick-access menu |
| 8 | `HOME-02` | **Navigasi Utama** | Bottom Navigation Bar / Drawer, routing antar halaman |

### Layanan

| **No** | **Kode** | **Nama Modul** | **Fitur Utama** |
|---|---|---|---|
| 9 | `SVC-01` | **Katalog Layanan** | Daftar layanan publik, filter kategori (Kepegawaian, Ketenagakerjaan, dll) |
| 10 | `SVC-02` | **Detail Layanan** | Halaman detail per layanan, deskripsi, syarat, dan akses |
| 11 | `SVC-03` | **Pencarian Layanan** | Search bar dengan real-time search (debounce) |
| 12 | `SVC-04` | **Akses Layanan Instansi** | Buka web-app layanan via Chrome Custom Tab / WebView |

### Profil & Akun

| **No** | **Kode** | **Nama Modul** | **Fitur Utama** |
|---|---|---|---|
| 13 | `USR-01` | **Profil Pengguna** | Lihat profil (nama, email, NIK, foto), status KYC |
| 14 | `USR-02` | **Edit Profil** | Edit data profil, upload/ganti foto profil |
| 15 | `USR-03` | **Ubah Password** | Ganti password dari dalam aplikasi |
| 16 | `USR-04` | **Verifikasi KYC** | Cek status KYC, upload dokumen KYC (jika diperlukan) |

### Notifikasi

| **No** | **Kode** | **Nama Modul** | **Fitur Utama** |
|---|---|---|---|
| 17 | `NOTIF-01` | **Push Notification** | Integrasi Firebase Cloud Messaging (FCM), register token |
| 18 | `NOTIF-02` | **Notification Center** | Daftar notifikasi in-app, tandai sudah dibaca, hapus notifikasi |

### Riwayat

| **No** | **Kode** | **Nama Modul** | **Fitur Utama** |
|---|---|---|---|
| 19 | `HIST-01` | **Riwayat Aktivitas** | Log riwayat akses/aktivitas pengguna di aplikasi |

### Pengaturan

| **No** | **Kode** | **Nama Modul** | **Fitur Utama** |
|---|---|---|---|
| 20 | `SET-01` | **Pengaturan Aplikasi** | Pengaturan notifikasi, tentang aplikasi, versi, kebijakan privasi |

### Sistem & Infrastruktur

| **No** | **Kode** | **Nama Modul** | **Fitur Utama** |
|---|---|---|---|
| 21 | `SYS-01` | **Offline Caching** | Local database (sqflite/Hive), penyimpanan data offline |
| 22 | `SYS-02` | **Connectivity Checker** | Deteksi online/offline, indikator status koneksi |
| 23 | `SYS-03` | **Force Update** | Cek versi terbaru, paksa update jika versi lama |
| 24 | `SYS-04` | **Deep Linking** | Handle link dari notifikasi/email (reset password, verifikasi) |
| 25 | `SYS-05` | **Error Handling & Crash Reporting** | Global error handler, Firebase Crashlytics |

> **Total: 25 Modul** — mencakup seluruh kebutuhan fungsional dan non-fungsional aplikasi JOSS Mobile.

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
