# Dokumentasi Arsitektur, Fitur, Dependensi, dan API (JOSS Mobile)

Dokumen ini berisi spesifikasi teknis lengkap dari aplikasi **JOSS (Jombang One Stop Service) Mobile**, mencakup pola arsitektur, manajemen *state*, enkripsi, paket *dependency*, daftar fitur, dan katalog *endpoint* API.

---

## 1. Arsitektur & Pola Desain (Architecture)

Aplikasi dibangun dengan prinsip **Clean Architecture** berorientasi fitur (*feature-first*):

1. **Presentation Layer**:
   - Berisi antarmuka pengguna (`pages` dan `widgets`) serta *Business Logic Component* (`bloc`).
   - Menerima interaksi pengguna, mengirimkan *event* ke BLoC, dan me-*render* tampilan berdasarkan *state* terkini.
   - Contoh: [`HomePage`](lib/features/home/presentation/pages/home_page.dart), [`RegisterPage`](lib/features/auth/presentation/pages/register_page.dart), [`ServicesBloc`](lib/features/services/presentation/bloc/services_bloc.dart).
2. **Domain Layer**:
   - Berisi entitas bisnis murni (`entities`) dan aturan bisnis use case (`usecases`).
   - Independen dari framework UI maupun *network client*.
   - Contoh: [`ServiceEntity`](lib/features/services/domain/entities/service_entity.dart), [`RegisterSubmissionEntity`](lib/features/daftar/domain/entities/register_submission_entity.dart).
3. **Data Layer**:
   - Mengimplementasikan kontrak repositori dari *Domain Layer* (`repositories`).
   - Bertanggung jawab mengambil dan memetakan data dari sumber eksternal (`datasources` remote via Dio dan local via secure storage) ke model DTO (`models`).
   - Contoh: [`AuthRemoteDataSourceImpl`](lib/features/auth/data/datasources/auth_remote_data_source.dart), [`ServicesRepositoryImpl`](lib/features/services/data/repositories/services_repository_impl.dart).
4. **Dependency Injection**:
   - Menggunakan [`get_it`](lib/core/di/injection.dart) dan [`injectable`](lib/core/di/register_module.dart) untuk registrasi *singleton*, *factory*, dan modul eksternal secara otomatis melalui *code generation*.
5. **Functional Error Handling**:
   - Menggunakan tipe data `Either<Failure, T>` dari paket `fpdart` untuk menangani *error* secara deklaratif tanpa *runtime unhandled exceptions*.
6. **In-App Webview SSO Gateway**:
   - Layanan web eksternal dibuka menggunakan `flutter_inappwebview` dengan injeksi *bearer token* SSO aktif (`/mobile?token=<access_token>`) saat `authBypassMobile` bernilai `true`.

---

## 2. State Management

Manajemen *state* di seluruh aplikasi dikelola secara terpusat menggunakan **BLoC Pattern** via paket `flutter_bloc` (^9.1.1):

| No | BLoC | Lokasi Berkas | Tanggung Jawab / Fitur |
|---|---|---|---|
| 1 | `AuthBloc` | [`lib/features/auth/presentation/bloc/auth_bloc.dart`](lib/features/auth/presentation/bloc/auth_bloc.dart) | Mengelola status login SSO, logout, validasi sesi, refresh token otomatis, dan profil user. |
| 2 | `RegistrationBloc` | [`lib/features/auth/presentation/bloc/registration_bloc.dart`](lib/features/auth/presentation/bloc/registration_bloc.dart) | Mengelola *flow* pendaftaran akun warga multi-tahap (4 *steps*) dan pengiriman form data. |
| 3 | `KycBloc` | [`lib/features/daftar/presentation/bloc/kyc_bloc.dart`](lib/features/daftar/presentation/bloc/kyc_bloc.dart) | Memeriksa dan menampilkan status verifikasi akun/KYC serta daftar dokumen identitas. |
| 4 | `ServicesBloc` | [`lib/features/services/presentation/bloc/services_bloc.dart`](lib/features/services/presentation/bloc/services_bloc.dart) | Mengambil daftar layanan populer, semua layanan, kategori layanan, dan sub-layanan. |
| 5 | `WilayahBloc` | [`lib/features/wilayah/presentation/bloc/wilayah_bloc.dart`](lib/features/wilayah/presentation/bloc/wilayah_bloc.dart) | Mengelola data berjenjang (Provinsi $\rightarrow$ Kabupaten $\rightarrow$ Kecamatan $\rightarrow$ Kelurahan). |
| 6 | `NotificationBloc` | [`lib/features/notifications/presentation/bloc/notification_bloc.dart`](lib/features/notifications/presentation/bloc/notification_bloc.dart) | Inisialisasi Firebase Messaging, perizinan, dan pengelolaan token FCM perangkat. |
| 7 | `NotificationListBloc` | [`lib/features/notifications/presentation/bloc/notification_list_bloc.dart`](lib/features/notifications/presentation/bloc/notification_list_bloc.dart) | Mengelola daftar notifikasi lokal/riwayat dengan tab filter (Semua, Pengumuman, Layanan). |
| 8 | `SettingsBloc` | [`lib/features/settings/presentation/bloc/settings_bloc.dart`](lib/features/settings/presentation/bloc/settings_bloc.dart) | Mengelola pengaturan aplikasi dan mengambil informasi rilis via `package_info_plus`. |

