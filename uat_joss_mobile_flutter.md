# Dokumen User Acceptance Testing (UAT)
## Aplikasi JOSS Mobile (Flutter: Android & iOS) - Fase 2

---

## I. Informasi Pengujian
| **Item**               | **Detail**                                                                 |
| ---------------------- | -------------------------------------------------------------------------- |
| **Nama Proyek**        | JOSS Mobile (Jombang One Stop Service)                                                        |
| **Klien**              | Pemerintah Kabupaten Jombang — Dinas Komunikasi dan Informatika            |
| **Tanggal Pengujian**  | ..................................................                         |
| **Lokasi Pengujian**   | ..................................................                         |
| **Versi Aplikasi**     | v1.0.0 (Release Candidate)                                                 |
| **Perangkat Test**     | ..................................................                         |
| **Penguji (Klien)**    | ..................................................                         |
| **Pendamping (Dev)**   | ..................................................                         |

---

## II. Petunjuk Pengisian
Berikan tanda centang (✓) pada kolom **Status** sesuai dengan hasil pengujian:
- **[ PASS ]** : Fitur berjalan dengan baik sesuai skenario.
- **[ FAIL ]** : Fitur mengalami error, bug, atau tidak sesuai skenario (tuliskan detail di kolom Catatan).
- **[ N/A ]**  : Tidak dapat diaplikasikan / dilewati.

---

## III. Checklist Skenario UAT

### 1. Modul Autentikasi & SSO Keycloak (OIDC + PKCE)
| No | Skenario Pengujian | Ekspektasi Hasil | Status (Pass/Fail) | Catatan |
|:---|:---|:---|:---:|:---|
| 1.1 | Buka aplikasi pertama kali (Fresh Install) | Menampilkan Splash Screen lalu halaman Onboarding/Login. | | |
| 1.2 | Klik tombol "Masuk" / "Login" | Diarahkan ke halaman login Keycloak (via Chrome Custom Tabs). | | |
| 1.3 | Login dengan kredensial valid (SSO) | Login berhasil, CCT tertutup, diarahkan ke halaman Dashboard Mobile. | | |
| 1.4 | Login dengan kredensial tidak valid | Menampilkan pesan error dari Keycloak "Username/password salah". | | |
| 1.5 | Klik tombol "Daftar" / "Register" | Diarahkan ke form registrasi Keycloak, proses pendaftaran berhasil. | | |
| 1.6 | Fitur Lupa Password (Keycloak) | Menerima email reset password dan berhasil mengganti password. | | |
| 1.7 | Fitur Auto-Login (Tutup & buka app) | Aplikasi langsung masuk ke Dashboard tanpa meminta login ulang (Sesi tersimpan). | | |
| 1.8 | Fitur Logout (Keluar) | Sesi dihapus (di app & Keycloak), kembali ke halaman Login awal. | | |

### 2. Modul Keamanan & Biometrik
| No | Skenario Pengujian | Ekspektasi Hasil | Status (Pass/Fail) | Catatan |
|:---|:---|:---|:---:|:---|
| 2.1 | Aktivasi login Biometrik (Sidik Jari/Face ID) | Sistem meminta verifikasi biometrik dan berhasil menyimpannya. | | |
| 2.2 | Login menggunakan Biometrik | Berhasil masuk ke Dashboard hanya dengan scan biometrik. | | |
| 2.3 | Validasi Expired Token | Saat token habis, mekanisme *Refresh Token* berjalan otomatis tanpa *force logout*. | | |

### 3. Modul Dashboard & Navigasi Utama
| No | Skenario Pengujian | Ekspektasi Hasil | Status (Pass/Fail) | Catatan |
|:---|:---|:---|:---:|:---|
| 3.1 | Tampilan Dashboard | Menampilkan UI sesuai desain (Nama user, foto profil, kategori layanan). | | |
| 3.2 | Navigasi Bottom Bar | Berpindah dengan lancar antara tab (Beranda, Riwayat, Notifikasi, Profil). | | |
| 3.3 | Banner/Slider Pengumuman | Slider informasi di beranda dapat digeser (swipe) dan diklik. | | |

