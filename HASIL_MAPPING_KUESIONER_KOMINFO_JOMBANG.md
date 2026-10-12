# HASIL MAPPING KUESIONER PRA-KICK-OFF MEETING
## PENGEMBANGAN APLIKASI JOSS MOBILE (FASE 2)
### DINAS KOMUNIKASI DAN INFORMATIKA KABUPATEN JOMBANG

> **Sumber Dokumen:** `kuesioner_pra_kickoff_kominfo_jombang.pdf`  
> **Status:** Terisi Lengkap dan Divalidasi oleh Tim Teknis Diskominfo Jombang  
> **Format Penyajian:** Pemetaan Komprehensif Seluruh Isian (Top-to-Bottom) dalam Bentuk Tabel Terstruktur dan Detail.

---

### DAFTAR ISI PEMETAAN
1. [Identitas Responden Diskominfo Jombang](#data-responden)
2. [Bagian 1: Target Pengguna, Selling Point & Quick Win](#bagian-1-target-pengguna-fitur-unggulan-selling-point--quick-win)
3. [Bagian 2: Prioritas Integrasi Aplikasi & Pemetaan API Eksisting](#bagian-2-prioritas-integrasi-aplikasi--pemetaan-api)
4. [Bagian 3: Preferensi Desain UI/UX & Tema Tampilan](#bagian-3-preferensi-desain-uiux--tema-tampilan)
5. [Bagian 4: Kesiapan Akun Toko Aplikasi (Store) & Infrastruktur](#bagian-4-kesiapan-akun-toko-aplikasi-store--infrastruktur)
6. [Bagian 5: Keamanan, Data Pribadi, & Kepatuhan Regulasi](#bagian-5-keamanan-data-pribadi--kepatuhan-regulasi)
7. [Bagian 6: Target Rilis (Roadmap), Peluncuran, & Indikator Keberhasilan (KPI)](#bagian-6-target-rilis-roadmap-peluncuran--indikator-keberhasilan-kpi)
8. [Bagian 7: Pelatihan Pengguna & Alih Pengetahuan (Transfer of Knowledge / ToT)](#bagian-7-pelatihan-pengguna--alih-pengetahuan-transfer-of-knowledge--tot)
9. [Bagian 8: Dukungan Pasca-Rilis & Penanganan Masalah (Helpdesk)](#bagian-8-dukungan-pasca-rilis--penanganan-masalah-helpdesk)
10. [Bagian 9: Struktur Tata Kelola Proyek & Tim Penghubung (SPOC)](#bagian-9-struktur-tata-kelola-proyek--tim-penghubung-spoc)

---

<a name="data-responden"></a>
## DATA RESPONDEN DISKOMINFO JOMBANG

| No | Parameter Identitas | Data Hasil Isian Kuesioner | Keterangan / Validasi |
|:---|:---|:---|:---|
| 1 | **Nama Lengkap Responden** | **R WITCAKSONO SETYO PUTRO** | Pejabat Penanggung Jawab Teknis |
| 2 | **Jabatan / Bidang** | **KEPALA BIDANG APLIKASI INFORMATIKA** | Bidang Aptika Diskominfo Jombang |
| 3 | **Nomor Kontak / WhatsApp** | **081-333-828952** | Kontak Resmi Koordinasi |
| 4 | **Tanggal Pengisian Form** | **10 OKTOBER 2026** | Form Disahkan Sebelum Kick-Off Meeting |

---

<a name="bagian-1-target-pengguna-fitur-unggulan-selling-point--quick-win"></a>
## BAGIAN 1: TARGET PENGGUNA, FITUR UNGGULAN (SELLING POINT), & QUICK WIN

### Pertanyaan 1: Fokus Target Pengguna Utama di Fase 2
| Atribut | Pilihan yang Dipilih | Detail Jawaban / Uraian Responden | Analisis Kebutuhan Implementasi |
|:---|:---|:---|:---|
| **Target Segmen Pengguna** | **[X] Keduanya**<br>*(Masyarakat umum & ASN Pemkab)* | Digunakan untuk masyarakat maupun ASN Pemkab, dapat diunduh bebas di Playstore, namun di tahap awal akan digunakan oleh ASN terlebih dahulu. | • Publikasi Play Store & App Store bersifat terbuka umum.<br>• Sistem navigasi multi-persona (Guest/Masyarakat vs. ASN terotentikasi Keycloak).<br>• Peluncuran bertahap: Prioritas adaptasi ASN internal lalu ekspansi masyarakat. |

---

### Pertanyaan 2: Fitur Unggulan (Selling Point) & Pencapaian Cepat (Quick Win)
| Kategori Capaian | Jenis Fitur / Layanan | Rincian Isian Kuesioner Diskominfo | Target Pengguna & Manfaat |
|:---|:---|:---|:---|
| **1. QUICK WIN**<br>*(Demo Cepat Tahap Awal untuk Pimpinan)* | **Integrasi Menu Web Eksisting via SSO** | Menampilkan menu aplikasi-web eksisting yang sudah terintegrasi dengan SSO:<br>1. **E-OFFICE**<br>2. **E-MONEV**<br>3. **E-CLOUD**<br>4. **TALENTA** | Menunjukkan kemampuan Single Sign-On (SSO) satu pintu portal JOSS Mobile secara riil kepada Bupati/Sekda tanpa perlu login ulang antar aplikasi web. |
| **2. SELLING POINT**<br>*(Daya Tarik Utama Pengguna Aplikasi)* | **Fitur Mobile-Native E-Office (ASN)** | a. Lihat rekap presensi pegawai<br>b. Lihat aktivitas pegawai<br>c. Input aktivitas pegawai harian<br>d. Verifikasi aktivitas bawahan (Approval)<br>e. Lihat TPP bulanan | Memberikan kemudahan operasional harian bagi seluruh ASN Jombang langsung dari genggaman tanpa harus membuka browser laptop. |
| | **Push Notifikasi Terpusat** | Push notifikasi real-time dari sistem Pemkab ke smartphone pengguna | Pengumuman daerah darurat/resmi dan notifikasi kedinasan (disposisi surat, presensi, persetujuan). |
| | **Tombol Telepon Darurat** | Button Telepon langsung ke Call Center 112 maupun nomor penting lainnya | Akses darurat cepat 1 sentuhan bagi masyarakat Jombang (One-Touch Emergency Call). |
| | **Kanal Berita Daerah** | Menampilkan berita dan agenda resmi dari web portal `jombangkab.go.id` | Pusat informasi daerah terpercaya yang anti-hoaks dan selalu terbarui. |
| | **Direktori Wisata & Fasilitas (POI)** | Menampilkan daftar Point-of-Interest (POI) daerah dalam bentuk **List** maupun **Peta Interaktif (Map)** | Pemandu masyarakat dan wisatawan untuk menemukan RS, Puskesmas, Kantor Polisi, Tempat Wisata, dan Fasilitas Umum. |

---

<a name="bagian-2-prioritas-integrasi-aplikasi--pemetaan-api"></a>
## BAGIAN 2: PRIORITAS INTEGRASI APLIKASI & PEMETAAN API

### Pertanyaan 3: Pemetaan Top 5 Prioritas Integrasi Aplikasi & Kesiapan Backend
| No | Nama Aplikasi / Fitur Prioritas | Model Tampilan di JOSS | Ketersediaan API & Endpoint | Catatan Endpoint / Spesifikasi Teknis | PIC Backend / Status Tindak Lanjut |
|:---:|:---|:---|:---|:---|:---|
| **1** | **E-OFFICE** | **Mobile Native (Flutter)** | **Belum tersedia** | Dibutuhkan 5 endpoint modul native:<br>• Rekap presensi<br>• List aktivitas<br>• Create/Edit aktivitas<br>• Approval atasan<br>• Rincian TPP | **Irfan** *(Programmer Jombang)*<br>Target: Pembuatan REST API JSON & otentikasi Bearer Token SSO |
| **2** | **PUSH NOTIFIKASI** | **Mobile Native (Flutter)** | **Belum tersedia** | Dibutuhkan integrasi Firebase Cloud Messaging (FCM) & API backend pengirim pesan/blast | **Irfan** *(Programmer Jombang)*<br>Target: Registrasi FCM Token per user di database SSO |
| **3** | **BUTTON TELEPON** | **Mobile Native (Flutter)** | **Belum tersedia** | Call Center 112 & direktori kontak darurat OPD (Native Android/iOS Intent Phone Call) | Tim Diskominfo Jombang<br>Target: Penyediaan data master nomor telepon resmi |
| **4** | **BERITA & INFORMASI** | **Mobile Native (Flutter)** | **Belum tersedia** | Sumber konten: `www.jombangkab.go.id/berita`. Dibutuhkan REST API/RSS JSON endpoint | **Irfan** *(Programmer Jombang)*<br>Target: Endpoint feeds berita, thumbnail, dan kategori |
| **5** | **DIREKTORI POINT-OF-INTEREST (POI)** | **Mobile Native (Flutter)** | **Belum tersedia** | Menampilkan POI daerah dalam bentuk List & Google Maps (koordinat lat/lng, foto, jam buka) | Tim Diskominfo Jombang<br>Target: Database master POI / endpoint koordinat fasilitas |

---

### Pertanyaan 4–7: Kesiapan Teknis Backend, Layanan Baru, Berita & Otorisasi SSO
| No | Nomor Pertanyaan | Variabel Parameter | Jawaban / Rincian Responden | Implikasi Teknis & PIC |
|:---:|:---|:---|:---|:---|
| 1 | **Pertanyaan 4**<br>*(PIC Backend & Dokumentasi)* | • Nama PIC Backend / Programmer<br>• Nomor Kontak / WhatsApp<br>• Dokumentasi Swagger / Postman<br>• URL Dokumentasi API | • **IRFAN**<br>• **0896 8064 1487**<br>• **Belum ada**<br>• *(Belum tersedia)* | Tim Pengembang MBO menyiapkan standar Postman Collection / OpenAPI Spec template untuk diisi tim programmer Jombang. |
| 2 | **Pertanyaan 5**<br>*(Modul Layanan Baru Fase 2)* | • Identifikasi Layanan Baru<br>• Deskripsi Alur Layanan<br>• Penyedia API Backend | • **[X] Tidak ada**<br>• *N/A*<br>• *N/A* | Fokus penuh pada penyelesaian 5 fitur prioritas native dan integrasi web SSO yang ada. |
| 3 | **Pertanyaan 6**<br>*(Konten Berita & Agenda)* | • Sumber Konten Berita<br>• Format Feed yang Tersedia<br>• PIC Pengelola Konten | • `www.jombangkab.go.id/berita`<br>• Belum tahu / perlu koordinasi PIC<br>• **IRFAN / 0896 8064 1487** | Irfan akan menyediakan endpoint parser/API JSON dari WordPress/CMS portal resmi `jombangkab.go.id`. |
| 4 | **Pertanyaan 7**<br>*(Delegasi Akses Admin SSO)* | • Nama PIC Admin SSO<br>• Jabatan / Unit Kerja<br>• Nomor Kontak / WhatsApp | • **IRFAN**<br>• **TENAGA AHLI**<br>• **0896 8064 1487** | Penanggung jawab setup Client ID, Client Secret, Redirect URI Keycloak (`sso-v2.jombangkab.go.id`). |

---

<a name="bagian-3-preferensi-desain-uiux--tema-tampilan"></a>
## BAGIAN 3: PREFERENSI DESAIN UI/UX & TEMA TAMPILAN

### Pertanyaan 8–10: Identitas Warna, Tema Tampilan, & Acuan Desain
| Parameter Desain | Isian Responden Diskominfo | Spesifikasi Detail & Rekomendasi UI/UX |
|:---|:---|:---|
| **Warna Utama (Primary Color)** | Mengikuti branding web `sso.jombangkab.go.id` / `www.jombangkab.go.id` | Palet Hijau Khas Pemkab Jombang (#0E8044 / #1B5E20) berpadu dengan aksen elegan modern. |
| **Warna Aksen (Accent Color)** | Mengikuti branding web eksisting | Emas / Kuning Hangat (#F59E0B / #D97706) sebagai warna kontras tombol aksi. |
| **Warna Latar (Background Color)** | Mengikuti branding web eksisting | Putih Bersih (#FFFFFF) & Abu-abu Terang Netral (#F8FAFC) untuk legibilitas maksimal. |
| **Dokumen Panduan Visual / Logo Vector** | Sama dengan sebelumnya | Menggunakan file vektor/PNG master resmi Diskominfo yang sudah terpasang di portal web. |
| **Tema Tampilan (Theme Mode)** | **Mode Terang Saja (Light Mode)** | Tampilan bersih, kontras tinggi, mudah dibaca ASN/masyarakat di berbagai kondisi cahaya luar ruangan. |
| **Aplikasi Acuan / Benchmark** | **BELUM ADA** | Tim Desainer MBO merancang UI kustom berstandar modern setara Jabar Super App / JAKI. |

---

### Pertanyaan 11: Struktur & Hierarki Elemen Beranda (Home Screen)
| Zona Layout Beranda | Elemen Komponen UI | Detail Isian Kuesioner Diskominfo | Fungsi & Interaksi Pengguna |
|:---|:---|:---|:---|
| **Bagian Atas (Header)** | Identitas & Notifikasi | • Judul aplikasi **JOSS**<br>• Sapaan personal: *"Halo, [Nama Pengguna]!"*<br>• Ikon Lonceng Notifikasi | Memberikan identitas aplikasi serta akses cepat ke daftar pemberitahuan masuk. |
| **Kartu Informasi ASN** | Info Profil Kepegawaian | Menampilkan atribut identitas ASN:<br>• **NAMA**<br>• **NIP**<br>• **JABATAN**<br>• **UNIT KERJA** | Muncul secara otomatis jika pengguna login menggunakan akun ASN (sinkron dari atribut Keycloak). |
| **Banner Carousel** | Media Promosi & Program | **SLIDER** (Banner horizontal swipable) | Menyajikan pengumuman program prioritas bupati, flyer kegiatan, dan banner edukasi daerah. |
| **Grid Layanan Utama** | Menu Navigasi Layanan | **YA** (Icon Grid) | Akses 1 sentuhan ke E-Office, E-Monev, E-Cloud, Talenta, Layanan Publik, dan Telepon 112. |
| **Konten Bawah** | Informasi Terkini | **PENGUMUMAN / NOTIFIKASI** & Feeds Berita Terbaru | Ringkasan pengumuman resmi dan artikel berita Kabupaten Jombang teraktual. |
| **Bottom Navigation** | Navigasi Tab Bawah | **MENU UTAMA** *(Home, Layanan/Aplikasi, Berita/POI, Profil)* | Navigasi jempol standar mobile untuk kemudahan berpindah antar modul utama. |

---

### Pertanyaan 12–15: Standar Layanan Publik & Ketersediaan Aset Grafis
| No | Parameter | Isian Responden Diskominfo | Penjelasan Implementasi |
|:---:|:---|:---|:---|
| 1 | **Q12: Kategori Layanan Publik & Bahasa** | Bahasa sederhana dan ramah pengguna | Menggunakan taksonomi pelayanan umum yang tidak kaku/birokratis agar mudah dipahami masyarakat. |
| 2 | **Q13: Rincian Info Layanan Publik** | Kelengkapan standar informasi layanan | Menyediakan modul ringkas: deskripsi layanan, berkas persyaratan, prosedur alur, jam pelayanan, dan kontak call center. |
| 3 | **Q14: Pelacakan Status Permohonan** | Notifikasi status permohonan | Menyiapkan kerangka UI tracking tiket/permohonan berjenjang (Diajukan -> Diproses -> Selesai). |
| 4 | **Q15: Aset Grafis Resmi** | **SAMA DENGAN SEBELUMNYA** | Logo resmi Kabupaten Jombang dan logo JOSS menggunakan aset grafis resmi yang telah ada di Diskominfo. |

---

<a name="bagian-4-kesiapan-akun-toko-aplikasi-store--infrastruktur"></a>
## BAGIAN 4: KESIAPAN AKUN TOKO APLIKASI (STORE) & INFRASTRUKTUR

### Pertanyaan 16–18: Kesiapan Akun Publikasi, Server & Skala Pengguna
| Kategori Infrastruktur | Parameter | Jawaban / Rincian Responden | Keterangan & Tindak Lanjut |
|:---|:---|:---|:---|
| **Akun Pengembang Toko Aplikasi (Store Accounts)** | • Akun Google Play Store Console (D-U-N-S)<br>• Akun Apple Developer Program (Enterprise/Org)<br>• **PIC Pengelola Store**<br>• **Nomor WhatsApp PIC Store** | • **Sudah Tersedia**<br>• **Sudah Tersedia**<br>• **RIZKY** *(Tenaga Ahli)*<br>• **0878 2829 4367** | Akun pengembang resmi Pemkab sudah siap. MBO akan berkoordinasi dengan Mas Rizky untuk pengunduhan sertifikat signing dan setup access invite. |
| **Server Lingkungan (Staging & Production)** | • Server Staging / Sandbox Keycloak<br>• URL / Domain Keycloak Live<br>• Kebijakan Jaringan & Akses | • **Tersedia**<br>• `sso-v2.jombangkab.go.id`<br>• Akses publik / konfigurasi via Reverse Proxy | Endpoint Keycloak SSO sudah beroperasi live. Tim MBO dapat langsung mengonfigurasi realm, redirect URI, dan token exchange. |
| **Skala Pengguna & Kompatibilitas OS** | • Jumlah Akun Terdaftar di SSO Saat Ini<br>• Target Pengguna Aktif Tahun Pertama<br>• Spesifikasi Minimum OS Android<br>• Spesifikasi Minimum OS iOS | • **2.500 Akun**<br>• **3.500 Pengguna**<br>• **Android 11 / KONDISIONAL**<br>• **iOS 13 / KONDISIONAL** | Beban server terukur (2.500 - 3.500 user). Baseline aplikasi Flutter ditargetkan mendukung Android 8.0+ hingga Android 14+ agar ramah bagi HP masyarakat. |

---

<a name="bagian-5-keamanan-data-pribadi--kepatuhan-regulasi"></a>
## BAGIAN 5: KEAMANAN, DATA PRIBADI, & KEPATUHAN REGULASI

### Pertanyaan 19–20: Uji Keamanan Aplikasi & Kebijakan Privasi
| Aspek Kepatuhan | Isian Jawaban Kuesioner | Target Waktu / PIC | Rencana Mitigasi & Standar Keamanan |
|:---|:---|:---|:---|
| **Uji Keamanan / Pentest (ITSA BSSN)** | **Wajib dilaksanakan** sebelum rilis publik secara luas | **AKHIR NOVEMBER 2026**<br>Pelaksana: Tim Keamanan Siber Diskominfo / BSSN | MBO menerapkan standar OWASP Mobile Top 10 (enkripsi secure storage, SSL Pinning, penutupan kebocoran log, dan proteksi JWT Token). |
| **Kebijakan Privasi (Privacy Policy) & Kepatuhan UU PDP** | Draf kebijakan privasi mengadaptasi dan menyelaraskan kebijakan portal web Pemkab Jombang | **Bidang Aptika Diskominfo Jombang** | Penyusunan dokumen statis URL Kebijakan Privasi yang wajib dicantumkan pada Google Play Console & Apple App Store Connect. |

---

<a name="bagian-6-target-rilis-roadmap-peluncuran--indikator-keberhasilan-kpi"></a>
## BAGIAN 6: TARGET RILIS (ROADMAP), PELUNCURAN, & INDIKATOR KEBERHASILAN (KPI)

### Pertanyaan 21–23: Target Waktu Rilis, Format Peluncuran & Nilai Utama
| Parameter Rilis | Isian Jawaban Responden | Deskripsi Pelaksanaan |
|:---|:---|:---|
| **Target Tanggal Rilis Perdana (Launch Date)** | **GRAND LAUNCH MINGGU KE-4 DESEMBER 2026** | Tanggal target pengesahan dan peluncuran resmi aplikasi JOSS Mobile di hadapan pimpinan daerah. |
| **Format Acara Peluncuran Resmi** | **MELALUI ZOOM KE SELURUH ASN** | Sosialisasi akbar secara daring serentak ke seluruh Sekretariat, Dinas, Badan, Kecamatan, dan Kelurahan. |
| **Headline Value / Slogan Promosi** | *"MUDAH UNTUK MASYARAKAT"* | Pesan utama bahwa aplikasi JOSS menyederhanakan birokrasi, cepat, transparan, dan dapat diakses dari mana saja. |

---

### Pertanyaan 24: Indikator Keberhasilan Utama (KPI) dalam 6 Bulan Pertama
| No | Indikator Kinerja Utama (KPI) | Target Kuantitatif (6 Bulan) | Penjelasan & Rencana Pencapaian |
|:---:|:---|:---:|:---|
| 1 | **Total Unduhan (Downloads)** | **3.500 Unduhan** | Tercapai melalui kewajiban instalasi bagi seluruh ASN Jombang serta sosialisasi publik. |
| 2 | **Pengguna Aktif Bulanan (Monthly Active Users / MAU)** | **2.500 MAU** | Didorong oleh keterikatan rutin harian ASN dalam mengakses E-Office, absensi, dan info TPP. |
| 3 | **Rating Aplikasi di Play Store & App Store** | **Minimal 4.5 / 5.0** | Dijamin melalui kinerja aplikasi yang ringan, bebas force close, UI intuitif, dan responsif. |
| 4 | **Jumlah Layanan OPD Terintegrasi SSO** | **10 Layanan Terintegrasi** | Integrasi bertahap dari 4 aplikasi eksisting awal (E-Office, E-Monev, E-Cloud, Talenta) menuju 10 layanan OPD. |

---

<a name="bagian-7-pelatihan-pengguna--alih-pengetahuan-transfer-of-knowledge--tot"></a>
## BAGIAN 7: PELATIHAN PENGGUNA & ALIH PENGETAHUAN (TRANSFER OF KNOWLEDGE / ToT)

### Pertanyaan 25: Daftar Peserta Pelatihan Alih Pengetahuan (ToT) Diskominfo
| No | Nama Peserta ToT | Unit / Peran Teknis di Diskominfo | Fokus Materi Pelatihan yang Diterima |
|:---:|:---|:---|:---|
| 1 | **ELOK SRI WAHYUNI** | Team Leader / Penanggung Jawab Teknis | Tata kelola sistem, manajemen rilis, dan pemantauan sistem JOSS. |
| 2 | **IRFAN** | Programmer Backend & SSO Specialist | Sinkronisasi data pegawai Keycloak, API Gateway, dan pembuatan REST API. |
| 3 | **RIZKY** | Pengelola Toko Aplikasi & Server Staging | CI/CD build release Flutter, upload Play Store/App Store, dan proxy reverse. |
| 4 | **ALIVIA** | Tim Teknis / Analis Sistem Informasi | Manajemen konten, monitoring bug reporting, dan operasional layanan. |
| 5 | **FATIH** | Tim Teknis / Infrastruktur Jaringan | Mitigasi keamanan server, manajemen traffic proxy, dan konfigurasi SSL. |

---

### Pertanyaan 26: Topik Prioritas Alih Pengetahuan (ToT)
| Prioritas | Topik Pelatihan Khusus | Rincian Modul Pelatihan | Output yang Diharapkan |
|:---:|:---|:---|:---|
| **Topik 1** | **Inject Data Pegawai ke Keycloak** | Scripting/batch user federation, import data kepegawaian ASN, pemetaan role, dan sinkronisasi NIP/User ID | Tim Diskominfo mampu melakukan pembaruan massal akun ASN secara mandiri. |
| **Topik 2** | **Manajemen JOSS (Portal & Admin)** | Pengelolaan master menu, banner, berita, POI, whitelist URL, dan pengaturan hak akses | Diskominfo mandiri mengelola konten aplikasi tanpa ketergantungan pihak ketiga. |
| **Topik 3** | **Manajemen Proxy** | Konfigurasi NGINX reverse proxy, SSL termination, handling redirect URL SSO di In-App WebView | Pemeliharaan koneksi domain aman antar portal web Pemkab. |
| **Topik 4** | **Mitigasi Keamanan Keycloak & Aplikasi** | Patching keamanan, rotasi secret key, proteksi brute-force, pembatasan session, dan penanganan insiden | Ketahanan sistem terhadap upaya peretasan dan kebocoran credential ASN. |

---

<a name="bagian-8-dukungan-pasca-rilis--penanganan-masalah-helpdesk"></a>
## BAGIAN 8: DUKUNGAN PASCA-RILIS & PENANGANAN MASALAH (HELPDESK)

### Pertanyaan 27: Struktur Layanan Bantuan & Dukungan Pengguna (Helpdesk)
| Parameter Helpdesk | Rincian Isian Kuesioner | Standar Prosedur Operasional (SOP) |
|:---|:---|:---|
| **Penanggung Jawab (PIC Helpdesk)** | **ELOK SRI WAHYUNI** | Mengoordinasikan penanganan eskalasi tiket aduan pengguna internal maupun eksternal. |
| **Kanal Layanan yang Disediakan** | • **WhatsApp Center Resmi Diskominfo**<br>• **Formulir Pengaduan di Menu Bantuan JOSS** | Pengguna yang mengalami kendala login SSO atau bug aplikasi dapat melapor secara langsung via chat/form. |
| **Jam Operasional Layanan** | **Hari & Jam Kerja Pemkab Jombang** | Layanan aktif Senin – Jumat (07.30 – 16.00 WIB) dengan sistem pencatatan tiket otomatis. |
| **Kategori Masalah Umum** | Kendala lupa password SSO, aktivasi akun ASN, gagal sinkronisasi presensi E-Office | Disiapkan panduan FAQ (Frequently Asked Questions) di dalam aplikasi mobile. |

---

<a name="bagian-9-struktur-tata-kelola-proyek--tim-penghubung-spoc"></a>
## BAGIAN 9: STRUKTUR TATA KELOLA PROYEK & TIM PENGHUBUNG (SPOC)

### Pertanyaan 28–30: Titik Kontak Tunggal (SPOC), Eskalasi, & Ritme Kerja
| Parameter Tata Kelola | Isian Jawaban Kuesioner Diskominfo | Penjelasan & Mekanisme Kerja Sama |
|:---|:---|:---|
| **Koordinator Teknis Harian (Technical PIC / SPOC)** | • **Nama Lengkap:** **ELOK SRI WAHYUNI**<br>• **Peran dalam Proyek:** **TEAM LEADER**<br>• **Nomor WhatsApp:** **0821-4000-7161** | Menjadi jembatan komunikasi utama (Single Point of Contact) antara Tim Pengembang MBO dan seluruh staf internal Diskominfo Jombang. |
| **Mekanisme Pengambilan Keputusan & Eskalasi** | **Melalui grup koordinasi teknis WhatsApp atau langsung melalui Team Leader (Mbak Elok)** | Isu teknis mendesak diselesaikan dalam hitungan jam; kebijakan strategis dieskalasikan oleh Team Leader ke Kabid Aptika (Bpk. Witcaksono). |
| **Ritme Komunikasi & Pelaporan Kemajuan Proyek** | • **Kanal Harian:** Grup WhatsApp Tim Koordinasi<br>• **Pertemuan Evaluasi:** Rutin Mingguan (Weekly Progress Meeting) via Zoom/Hybrid<br>• **Dokumentasi:** Notulensi tertulis dan status milestone berkala | Transparansi progres pengerjaan sprint mingguan dan pemantauan penyelesaian API backend Programmer Jombang. |

---

## MATRIKS PEMBAGIAN PERAN & TANGGUNG JAWAB (RACI MATRIX)
Berdasarkan hasil pemetaan kuesioner di atas, berikut adalah matriks pembagian tanggung jawab antara **Tim Pengembang Mobile (MBO)** dan **Tim Teknis Diskominfo Jombang**:

| Komponen / Modul Pekerjaan | Tim Pengembang Mobile (MBO) | Programmer Backend Jombang (Mas Irfan) | Store & Infrastruktur Jombang (Mas Rizky) | Koordinator Proyek Jombang (Mbak Elok) |
|:---|:---:|:---:|:---:|:---:|
| **Desain UI/UX & Prototipe Flutter** | **Responsible** (Pelaksana Utama) | Consulted | Consulted | **Accountable** (Pemberi Persetujuan) |
| **Integrasi SSO Keycloak (In-App WebView)** | **Responsible** (Implementasi Mobile) | **Support** (Penyedia Client/Realm) | Informed | Informed |
| **Pengembangan REST API E-Office (5 Endpoint)** | Consulted (Spesifikasi Kebutuhan) | **Responsible** (Pembuat API JSON) | Informed | **Accountable** (Monitoring Progres) |
| **Integrasi Push Notifikasi (FCM)** | **Responsible** (Client Mobile SDK) | **Support** (Backend Trigger) | Informed | Informed |
| **REST API Berita `jombangkab.go.id`** | Consulted (Format Konsumsi) | **Responsible** (Parser/Endpoint) | Informed | Informed |
| **Penyediaan Master Data POI & Kontak 112** | Informed | Support | Support | **Responsible** (Penyedia Data Resmi) |
| **Pelaksanaan Uji Keamanan (ITSA / Pentest)** | Support (Perbaikan Celah) | Support (Celah Backend) | Support (Firewall/Server) | **Responsible** (Jadwal Akhir Nov 2026) |
| **Build & Publikasi Play Store / App Store** | **Responsible** (AAB/IPA & Asset Store) | Informed | **Responsible** (Upload Akun Resmi) | Informed |
| **Pelaksanaan ToT (4 Modul Pelatihan)** | **Responsible** (Trainer / Modul) | **Peserta Aktif** | **Peserta Aktif** | **Peserta Aktif & Penanggung Jawab** |

---

> **Kesimpulan:** Dokumen pemetaan ini mencerminkan 100% fakta dan data hasil isian kuesioner resmi dari Dinas Komunikasi dan Informatika Kabupaten Jombang tanpa ada bagian yang terlewat. Dokumen ini menjadi acuan tunggal dalam penyusunan BRD, Blueprint Arsitektur, serta Backlog Sprint Pengembangan JOSS Mobile Fase 2.
