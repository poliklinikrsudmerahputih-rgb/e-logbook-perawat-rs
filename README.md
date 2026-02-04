# e-logbook-perawat-rs
logbookpro
A. Digitalisasi Butir Kegiatan Jabfung (Master Data)
1. Membuat jadwal dinas tenaga perawat, bidan, fisioterapis, terapi gigi dan mulut, psikolg klinis Target 12 (Dokumen)
2. Melakukan operan/Meeting/Pre-Post Conference/Rapat Koordinasi ruangan atau antar instalasi Target 275 (Kegiatan)
3. Melakukan pelaksanaan kegiatan perencanaan pelayanan keperawatan (meliputi perencanaan tenaga, peralatan, dan kegiatan pelayanan) Target 3 (Dokumen)
4. Melakukan penilaian terhadap perawat pelaksana yang berada dibawah tanggung jawabnya Target 12 (Kegiatan)
B. Template Header & Identitas Institusi
1. RSUD MERAH PUTIH KABUPATEN MAGELANG, Unit Kerja Instalasi Rawat Jalan
2. Kabupaten Magelang Kecamatan Mertoyudan
3. LOG BOOK HARIAN PERAWAT
Pemetaan Folder Bukti Fisik
1. Tentukan file apa saja yang diizinkan (misal: .jpg, .png untuk screenshot, .pdf atau .docx untuk laporan).
2. Ukuran Maksimal: maksimal 2MB
Berikut adalah blueprint logika untuk fitur Otomatisasi Tanda Tangan & Header:

1. Logika Tanggal & Lokasi Otomatis
Sistem akan menggunakan logika tanggal untuk menentukan baris titimangsa (tempat & tanggal):

Kabupaten: Diambil otomatis dari data profil "Kab./Kota" yang diisi di awal (misal: Magelang atau Mertoyudan).

Tanggal Akhir Bulan: Sistem akan menghitung hari terakhir bulan tersebut.

Jika pilih Januari, otomatis muncul: Mertoyudan, 31 Januari 2024.

Jika pilih Februari (tahun kabisat), otomatis muncul: Mertoyudan, 29 Februari 2024.

Status Hari: Jika tanggal terakhir bulan tersebut jatuh pada hari Minggu, kita bisa mensetting sistem untuk otomatis mundur ke hari Sabtu (opsional, sesuai aturan instansi Anda).

2. Struktur Layout Tanda Tangan (Print View)
Pada tampilan cetak (Print Preview), bagian bawah tabel akan disusun secara presisi agar sejajar:

Penilai (Atasan Langsung)	Pembuat (Pegawai)




(Nama Atasan Langsung)	(Nama Lengkap Anda)
NIP. (NIP Atasan)	NIP. (NIP Anda)
Data ini ditarik langsung dari Tabel 1 (Users Profile) yang sudah Anda isi di awal.

3. Blueprint Header & Judul Dinamis
Bagian atas laporan akan berubah secara otomatis tergantung filter yang Anda pilih:

Jika Logbook Bulanan:

LOGBOOK KEGIATAN HARIAN PERAWAT BULAN: JANUARI TAHUN 2024

Jika Triwulanan:

REKAPITULASI KEGIATAN TRIWULAN I TAHUN 2024

Setelah judul, di bawahnya langsung muncul blok Identitas Identitas (Nama, NIP, Jabatan, Unit Kerja) sebelum masuk ke tabel utama.

4. Alur Logika (Flowchart) Sistem
Agar Anda memiliki gambaran bagaimana data berpindah tanpa coding, berikut alurnya:

START: User Login.

PROFIL: Sistem cek apakah profil sudah lengkap (termasuk data atasan). Jika belum, paksa isi profil.

INPUT: User pilih tanggal -> pilih Butir Kegiatan (Dropdown) -> isi No. RM -> Upload Bukti.

PROCESSING:

Sistem menyimpan ke logbook_harian.

Sistem menghitung total jumlah kegiatan yang sama dalam satu bulan.

Sistem menghitung: Target−Realisasi=Sisa.

OUTPUT (PRINT):

User klik "Rekap Bulanan" -> Pilih "Maret".

Sistem mengambil Nama Anda & Nama Atasan.

Sistem mencari tanggal terakhir di bulan Maret (tanggal 31).

Sistem menyusun Tabel, Header, dan Footer Tanda Tangan menjadi satu halaman siap cetak.

5. Mengapa ini menguntungkan Anda?
Konsistensi: Format laporan Anda tidak akan pernah berubah-ubah atau berantakan seperti di Excel.

Efisiensi Waktu: Anda tidak perlu mengetik ulang Nama, NIP, atau Tanggal setiap bulan. Cukup input kegiatan, laporan jadi sendiri.

Validitas: Karena data atasan sudah terkunci di profil, link yang dibuka oleh penilai akan selalu menampilkan data yang benar.

Blueprint ini sudah sangat lengkap. Sekarang Anda sudah memiliki:

Konsep Teknologi (Web App + GitHub + Supabase).

Struktur Database (4 Tabel Utama).

Logika Input (Dropdown + No. RM).

Logika Output (Otomatisasi Tanda Tangan & Header).

Apakah Anda ingin saya buatkan draf "Daftar Menu" atau "Site Map" (peta halaman) untuk web ini? Jadi Anda tahu nanti ada tombol apa saja di sidebar-nya.
