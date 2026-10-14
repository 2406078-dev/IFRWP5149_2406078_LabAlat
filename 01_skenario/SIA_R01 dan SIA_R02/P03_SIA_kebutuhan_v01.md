# P03_SIA_kebutuhan_v01

## 1. Skenario

Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan
menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah,
dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan
berstatus menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan,
mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali menyetujui
atau menolak KRS dan memberikan catatan keputusan.

Ketentuan ini fiktif untuk praktikum. Batas SKS, aturan pembayaran, dan
kewenangan institusi nyata tidak boleh ditambahkan tanpa sumber.

---

## 2. Batas Sistem

Sistem Informasi Akademik — modul pengajuan KRS.

- Fokus pemodelan: pengajuan KRS, validasi KRS, unduh bukti, dan
  proses keputusan KRS.
- Di luar batas: pembayaran, pengisian nilai, dan implementasi basis data.

---

## 3. Daftar Kebutuhan

| ID | Kebutuhan |
|---|---|
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah |
| SIA-R02 | Admin akademik dapat mengelola jadwal kuliah |
| SIA-R03 | Mahasiswa dapat mengajukan KRS |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian pengajuan |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan |
| SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS |

Catatan:
- SIA-R01 dan SIA-R02 tetap milik Pertemuan 2 dan tidak dimodelkan ulang
  dalam tugas KRS.
- Kode dimulai dari R03 agar identitas kebutuhan berbeda dari Pertemuan 2.

---

## 4. Aturan dan Asumsi

| Kode | Jenis | Isi |
|---|---|---|
| A-01 | Asumsi | Pengguna telah terautentikasi |
| A-02 | Asumsi | Data mata kuliah, prasyarat, dan jadwal tersedia |
| A-03 | Aturan | Validasi gagal menyebabkan pengajuan belum berhasil tersimpan |
| A-04 | Aturan | Unduh bukti tidak menjadi syarat keberhasilan pengajuan |
| A-05 | Aturan | KRS tersimpan belum berarti disetujui |
| A-06 | Batas | Pembayaran, pengisian nilai, dan implementasi basis data di luar tugas |

---

## 5. Pertanyaan yang Belum Terjawab (ditandai)

- Batas SKS per mahasiswa.
- Aturan pembayaran sebagai prasyarat KRS.
- Kewenangan institusi nyata atas perubahan KRS.

---

## 6. Keterlacakan ke Tahap Berikutnya

| Kebutuhan | Akan dimodelkan sebagai |
|---|---|
| SIA-R03 | Use case Ajukan KRS (SIA-UC03) |
| SIA-R04 | Use case Validasi KRS (SIA-UC04) via «include» pada SIA-UC03 |
| SIA-R05 | Use case Unduh bukti pengajuan KRS (SIA-UC05) via «extend» pada SIA-UC03 |
| SIA-R06 | Use case Proses keputusan KRS (SIA-UC06) |

Catatan:
- SIA-R01 dan SIA-R02 dimodelkan pada Pertemuan 2
  (SIA-UC01 Lihat jadwal kuliah, SIA-UC02 Kelola jadwal kuliah).
- Kebutuhan SIA-R01 dan SIA-R02 tidak dimodelkan ulang pada P03.