### 4. Modul Katalog Layanan & Pencarian
| No | Skenario Pengujian | Ekspektasi Hasil | Status (Pass/Fail) | Catatan |
|:---|:---|:---|:---:|:---|
| 4.1 | Filter Layanan per Kategori | Menampilkan list layanan sesuai kategori (Kepegawaian, Ketenagakerjaan, dll). | | |
| 4.2 | Fitur Pencarian Layanan (Search Bar) | Mengetik nama layanan menampilkan hasil pencarian yang relevan & cepat. | | |
| 4.3 | Klik detail layanan publik | Menampilkan deskripsi layanan, syarat, dan tombol aksi (Akses Layanan). | | |
| 4.4 | Akses Layanan Web (Integrasi SSO) | Saat klik layanan pihak ketiga (misal: MKJU), diarahkan via Chrome Custom Tab otomatis login tanpa input password lagi. | | |

### 5. Modul Profil & Verifikasi (KYC)
| No | Skenario Pengujian | Ekspektasi Hasil | Status (Pass/Fail) | Catatan |
|:---|:---|:---|:---:|:---|
| 5.1 | Halaman Profil Pengguna | Menampilkan data NIK, Nama, Email, dan Foto Profil dengan benar. | | |
| 5.2 | Edit Foto Profil | Berhasil mengambil dari Galeri/Kamera, upload ke server, dan foto terupdate. | | |
| 5.3 | Status Verifikasi KYC | Menampilkan status akun (Belum Terverifikasi / Dalam Antrean / Terverifikasi). | | |
| 5.4 | Peringatan Akun Belum Terverifikasi | Memunculkan alert peringatan saat mengakses layanan khusus jika akun belum di-KYC. | | |

### 6. Modul Notifikasi (Firebase FCM) & Riwayat
| No | Skenario Pengujian | Ekspektasi Hasil | Status (Pass/Fail) | Catatan |
|:---|:---|:---|:---:|:---|
| 6.1 | Menerima Push Notification (App Tertutup) | Muncul pop-up notifikasi di bar notifikasi sistem Android/iOS. | | |
| 6.2 | Menerima In-App Notification (App Terbuka) | Muncul badge/indikator notifikasi baru di tab Notifikasi. | | |
| 6.3 | Interaksi Notifikasi | Saat notifikasi diklik, aplikasi terbuka dan mengarah ke halaman yang sesuai. | | |
| 6.4 | Halaman Riwayat Akses | Menampilkan daftar (log) layanan apa saja yang terakhir diakses oleh user. | | |

### 7. Pengujian Lingkungan Offline / Error Handling
| No | Skenario Pengujian | Ekspektasi Hasil | Status (Pass/Fail) | Catatan |
|:---|:---|:---|:---:|:---|
| 7.1 | Buka aplikasi tanpa koneksi internet | Menampilkan pesan "Tidak ada koneksi internet". Data terakhir (cache) tetap tampil. | | |
| 7.2 | Akses layanan saat server maintenance | Menampilkan *Error State / Empty State* yang ramah pengguna (bukan force close). | | |

---

## IV. Kesimpulan & Pengesahan

**Status UAT Akhir:**
- [ ] Diterima tanpa catatan (Lanjut ke Deployment / BAST)
- [ ] Diterima dengan catatan perbaikan minor (Tidak menghalangi *Go-Live*)
- [ ] Belum Diterima, butuh perbaikan major (UAT Ulang)

**Catatan Umum / Tindak Lanjut:**
*(Tuliskan rekapitulasi temuan bug atau revisi yang disepakati di sini)*
1. ........................................................................................
2. ........................................................................................
3. ........................................................................................


<br><br>
**Jombang, .................................... 2027**

| Disetujui Oleh (Klien) | Dibuat & Diserahkan Oleh (Tim Dev) |
| :---: | :---: |
| <br><br><br><br> | <br><br><br><br> |
| **(...........................................)** | **(...........................................)** |
| *Pemerintah Kab. Jombang* | *Project Manager / Lead Dev* |