---

## 3. Enkripsi & Keamanan Data (Encryption & Security)

1. **Penyimpanan Kredensial Terenkripsi (`flutter_secure_storage`)**:
   - Berkas: [`lib/features/auth/data/datasources/auth_local_data_source.dart`](lib/features/auth/data/datasources/auth_local_data_source.dart)
   - Digunakan untuk menyimpan sesi Keycloak (`auth_tokens`) yang terdiri dari `access_token`, `refresh_token`, dan masa kedaluwarsa.
   - Menggunakan Keychain pada iOS dan KeyStore/EncryptedSharedPreferences pada Android.
2. **Obfuscation Rahasia Aplikasi (`envied`)**:
   - Berkas: [`lib/keycloak_env.dart`](lib/keycloak_env.dart)
   - Mengenkripsi dan mengaburkan *variable* rahasia (`KEYCLOAK_CLIENT_SECRET`) ke dalam kode biner C/Dart saat proses *compile*, mencegah ekstraksi via *decompilation*.

---

## 4. Paket Dependensi (Packages)

Berdasarkan berkas [`pubspec.yaml`](pubspec.yaml):

### Dependensi Aplikasi (Production)
- **State & Architecture**: `flutter_bloc` (^9.1.1), `get_it` (^9.2.1), `injectable` (^3.0.0), `fpdart` (^1.2.0), `equatable` (^2.0.8)
- **Networking & API**: `dio` (^5.9.2)
- **Firebase & Notifikasi**: `firebase_core` (^4.7.0), `firebase_messaging` (^16.2.1), `flutter_local_notifications` (^21.0.0)
- **Keamanan & Storage**: `flutter_secure_storage` (^10.3.1), `envied` (^1.3.5)
- **Web & Browser**: `flutter_inappwebview` (^6.1.5), `url_launcher` (^6.3.1)
- **Media & Device Info**: `image_picker` (^1.2.1), `package_info_plus` (^10.1.0)
- **Tampilan & Utilitas**: `google_fonts` (^8.1.0), `cupertino_icons` (^1.0.8), `intl` (^0.20.2)

### Dependensi Pembangunan (Development / Code Generation)
- `build_runner` (^2.13.1)
- `injectable_generator` (^3.0.2)
- `envied_generator` (^1.3.5)
- `flutter_launcher_icons` (^0.14.4)
- `flutter_lints` (^6.0.0)
- `flutter_test` (Flutter SDK)

---

## 5. Daftar Fitur Lengkap (Features)

### A. Autentikasi & Akun (`auth`)
- **Login SSO Keycloak**: Autentikasi berbasis OAuth 2.0 Resource Owner Password Credentials (ROPC) grant.
- **Auto-Login & Token Refresh**: Restorasi sesi dari penyimpanan aman dan penyegaran token otomatis sebelum kedaluwarsa.
- **Profil Pengguna**: Menampilkan informasi warga, NIK, email, status verifikasi akun, dan inisial avatar.
- **Lupa Kata Sandi**: Halaman permohonan reset kata sandi melalui tautan email resmi.
- **Logout**: Pencabutan sesi dari *server* SSO Keycloak dan pembersihan cache lokal.

### B. Pendaftaran Warga & KYC (`daftar`)
- **Pendaftaran Bertahap (4 Langkah)**:
  - *Langkah 1 (Data Diri)*: Nama lengkap, NIK (16 digit), jenis kelamin, tanggal lahir.
  - *Langkah 2 (Kontak & Akun)*: Email, nomor WhatsApp (normalisasi format Indonesia `+62`/`08`), kata sandi & konfirmasi.
  - *Langkah 3 (Alamat & Domisili)*: Integrasi cascading master wilayah (Provinsi, Kabupaten, Kecamatan, Kelurahan), nomor RT/RW, kode pos, dan alamat detail.
  - *Langkah 4 (Dokumen KYC)*: Pengambilan atau upload foto fisik KTP dan foto selfie wajah, dilengkapi persetujuan syarat & ketentuan.
