# NOTULENSI HASIL MEETING INTERNAL
## TIM PENGEMBANG JOSS MOBILE

> **Format Dokumen:** Transkripsi & Notula Rapat Internal  
> **Topik Bahasan:** Pembahasan Hasil Kuesioner Kominfo Jombang, Batasan E-Office, Kesiapan API, dan Target Rilis  
> **Tanggal Notula:** 14 Oktober 2026  

---

### BUTIR NOTULENSI HASIL RAPAT (ORIGINAL)

1. **berita sudah ada APInya (perlu dipastikan lagi)**
2. **E-office --> presensi saja yang diakomodir (karena bila isinya e-officenya terlalu kompleks karena ada presensi, TPP, dan lain sebagainya)**
3. **bila E office belum ada APInya --> di tanyakan (karena ternyata isinya e office nya mereka terlalu luas)**
4. **fokuskan e office nya yang presensi dulu saja --> sehingga jombang cukup menyiapkan yang presensi saja (perlu diskusi dengan jombang dulu)**
5. **lebih baik dari pada e office mending presensi atau jika mereka sudah punya service APInya aman tinggal panggil**
6. **notifikasi -> ada 2 (grub dan personal)**
7. **request button telepon bisa aman**
8. **yang direktori point of interest perlu dikonfirmasi maksud fiturnya**
9. **batas minimal android perlu dicek dan dipastikan mas imam**
10. **akhir November target penetrating testing**
11. **hasil analisis kebutuhan akan berupa rekomendasi apa saja yang bisa diimplementasikan menyesuaikan Waktu**
12. **Grandlaunchingnya akhir bulan desember (launching ke ASN)**
13. **TOTnya diperjelas perannya Bu Elok, Alivia, Rizki, Irfan,dll**
14. **kanal pengaduan di konfirmasi lewat WA atau email atau call center (perlu dikoordinasi dengan jombang dulu)**
15. **mas jerri bertugas menyiapkan tampilan untuk e-presensi**
16. **Api beritanya ternyata belum bisa dipanggil datanya (perlu konfirmasi lagi dan cek lagi)**
17. **Rekomendasi di android 8 agar cakupannya lebih luas (hampir sama JSS)**
18. **Clearkan Batasan E-office**
19. **disiapkan antifake GPS dan anti costume room**
20. **Goal yang harus bisa dipresentasikan jumat adalah desain dan arsitektur dasar**
21. **Team Jombang rekomendasinya bisa di invite ke Trello (untuk memudahkan proses checklist dan kolaborasi progress)**

---

### TABEL RINCIAN TINDAK LANJUT & PENANGGUNG JAWAB (ACTION ITEMS)

