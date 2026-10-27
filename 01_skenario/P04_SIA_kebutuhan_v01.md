Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan berstatus menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS dan memberikan catatan keputusan.

| ID      | Deskripsi Kebutuhan                                                      |
|---------|--------------------------------------------------------------------------|
| SIA-R01 | Mahasiswa dapat mengakses dan melihat jadwal perkuliahan.                |
| SIA-R02 | Admin akademik dapat mengelola dan mengatur jadwal kuliah.               |
| SIA-R03 | Mahasiswa dapat melakukan pengajuan KRS.                                 |
| SIA-R04 | Sistem secara otomatis memvalidasi KRS dalam proses pengajuan.           |
| SIA-R05 | Mahasiswa dapat mengunduh cetakan bukti setelah mengonfirmasi pengajuan. |
| SIA-R06 | Dosen wali dapat memproses persetujuan maupun penolakan KRS.             |

• Pengguna telah terautentikasi. • Data mata kuliah, prasyarat, dan jadwal tersedia. • Validasi gagal menyebabkan pengajuan belum berhasil tersimpan. • Unduh bukti tidak menjadi syarat keberhasilan pengajuan. • KRS tersimpan belum berarti disetujui. • Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.

| Aktor          | Peran & Tujuan pada Sistem                                                         |
|----------------|------------------------------------------------------------------------------------|
| Admin Akademik | Mengatur dan mengelola data jadwal perkuliahan.                                    |
| Dosen Wali     | Memproses persetujuan maupun penolakan pengajuan KRS.                              |
| Mahasiswa      | Memeriksa jadwal kuliah, melakukan pengajuan KRS, serta mengunduh bukti pengajuan. |

| ID       | Nama Fungsi                            | Aktor Terkait  | Acuan Kebutuhan |
|----------|----------------------------------------|----------------|-----------------|
| SIA-UC01 | Menampilkan jadwal perkuliahan         | Mahasiswa      | SIA-R01         |
| SIA-UC02 | Mengelola data jadwal kuliah           | Admin akademik | SIA-R02         |
| SIA-UC03 | Melakukan pengajuan KRS                | Mahasiswa      | SIA-R03         |
| SIA-UC04 | Memvalidasi kelayakan KRS              | Sistem         | SIA-R04         |
| SIA-UC05 | Mengunduh berkas bukti pengajuan       | Mahasiswa      | SIA-R05         |
| SIA-UC06 | Memproses keputusan KRS (setuju/tolak) | Dosen wali     | SIA-R06         |

SIA-UC03 «include» SIA-UC04 Alasan: pemeriksaan kelengkapan, prasyarat mata kuliah, dan benturan jadwal menjadi bagian validasi pengajuan.

SIA-UC05 «extend» SIA-UC03 Extension point: Bukti pengajuan tersedia. Kondisi: [mahasiswa memilih mengunduh bukti]. Alasan: pengajuan tetap berhasil tanpa pengunduhan bukti.