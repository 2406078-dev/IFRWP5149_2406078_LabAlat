### SIA-UC08: Input Nilai Mata Kuliah

| Elemen | SIA-UC08: Input Nilai Mata Kuliah |
| --- | --- |
| **ID dan nama** | SIA-UC08: Input Nilai Mata Kuliah |
| **Sumber kebutuhan** | SIA-R08 dan SIA-R12 |
| **Tujuan** | Memasukkan dan menyimpan data nilai mata kuliah mahasiswa yang diampu |
| **Aktor utama** | Dosen |
| **Pemicu** | Dosen memilih fungsi input nilai dan menentukan mata kuliah serta kelas yang diampu |
| **Prasyarat** | Dosen telah terautentikasi; Dosen adalah pengampu mata kuliah yang bersangkutan |
| **Pascakondisi berhasil** | Data nilai mahasiswa berhasil tersimpan di dalam sistem dan siap dipublikasikan |
| **Pascakondisi gagal** | Data nilai tidak tersimpan (nilai di luar rentang yang sah ditolak); status nilai tidak berubah |
| **Collaboration** | SIA-CO01: Input Nilai Mata Kuliah |

### SIA-UC09: Lihat KHS

| Elemen | SIA-UC09: Lihat KHS |
| --- | --- |
| **ID dan nama** | SIA-UC09: Lihat KHS |
| **Sumber kebutuhan** | SIA-R09 dan SIA-R12 |
| **Tujuan** | Menampilkan Kartu Hasil Studi (KHS) mahasiswa untuk semester yang nilainya sudah dipublikasikan |
| **Aktor utama** | Mahasiswa |
| **Pemicu** | Mahasiswa memilih fungsi lihat KHS dan menentukan semester yang ingin dilihat |
| **Prasyarat** | Mahasiswa telah terautentikasi; nilai semester yang dipilih sudah dipublikasikan oleh bagian akademis |
| **Pascakondisi berhasil** | KHS beserta rincian nilai, SKS, dan Indeks Prestasi (IP) semester terpilih berhasil ditampilkan |
| **Pascakondisi gagal** | KHS tidak ditampilkan dan sistem memberikan pesan bahwa nilai semester belum dipublikasikan |
| **Collaboration** | SIA-CO02: Lihat KHS |