| No | Butir Notulensi | Kategori | Tindak Lanjut / Catatan Teknis | PIC / Penanggung Jawab |
|:---:|:---|:---|:---|:---:|
| 1 | Berita sudah ada API-nya (perlu dipastikan lagi) | Integrasi API | Hubungi Mas Irfan untuk memastikan endpoint resmi dan format JSON | Tim Pengembang / Mas Irfan |
| 2 | E-office $\rightarrow$ presensi saja yang diakomodir | Lingkup Scope | Batasi lingkup native E-Office ke presensi saja karena E-Office terlalu kompleks (ada TPP, aktivitas, approval, dll) | Tim Pengembang |
| 3 | Bila E-office belum ada API-nya $\rightarrow$ ditanyakan | Integrasi API | Tanyakan kepastian ketersediaan API E-Office ke tim Jombang | Tim Pengembang |
| 4 | Fokuskan E-office yang presensi dulu saja | Strategi Scope | Jombang cukup menyiapkan API presensi terlebih dahulu (diskusikan dengan pihak Jombang) | Tim Pengembang / Jombang |
| 5 | Lebih baik presensi atau jika sudah ada service API aman tinggal panggil | Integrasi API | Utamakan presensi, atau jika service API sudah siap maka tim mobile langsung integrasi | Tim Mobile / Mas Irfan |
| 6 | Notifikasi $\rightarrow$ ada 2 (grup dan personal) | Fitur Notifikasi | Siapkan arsitektur FCM: Topic/Broadcast (Grup/Publik) dan Targeted Token (Personal per ASN) | Tim Mobile (Flutter FCM) |
| 7 | Request button telepon bisa aman | Fitur Komunikasi | Fitur panggilan 112 & call center OPD aman diimplementasikan via native phone intent | Tim Mobile |
| 8 | Direktori Point of Interest (POI) perlu dikonfirmasi | Klarifikasi Fitur | Konfirmasi ekspektasi fitur POI ke Diskominfo (cukup list direktori + buka Google Maps) | Tim Analis / Diskominfo |
| 9 | Batas minimal Android dicek dan dipastikan Mas Imam | Arsitektur Mobile | Cek kompatibilitas SDK target dan kestabilan library di Android versi bawah | Mas Imam |
| 10 | Akhir November target penetrating testing | Jadwal & Security | Selesaikan semua fitur inti sebelum akhir November untuk jadwal pentest ITSA BSSN | Seluruh Tim |
| 11 | Hasil analisis kebutuhan berupa rekomendasi sesuai waktu | Manajemen Proyek | Susun dokumen rekomendasi realistis berbasis batas waktu peluncuran | Tim Analis |
| 12 | Grand Launching akhir Desember (launching ke ASN) | Milestone Rilis | Rilis perdana ditargetkan akhir Desember via Zoom khusus pengguna ASN Pemkab | Stakeholder Jombang & Tim |
| 13 | ToT diperjelas perannya Bu Elok, Alivia, Rizki, Irfan, dll | Alih Pengetahuan | Susun matriks peran spesifik materi ToT untuk masing-masing personel Diskominfo | Tim Pengembang |
| 14 | Kanal pengaduan dikonfirmasi (WA/Email/Call Center) | Layanan Bantuan | Koordinasikan saluran pengaduan helpdesk yang aktif (prioritas WhatsApp resmi) | Diskominfo Jombang |
| 15 | Mas Jerri bertugas menyiapkan tampilan untuk e-presensi | UI/UX Desain | Buat desain antarmuka (UI/UX) khusus alur e-presensi untuk presentasi Jumat | Mas Jerri |
| 16 | API berita belum bisa dipanggil datanya | Masalah Teknis | Cek kendala koneksi API berita (CORS/URL/Network) dan mintakan pembaruan endpoint | Tim Pengembang / Mas Irfan |
| 17 | Rekomendasi di Android 8 agar cakupan lebih luas (hampir sama JSS) | Kompatibilitas OS | Tetapkan batas minimal Android 8.0 (API 26) mengacu standar Jogja Smart Service (JSS) | Mas Imam / Tim Mobile |
| 18 | Clearkan Batasan E-office | Batasan Proyek | Buat batasan tegas hitam-di-atas-putih: Native hanya Presensi, sisanya WebView/Report View | Tim Pengembang |
| 19 | Disiapkan anti-fake GPS dan anti-costume room (custom ROM) | Keamanan Presensi | Implementasikan deteksi mock location dan deteksi root/custom ROM pada modul presensi | Tim Mobile (Keamanan) |
| 20 | Goal presentasi Jumat: Desain dan Arsitektur Dasar | Target Mingguan | Siapkan materi presentasi hari Jumat: Mockup UI (Mas Jerri) dan Blueprint Arsitektur | Mas Jerri, Mas Imam, & Tim |
| 21 | Team Jombang rekomendasinya bisa di invite ke Trello | Manajemen Kerja | Buat board Trello bersama untuk checklist tugas, status API backend, dan progress sprint | Koordinator Tim |

---

### DRAF DAFTAR PERTANYAAN & KLARIFIKASI RESMI KE PIHAK DISKOMINFO JOMBANG

> **Catatan Pengantar:**  
> Draf pertanyaan di bawah ini disusun dengan bahasa yang santun, profesional, dan terstruktur agar dapat dikirimkan langsung melalui pesan koordinasi teknis (WhatsApp/Email) maupun menjadi agenda pembahasan pada rapat koordinasi bersama Tim Diskominfo Jombang (Ibu Elok, Mas Irfan, Mas Rizky, dkk).

---

#### 📌 BAGIAN A: PERTANYAAN PRIORITAS UTAMA (DIMULAI DARI POIN 1: API BERITA)

##### 1. Konfirmasi Kesiapan & Endpoint API Berita Daerah (Poin 1 & 16)
*Ditujukan kepada: Mas Irfan (Backend Developer / Tenaga Ahli Jombang)*

> *"Selamat pagi/siang Mas Irfan dan Tim Teknis Diskominfo Jombang,*  
> *Izin menyambung hasil pemetaan kuesioner terkait modul **Berita Daerah (`jombangkab.go.id/berita`)**, dari hasil pengecekan awal tim mobile kami, pemanggilan endpoint data berita saat ini belum dapat ditarik/menampilkan data JSON secara optimal.*  
> 
> *Mohon berkenan arahan dan konfirmasi Mas Irfan terkait beberapa hal teknis berikut:*  
> 1. *Apakah endpoint resmi berita sudah tersedia dalam bentuk REST API JSON siap konsumsi? Jika sudah, mohon dapat dibagikan URL endpoint lengkap beserta contoh format responsnya.*  
> 2. *Apakah pemanggilan API berita membutuhkan otentikasi tertentu (misalnya API Key / Bearer Token) atau bersifat open/public endpoint?*  
> 3. *Apakah kebijakan CORS (Cross-Origin) pada server portal berita sudah diizinkan untuk pemanggilan dari client aplikasi mobile?*  
> 4. *Sebagai alternatif cepat (fallback) agar tidak membebani Mas Irfan, apakah tim mobile kami diperkenankan langsung mengonsumsi endpoint bawaan WordPress REST API (`/wp-json/wp/v2/posts?_embed`) atau RSS Feed XML resmi milik Pemkab Jombang?*  
> 
> *Terima kasih banyak atas bantuan dan arahannya, Mas Irfan."*

