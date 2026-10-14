Mahasiswa mengajukan peminjaman peralatan dengan memilih alat,
jumlah, dan rentang waktu. Sistem memeriksa ketersediaan. Jika
tersedia dan data lengkap, sistem menyimpan pengajuan berstatus
menunggu keputusan. Pada tampilan konfirmasi, mahasiswa dapat
memilih mencetak bukti pengajuan. Petugas mengelola data peralatan
serta menyetujui atau menolak pengajuan. Kepala laboratorium melihat
laporan peminjaman.

|  ID   |                                            Kebutuhan                                            |
|-------|-------------------------------------------------------------------------------------------------|
|LAB-R01|                         Mahasiswa dapat melihat ketersediaan peralatan                          |
|LAB-R02|                             Petugas dapat mengelola data peralatan                              |
|LAB-R03|Mahasiswa dapat mengajukan peminjaman; sistem memeriksa ketersediaan sebelum menyimpan pengajuan |
|LAB-R04|            Mahasiswa dapat mencetak bukti pada konfirmasi pengajuan jika memilihnya             |
|LAB-R05|                  Petugas dapat menetapkan persetujuan atau penolakan pengajuan                  |
|LAB-R06|                      Kepala laboratorium dapat melihat laporan peminjaman                       |


Batas sistem dan aturan:
• Sistem mencatat dan menyediakan informasi; perpindahan fisik alat tidak terjadi di dalam perangkat lunak.
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
• Pengajuan yang diterima sistem berstatus Menunggu keputusan, bukanotomatis Disetujui.
• Pengajuan dengan peralatan tidak tersedia tidak disimpan sebagai pengajuan berhasil.
• Pencetakan bukti tidak menjadi syarat keberhasilan pengajuan.
• Persetujuan petugas belum dimodelkan sebagai reservasi teknis stok.
• Pengambilan, pengembalian, kondisi alat, dan denda belum dianalisis pada potongan model ini.

|       Aktor       |                     Tujuanterhadapsistem                      |
|-------------------|---------------------------------------------------------------|
|     Mahasiswa     |Melihatketersediaan, mengajukan peminjaman, dan mencetak bukti |
|Petugaslaboratorium|          Mengelola peralatan dan memproses keputusan          |
|Kepalalaboratorium |                  Melihat laporan peminjaman                   |

|   ID   |       Namausecase        |         Perandalammodel         |
|--------|--------------------------|---------------------------------|
|LAB-UC01|Lihatketersediaanperalatan|      Fungsiutamamahasiswa       |
|LAB-UC02|   Keloladataperalatan    |       Fungsiutamapetugas        |
|LAB-UC03|     Ajukanpeminjaman     |     Fungsi utama mahasiswa      |
|LAB-UC04|   Periksaketersediaan    |  Perilaku yang disertakan UC03  |
|LAB-UC05|   Cetakbuktipengajuan    |  Tambahan bersyarat pada UC03   |
|LAB-UC06|Proseskeputusanpeminjaman |      Fungsi utama petugas       |
|LAB-UC07|  Lihatlaporanpeminjaman  |Fungsi utama kepala laboratorium |