- **Status KYC**:
  - Banner dinamis di Beranda yang menginformasikan status verifikasi (Belum Terverifikasi, Menunggu Verifikasi, Terverifikasi, Ditolak).
  - Layar detail status KYC ([`KycStatusScreen`](lib/features/daftar/presentation/pages/kyc_status_page.dart)) dengan rincian dokumen identitas.

### C. Dashboard & Navigasi (`dashboard`)
- **Bottom Navigation Bar**: Navigasi utama 4 tab (Menu Drawer, Beranda, Semua Layanan, Profil Saya).
- **Sidebar Drawer ([`AppSidebar`](lib/features/dashboard/presentation/widgets/app_sidebar.dart))**:
  - Header profil ringkas pengguna dan lencana status verifikasi.
  - Tautan navigasi: Beranda, Semua Layanan, Profil Saya, Pengaturan, Bantuan & FAQ (Helpdesk), serta tombol Login/Logout.

### D. Beranda (`home`)
- **Hero & Pencarian Cepat**: Pencarian nama layanan secara langsung (*real-time filter*).
- **Banner Akun KYC**: Kartu informasi status verifikasi akun pengguna.
- **Grid Layanan Populer**: Menampilkan 8 layanan publik paling sering diakses warga dengan ikon tematik.
- **Aksi Cepat "Lihat Semua"**: Membuka katalog lengkap layanan daerah.

### E. Katalog Layanan Publik (`services`)
- **Layanan Populer**: Halaman daftar layanan terpopuler.
- **Semua Layanan**: Tampilan lengkap seluruh layanan pemerintah daerah Jombang.
- **Kategori Layanan**: Pengelompokan layanan berdasarkan bidang (Administrasi Kependudukan, Kesehatan, Perizinan, dsb.).
- **Pelacak Akses (Counter)**: Mencatat analitik klik/akses layanan oleh pengguna.
- **In-App Browser & SSO Bypass**: Membuka tautan sistem eksternal di dalam aplikasi tanpa perlu login ulang jika layanan mendukung SSO bypass.

### F. Wilayah Administratif (`wilayah`)
- Penyediaan data wilayah administratif bertingkat yang digunakan pada form registrasi warga.

### G. Notifikasi (`notifications`)
- **Push Notification (FCM)**: Menerima notifikasi langsung dari server Firebase baik saat aplikasi di latar depan, latar belakang, maupun mati.
- **Notifikasi Lokal**: Integrasi `flutter_local_notifications` dengan channel prioritas tinggi di Android (`high_importance_channel`).
- **Pusat Notifikasi**: Layar riwayat notifikasi dengan filter kategori (Semua, Pengumuman, Layanan).
- **Halaman Pengujian FCM**: Layar khusus untuk memeriksa, menyalin token FCM perangkat, dan melakukan simulasi notifikasi lokal.

### H. Pengaturan & Bantuan (`settings`)
- **Pengaturan Notifikasi & Akun**: Konfigurasi preferensi pengguna dan jalan pintas ke status KYC.
- **Kebijakan Privasi & Syarat Ketentuan**: Membuka dokumen hukum dan kepatuhan data via Webview.
- **Tentang Aplikasi (`AboutPage`)**: Informasi versi aplikasi, logo daerah, dan hak cipta Pemerintah Kabupaten Jombang.
- **Helpdesk Pemkab Jombang**: Akses cepat ke portal bantuan teknis Pemkab.

---

## 6. Katalog API Endpoint

### A. Keycloak SSO (Autentikasi & Akun)
- **Base URL**: `https://sso-v2.jombangkab.go.id`
- **Konfigurasi**: [`KeycloakConfig`](lib/core/constants/keycloak_config.dart)
- **Realm**: `jombangkab`
- **Client ID**: `joss-mobile`