---

#### 📌 BAGIAN B: PERTANYAAN & KLARIFIKASI LANJUTAN (RUNUT SESUAI BUTIR NOTULENSI)

##### 2, 3, 4, 5 & 18. Klarifikasi Kebutuhan & Ekspektasi Lingkup Native E-Office
*Ditujukan kepada: Ibu Elok Sri Wahyuni (Team Leader) & Mas Irfan (Backend Developer)*

> *"Izin Ibu Elok dan Mas Irfan,*  
> *Menyambung isian kuesioner terkait modul E-Office yang diharapkan dapat diakses secara mobile native, kami ingin memahami lebih dalam terkait latar belakang dan ekspektasi utamanya:*  
> 
> 1. *Mohon arahan dan gambarannya, apa pertimbangan utama atau pain point yang mendasari kebutuhan modul E-Office ini ingin dibuat secara mobile native? Apakah kebutuhan utamanya lebih condong ke kemudahan presensi harian ASN (yang membutuhkan sensor HP seperti GPS & kamera), atau ada proses operasional tertentu yang memang dirasa mendesak harus native?*  
> 2. *Mengingat sistem E-Office mencakup banyak alur (seperti Presensi, Aktivitas Harian, Approval Atasan, hingga Rincian TPP), di antara modul-modul tersebut, manakah yang menurut Ibu Elok dan tim menjadi prioritas paling mendesak bagi ASN saat peluncuran tahap awal nanti?*  
> 3. *Untuk proses birokrasi yang alurnya cukup panjang (misalnya verifikasi aktivitas atau disposisi naskah dinas), apakah selama ini ada kendala jika ASN tetap mengaksesnya melalui sistem web eksisting, ataukah memang ada target khusus untuk memindahkannya ke mobile?*  
> 4. *Melihat batasan waktu target pengujian keamanan (Pentest BSSN) di akhir November, dari sisi kesiapan backend di Diskominfo Jombang sendiri, apakah saat ini sudah ada rencana atau gambaran kesiapan service API untuk masing-masing bagian E-Office tersebut?*  
> 
> *Pertanyaan ini kami sampaikan agar kami mendapatkan gambaran yang jelas mengenai kebutuhan riil di lapangan, sehingga kita bisa bersama-sama memetakan mana fitur yang paling berdampak langsung bagi ASN dan paling realistis untuk disiapkan.*  
> *Terima kasih banyak atas pencerahan dan arahannya, Bu Elok dan Mas Irfan."*

---

##### 6. Arsitektur Push Notifikasi Terpusat (FCM)
*Ditujukan kepada: Mas Irfan (Backend Developer)*

> *"Terkait fitur Push Notifikasi via Firebase Cloud Messaging (FCM), kami ingin mengonfirmasi kebutuhan distribusinya:*  
> 1. *Apakah sistem notifikasi yang diharapkan mencakup 2 kategori: **(a) Notifikasi Siaran Umum/Grup** (pengumuman daerah untuk seluruh pengguna) dan **(b) Notifikasi Personal** (kedinasan khusus per individu ASN, seperti status absensi atau disposisi surat)?*  
> 2. *Jika mencakup notifikasi personal, apakah backend Jombang siap menyediakan 1 endpoint sederhana untuk menerima penyimpanan `fcm_token` yang dipasangkan dengan data NIP/User ID Keycloak saat pengguna berhasil login?"*

---

##### 7 & 14. Kanal Pengaduan Pengguna & Kontak Darurat 112
*Ditujukan kepada: Ibu Elok Sri Wahyuni & Tim Helpdesk Diskominfo*

> *"Untuk modul Bantuan & Layanan Pengaduan Pengguna di dalam aplikasi JOSS Mobile:*  
> 1. *Apakah untuk kanal helpdesk utama, kami dapat menyematkan tautan direct chat langsung ke **WhatsApp Center Resmi Diskominfo Jombang**? Jika ya, mohon dapat dipastikan nomor WhatsApp yang menjadi pusat admin helpdesk beserta jam operasional pelayanannya.*  
> 2. *Untuk tombol darurat (Emergency Call 112), apakah cukup mengarahkan panggilan langsung ke nomor 112, atau ada nomor kontak darurat OPD lain (RSUD, Damkar, BPBD, Polres) yang perlu kami cantumkan dalam daftar direktori telepon penting?"*

