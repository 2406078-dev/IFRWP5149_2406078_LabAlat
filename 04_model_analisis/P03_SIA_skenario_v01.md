# P03_SIA_skenario_v01


## Aktor (berdasarkan interaksi dalam skenario)
| Aktor      | Tujuan terhadap Sistem                                             |
|------------|--------------------------------------------------------------------|
| Mahasiswa  | Melihat jadwal, mengajukan KRS, mengunduh bukti pengajuan          |
| Dosen wali | Memproses persetujuan/penolakan KRS dan memberikan catatan         |

Catatan penting: Admin akademik TIDAK ditambahkan sebagai aktor modul KRS
karena tidak berinteraksi dalam skenario pengajuan KRS. Aktor tersebut
hanya terkait SIA-R02 (kelola jadwal) milik Pertemuan 2.

## Katalog Use Case
| ID       | Nama Use Case              | Aktor Terkait | Sumber  | Peran dalam Model                       |
|----------|----------------------------|---------------|---------|-----------------------------------------|
| SIA-UC03 | Ajukan KRS                 | Mahasiswa     | SIA-R03 | Fungsi utama mahasiswa                  |
| SIA-UC04 | Validasi KRS               | —             | SIA-R04 | Perilaku disertakan (include) oleh UC03 |
| SIA-UC05 | Unduh bukti pengajuan KRS  | Mahasiswa     | SIA-R05 | Tambahan bersyarat (extend) pada UC03   |
| SIA-UC06 | Proses keputusan KRS       | Dosen wali    | SIA-R06 | Fungsi utama dosen wali                 |