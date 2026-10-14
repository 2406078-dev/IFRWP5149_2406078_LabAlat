# P03_SIA_kebutuhan_v01
NIM: 2406078
Kasus: SIA — Sistem Informasi Akademik
Versi: v01
Tanggal: <isi sendiri>

## Skenario
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan
menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah,
dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan
berstatus menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan,
mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali menyetujui
atau menolak KRS dan memberikan catatan keputusan.

Ketentuan ini fiktif untuk praktikum. Batas SKS, aturan pembayaran, dan
kewenangan institusi nyata tidak boleh ditambahkan tanpa sumber.

## Batas Sistem
Sistem Informasi Akademik — modul pengajuan KRS.

## Daftar Kebutuhan (SIA-R03 s.d. SIA-R06)
| ID      | Kebutuhan                                                                 |
|---------|---------------------------------------------------------------------------|
| SIA-R03 | Mahasiswa dapat mengajukan KRS                                            |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian pengajuan                           |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan |
| SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS                 |

Catatan: SIA-R01 & SIA-R02 (jadwal kuliah) tetap milik Pertemuan 2,
tidak dimodelkan ulang pada tugas ini.

## Asumsi
- Pengguna telah terautentikasi.
- Data mata kuliah, prasyarat, dan jadwal tersedia.

## Aturan
- Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
- Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
- KRS tersimpan belum berarti disetujui.
- Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.

## Pertanyaan Belum Terjawab (di luar lingkup, ditandai)
- Batas SKS per mahasiswa.
- Aturan pembayaran sebagai prasyarat KRS.
- Kewenangan institusi nyata atas perubahan KRS.