| HTTP Method | Path | Header | Payload / Parameter | Deskripsi |
|---|---|---|---|---|
| `POST` | `/realms/jombangkab/protocol/openid-connect/token` | `Content-Type: application/x-www-form-urlencoded` | `grant_type=password`, `client_id`, `client_secret`, `username`, `password`, `scope=openid offline_access` | Login SSO pengguna via ROPC grant |
| `POST` | `/realms/jombangkab/protocol/openid-connect/token` | `Content-Type: application/x-www-form-urlencoded` | `grant_type=refresh_token`, `client_id`, `client_secret`, `refresh_token`, `scope=openid offline_access` | Memperbarui sesi dengan refresh token |
| `GET` | `/realms/jombangkab/protocol/openid-connect/userinfo` | `Authorization: Bearer <access_token>` | - | Mengambil data akun terdaftar di Keycloak |
| `POST` | `/realms/jombangkab/protocol/openid-connect/logout` | `Content-Type: application/x-www-form-urlencoded` | `client_id`, `client_secret`, `refresh_token` | Logout dan mencabut sesi pengguna |

### B. Microservice Profil JOSS
- **Base URL**: `https://api.jombangkab.go.id/micro-joss-profile/`

| HTTP Method | Path | Header | Payload / Parameter | Deskripsi |
|---|---|---|---|---|
| `GET` | `profile` | `Authorization: Bearer <access_token>` | - | Mengambil data profil detail warga di ekosistem JOSS |

### C. Microservice Pendaftaran & KYC (`DaftarConfig`)
- **Base URL**: `https://api.jombangkab.go.id/micro-joss-daftar/`
- **Konfigurasi**: [`DaftarConfig`](lib/core/constants/daftar_config.dart)

| HTTP Method | Path | Header | Payload / Parameter | Deskripsi |
|---|---|---|---|---|
| `POST` | `registrasi/submit` | `Content-Type: multipart/form-data`, `User-Agent: yaak` | `nik`, `nama`, `email`, `no_wa`, `jenis_kelamin`, `password`, `provinsi`, `kabupaten`, `kecamatan`, `kelurahan`, `alamat`, `rt`, `rw`, `kode_pos`, `ktp` (file .jpg), `selfie` (file .jpg) | Mengirimkan pendaftaran akun warga beserta berkas KYC |
| `GET` | `kyc/status` | `Authorization: Bearer <access_token>`, `User-Agent: yaak` | - | Mengambil status verifikasi KYC pengguna dan berkasnya |

### D. Microservice Menu & Layanan Publik (`MenuConfig`)
- **Base URL**: `https://api.jombangkab.go.id/micro-joss-menu/`
- **Konfigurasi**: [`MenuConfig`](lib/core/constants/menu_config.dart)

| HTTP Method | Path | Header | Parameter / Payload | Deskripsi |
|---|---|---|---|---|
| `GET` | `menu` | `Authorization: Bearer <access_token>`, `Accept: application/json` | Query: `platform=mobile` | Mengambil seluruh katalog menu layanan publik JOSS |
| `GET` | `menu/kategori` | `Authorization: Bearer <access_token>`, `Accept: application/json` | Query: `platform=mobile` | Mengambil daftar kategori layanan publik |
| `POST` | `counter` | `Authorization: Bearer <access_token>`, `Accept: application/json` | Body JSON: `{"platform": "mobile", "code": "<service_code>"}` atau `{"platform": "mobile", "id": "<service_id>"}` | Mencatat analitik jumlah klik/akses layanan oleh pengguna |

### E. Microservice Wilayah Administratif (`WilayahConfig`)
- **Base URL**: `https://api.jombangkab.go.id/micro-wilayah-administratif/`
- **Konfigurasi**: [`WilayahConfig`](lib/core/constants/wilayah_config.dart)

| HTTP Method | Path | Header | Query Parameter | Deskripsi |
|---|---|---|---|---|
| `GET` | `master/provinsi` | `Accept: */*`, `User-Agent: yaak` | - | Mengambil daftar seluruh provinsi di Indonesia |
| `GET` | `master/kabupaten` | `Accept: */*`, `User-Agent: yaak` | `prov_id=<provinsi_id>` | Mengambil daftar kabupaten/kota berdasarkan ID provinsi |
| `GET` | `master/kecamatan` | `Accept: */*`, `User-Agent: yaak` | `kab_id=<kabupaten_id>` | Mengambil daftar kecamatan berdasarkan ID kabupaten |
| `GET` | `master/kelurahan` | `Accept: */*`, `User-Agent: yaak` | `kec_id=<kecamatan_id>` | Mengambil daftar kelurahan/desa berdasarkan ID kecamatan |

---

## 7. Layanan Eksternal & Webview

| Layanan | Tautan / URL | Integrasi |
|---|---|---|
| **Portal Helpdesk Pemkab** | `https://helpdesk.jombangkab.go.id/` | Dibuka langsung di dalam In-App Webview |
| **Layanan Web SSO Bypass** | Dinamis sesuai `ServiceEntity.url` | Disuntik parameter autentikasi `?token=<access_token>` |