---

##### 8. Konfirmasi Ekspektasi Fitur Direktori Point of Interest (POI)
*Ditujukan kepada: Tim Teknis Diskominfo Jombang*

> *"Terkait fitur direktori Point of Interest (POI) daerah (seperti Wisata, Fasilitas Kesehatan, Layanan Publik):*  
> *Mohon arahan apakah tampilan yang diharapkan cukup berupa **katalog daftar (List View) per kategori yang dilengkapi tombol 'Buka Rute di Google Maps'**, ataukah ada kebutuhan khusus untuk menampilkan peta kustom mandiri di dalam aplikasi? Kami menyarankan opsi pembukaan via Google Maps native agar aplikasi tetap ringan, hemat kuota pengguna, dan akurasi navigasi terjamin."*

---

##### 9 & 17. Usulan Penyesuaian Batas Minimal Versi Android
*Ditujukan kepada: Mas Imam & Tim Teknis Diskominfo Jombang*

> *"Menyambung isian kuesioner mengenai batas minimal Android (yang sebelumnya tercatat Android 11):*  
> *Berdasarkan analisis kompatibilitas perangkat di lapangan (berkaca pada keberhasilan aplikasi daerah seperti Jogja Smart Service / JSS), kami menyarankan batas minimal diturunkan ke **Android 8.0 (Oreo / API Level 26)** dan **iOS 13.0**.*  
> *Hal ini bertujuan agar aplikasi JOSS dapat menjangkau seluruh lapisan masyarakat dan ASN yang masih menggunakan perangkat generasi sebelumnya secara lancar. Apakah dari pihak Diskominfo menyetujui rekomendasi standar OS ini?"*

---

##### 10 & 12. Penyelarasan Jadwal Kritis (Pentest ITSA BSSN & Grand Launching)
*Ditujukan kepada: Ibu Elok Sri Wahyuni & Kabid Aptika (Bpk. Witcaksono)*

> *"Izin mengonfirmasi kembali terkait jadwal pengujian dan peluncuran:*  
> 1. *Apakah target pelaksanaan uji keamanan (Penetration Testing / ITSA BSSN) tetap ditargetkan pada **akhir November 2026**? Kami akan menjadwalkan pembekuan kode (*code freeze*) pada tanggal 20 November 2026 agar aplikasi siap diserahkan ke tim penguji BSSN.*  
> 2. *Terkait rencana Grand Launching pada akhir Desember 2026 via Zoom kepada seluruh ASN, mohon konfirmasi target tanggal pastinya agar kami dapat menyelaraskan jadwal sosialisasi dan masa uji coba pengguna (UAT) sebelum hari peluncuran."*

---

##### 13. Penegasan Peran Personel dalam Pelatihan Alih Pengetahuan (ToT)
*Ditujukan kepada: Ibu Elok Sri Wahyuni*

> *"Untuk memastikan alih pengetahuan (Transfer of Knowledge) berjalan efektif dan aplikatif setelah proyek selesai, kami mengusulkan pembagian materi pelatihan yang terfokus sesuai tupoksi:*  
> 1. *Ibu Elok: Tata Kelola Sistem, SOP Rilis Versi, dan Monitoring Layanan.*  
> 2. *Mas Irfan: Pengembangan & Pemeliharaan Endpoint API serta Manajemen Keycloak SSO.*  
> 3. *Mas Rizky & Mas Fatih: Build Release Flutter, Pengelolaan Akun Store (Google Play & App Store), serta Konfigurasi Proxy.*  
> 4. *Mbak Alivia: SOP Layanan Helpdesk Pengguna & Pengelolaan Konten (Banner, Berita, POI).*  
> *Apakah pembagian peran ini sudah sesuai dengan struktur tim internal Diskominfo Jombang?"*

---

##### 21. Usulan Penggunaan Trello untuk Kolaborasi & Checklist Tugas Harian
*Ditujukan kepada: Seluruh Tim Teknis Diskominfo Jombang*

> *"Agar proses koordinasi teknis, pemantauan pembuatan endpoint API oleh Mas Irfan, dan progres pengerjaan mobile oleh tim kami dapat terpantau secara transparan dan terukur tanpa tumpang tindih chat di WhatsApp, kami mengusulkan pembuatan papan kerja bersama di **Trello**.*  
> *Mohon perkenan alamat email Ibu Elok, Mas Irfan, Mas Rizky, dan tim terkait agar dapat segera kami kirimkan undangan board Trello **'JOSS Mobile - Sinergi Dev & API'**."*
