Batas sistem dan aturan
• Sistem mencatat dan menyediakan informasi; perpindahan fisik alat tidak
terjadi di dalam perangkat lunak (tetap dari Pertemuan 3).
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran (tetap
dari Pertemuan 3).
• Pengembalian hanya dapat dicatat untuk peminjaman berstatus Dipinjam.
Peminjaman yang masih Menunggu Keputusan atau Ditolak tidak dapat
dicatat pengembaliannya.
• Kondisi peralatan pada pengembalian dicatat dengan salah satu nilai: Baik,
Rusak Ringan, atau Rusak Berat.
• Hapus Data Peralatan hanya untuk peralatan yang tidak sedang dipinjam
dan tidak memiliki pengajuan aktif.
• Keterlambatan dan denda belum dimodelkan pada pertemuan ini. Tuliskan
sebagai pertanyaan terbuka pada berkas kebutuhan, jangan mengarang
aturan denda.
• Kriteria penerimaan model: semua kebutuhan LAB-R01 sampai LAB-R11
mempunyai representasi pada diagram kumulatif, arah generalization dan
realization benar, dan diagram konsisten dengan deskripsinya.

Langkah 2: Tentukan aktor umum dan aktor khusus

|         Aktor         |  Kedudukan  |    Tujuan     terhadap                                                                        sistem                                                                         |
|-----------------------|-------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       Peminjam        |    Umum     (general),baru   pada pertemuan4   |                             Peran umum bagi peminjam peralatan.Mewariskan fungsinya kepada Mahasiswa dan dosen                             |
|       Mahasiswa       |   Khusus    dariPeminjam, tetapdari Pertemuan 3  |Melihat ketersediaan dan mengajukanpeminjaman (diwarisi dari Peminjam),ditambah mencetak bukti pengajuansebagai asosiasi khususnya sendiri. |
|         Dosen         |   Khusus         dari     Peminjam, |                              barupada Pertemuan 4Melihat ketersediaan dan mengajukanpeminjaman (diwarisi dari Peminjam).                              |
|  PetugasLaboratorium  |    Tetap     dariPertemuan 3|Mengelola                                  data peralatan, memproseskeputusan peminjaman, dan mencatatpengembalian peralatan.                                   |
|KepalaLaboratorium|TetapdariPertemuan   3|Melihat    laporan                                                                      peminjaman                                                                       |

Langkah 3: Susun katalog use case
|   ID   |Nama_Use_Case|Peran_dalam_Model|                                                      Sumber_Kebutuhan                                                      |
|--------|-------------|-----------------|----------------------------------------------------------------------------------------------------------------------------|
|LAB-UC01|    Lihat      Ketersediaan   |                       Peralatan Tetap dari Pertemuan 3;| fungsi aktor umum peminjam LAB-R01, LAB-R07                        |
|LAB-UC02|   Kelola          Data       |           Peralatan Tetap dari Pertemuan 3;| use case umum bagi LAB-UC08, LAB-UC09, dan LAB-UC10 LAB-R02, LAB-R08           |
|LAB-UC03|   Ajukan       Peminjaman    |Tetap dari Pertemuan 3; fungsi aktor umum peminjam, menyertakan LAB-UC04, dan direalisasikan oleh LAB-CO01 LAB-R03, LAB-R07 |
|LAB-UC04|   Periksa     Ketersediaan   |                      Tetap dari Pertemuan 3;| perilaku yang disertakan (include) oleh LAB-UC03 LAB-R03                      |
|LAB-UC05|    Cetak          Bukti      |                 Pengajuan Tetap dari Pertemuan 3;| tambahan bersyarat pada LAB-UC03 melalui extend LAB-R04                  |
|LAB-UC06|   Proses        Keputusan    |                              Peminjaman Tetap dari Pertemuan 3;| fungsi utama petugas LAB-R05                               |
|LAB-UC07|    Lihat         Laporan     |                        Peminjaman Tetap dari Pertemuan 3;| fungsi utama kepala laboratorium LAB-R06                         |
|LAB-UC08|   Tambah          Data       |                           Peralatan Baru pada Pertemuan 4;| use case khusus dari LAB-UC02 LAB-R08                           |
|LAB-UC09|    Ubah           Data       |                           Peralatan Baru pada Pertemuan 4;| use case khusus dari LAB-UC02 LAB-R08                           |
|LAB-UC10|    Hapus          Data       |                           Peralatan Baru pada Pertemuan 4;| use case khusus dari LAB-UC02 LAB-R08                           |


|   ID   |Nama_Use_Case|Peran_dalam_Model|                                      Sumber_Kebutuhan                                      |
|--------|-------------|-----------------|--------------------------------------------------------------------------------------------|
|LAB-UC10|    Hapus          Data       |                      Peralatan Use case khusus dari LAB-UC02 LAB-R08                       |
|LAB-UC11|    Catat      Pengembalian   |Peralatan Baru pada Pertemuan 4;| fungsi utama petugas; direalisasikan oleh LAB-CO02 LAB-R09 |
|LAB-UC12|   Periksa        Kondisi     | Peralatan Baru pada Pertemuan 4;| perilaku yang disertakan (include) oleh LAB-UC11 LAB-R09  |

Langkah 4: Tetapkan generalization aktor
• Mahasiswa adalah bentuk khusus dari Peminjam, dan Dosen adalah bentuk khusus dari Peminjam. Alasan: keduanya berbagi fungsi yang sama, yaitu melihat ketersediaan peralatan dan mengajukan peminjaman.
• Asosiasi ke LAB-UC01 dan LAB-UC03 digambar satu kali, yaitu dari Peminjam. Jangan menggambar garis yang sama dari Mahasiswa dan dari Dosen.
• Asosiasi Mahasiswa ke LAB-UC05 Cetak Bukti Pengajuan tidak ikut dipindahkan dan tidak dihapus, karena fungsi itu khusus mahasiswa. Asosiasi ini menjadi contoh asosiasi tambahan milik aktor khusus.
• Periksa arah panah pada gambar: ujung segitiga kosong harus menempel pada Peminjam, bukan pada Mahasiswa dan bukan pada Dosen. Karena Peminjam digambar di tengah, panah Mahasiswa mengarah ke bawah dan panah Dosen mengarah ke atas; keduanya berakhir pada Peminjam

Langkah 5: Tetapkan generalization use case
• LAB-UC08, LAB-UC09, dan LAB-UC10 adalah bentuk khusus dari LABUC02 Kelola Data Peralatan. Alasan: ketiganya adalah bentuk khusus pengelolaan data peralatan.
• Tuliskan untuk setiap use case khusus satu kalimat perilaku pembedanya. Tambah menghasilkan data peralatan baru. Ubah menghasilkan data peralatan yang berubah. Hapus menghasilkan data peralatan yang terhapus dengan syarat pada aturan studi kasus.


