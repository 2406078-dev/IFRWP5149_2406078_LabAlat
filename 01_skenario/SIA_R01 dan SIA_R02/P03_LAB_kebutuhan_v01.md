# P03_LAB_kebutuhan_v01

| Metadata | Isi |
|---|---|
| NIM | 2406078 |
| Kasus | LAB — Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus |
| Artefak | Kebutuhan dan Batas |
| Versi | v01 |
| Pertemuan | 3 |

---

## 1. Skenario

Mahasiswa mengajukan peminjaman peralatan dengan memilih alat, jumlah, dan
rentang waktu. Sistem memeriksa ketersediaan. Jika tersedia dan data lengkap,
sistem menyimpan pengajuan berstatus menunggu keputusan. Pada tampilan
konfirmasi, mahasiswa dapat memilih mencetak bukti pengajuan. Petugas
mengelola data peralatan serta menyetujui atau menolak pengajuan. Kepala
laboratorium melihat laporan peminjaman.

---

## 2. Batas Sistem

Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus.

- Sistem mencatat dan menyediakan informasi.
- Perpindahan fisik alat tidak terjadi di dalam perangkat lunak.

---

## 3. Daftar Kebutuhan

| ID | Kebutuhan |
|---|---|
| LAB-R01 | Mahasiswa dapat melihat ketersediaan peralatan |
| LAB-R02 | Petugas dapat mengelola data peralatan |
| LAB-R03 | Mahasiswa dapat mengajukan peminjaman; sistem memeriksa ketersediaan sebelum menyimpan pengajuan |
| LAB-R04 | Mahasiswa dapat mencetak bukti pada konfirmasi pengajuan jika memilihnya |
| LAB-R05 | Petugas dapat menetapkan persetujuan atau penolakan pengajuan |
| LAB-R06 | Kepala laboratorium dapat melihat laporan peminjaman |

Catatan: LAB-R01 dan LAB-R02 dipertahankan dari Pertemuan 2.
Kebutuhan berikutnya menambah ruang lingkup analisis tanpa mengubah arti
kebutuhan lama.

---

## 4. Aturan dan Asumsi

| Kode | Jenis | Isi |
|---|---|---|
| A-01 | Asumsi | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran |
| A-02 | Aturan | Pengajuan yang diterima berstatus Menunggu keputusan, bukan otomatis Disetujui |
| A-03 | Aturan | Pengajuan dengan peralatan tidak tersedia tidak disimpan sebagai pengajuan berhasil |
| A-04 | Aturan | Pencetakan bukti tidak menjadi syarat keberhasilan pengajuan |
| A-05 | Aturan | Persetujuan petugas belum dimodelkan sebagai reservasi teknis stok |
| A-06 | Batas | Pengambilan, pengembalian, kondisi alat, dan denda belum dianalisis pada potongan model ini |

---

## 5. Pertanyaan yang Belum Terjawab (ditandai)

- Aturan denda keterlambatan pengembalian.
- Mekanisme reservasi teknis stok setelah persetujuan petugas.
- Kondisi alat saat dikembalikan dan konsekuensinya.

---

## 6. Keterlacakan ke Tahap Berikutnya

| Kebutuhan | Akan dimodelkan sebagai |
|---|---|
| LAB-R01 | Use case Lihat ketersediaan peralatan (LAB-UC01) |
| LAB-R02 | Use case Kelola data peralatan (LAB-UC02) |
| LAB-R03 | Use case Ajukan peminjaman (LAB-UC03) + include Periksa ketersediaan (LAB-UC04) |
| LAB-R04 | Use case Cetak bukti pengajuan (LAB-UC05) extend LAB-UC03 |
| LAB-R05 | Use case Proses keputusan peminjaman (LAB-UC06) |
| LAB-R06 | Use case Lihat laporan peminjaman (LAB-UC07) |