SIA-UC03 — Ajukan KRS
Elemen	Isi
ID dan nama	SIA-UC03 — Ajukan KRS
Sumber kebutuhan	SIA-R03, SIA-R04, SIA-R05
Tujuan	Menghasilkan pengajuan KRS yang tersimpan dengan status Menunggu persetujuan dosen wali
Aktor utama	Mahasiswa
Aktor pendukung	—
Pemicu	Mahasiswa memilih fungsi pengajuan KRS
Prasyarat	Mahasiswa telah terautentikasi; data mata kuliah, prasyarat, dan jadwal tersedia
Include	SIA-UC04 — Validasi KRS
Extension point	Bukti pengajuan tersedia (pada langkah 6)
Extend	SIA-UC05 jika [mahasiswa memilih unduh]
Pascakondisi berhasil	Pengajuan KRS tersimpan dengan nomor dan status Menunggu persetujuan dosen wali
Pascakondisi gagal	Tidak ada pengajuan KRS baru yang berhasil tersimpan
Aturan bisnis/asumsi	KRS tersimpan belum berarti disetujui; unduh bukti bukan syarat keberhasilan

Alur utama
Langkah	Tindakan Mahasiswa	Respons Sistem
1	Membuka menu pengajuan KRS	Menampilkan formulir pemilihan mata kuliah
2	Memilih mata kuliah	Menampung isian
3	Mengirim pengajuan KRS	Memeriksa kelengkapan isian
4	—	Menjalankan SIA-UC04 (Validasi KRS)
5	—	Jika validasi berhasil, menyimpan pengajuan & memberi nomor
6	Melihat konfirmasi	Menampilkan nomor & status Menunggu persetujuan; mencapai extension point
7	Mengakhiri pengajuan	Menutup proses pengajuan

Alur alternatif / pengecualian
Kode	Rujukan Langkah	Kondisi	Aksi Sistem	Hasil Akhir
A1	Langkah 3	Data isian tidak lengkap	Menolak pengiriman & menampilkan pesan	Pengajuan tidak tersimpan; kembali ke langkah 2
A2	Langkah 4	Prasyarat mata kuliah tidak terpenuhi	SIA-UC04 mengembalikan "tidak valid" + daftar MK	Pengajuan tidak tersimpan; kembali ke langkah 2
A3	Langkah 4	Terjadi benturan jadwal	SIA-UC04 mengembalikan "tidak valid" + detail konflik	Pengajuan tidak tersimpan; kembali ke langkah 2
A4	Langkah 6	Validasi berhasil + mahasiswa memilih unduh	Menjalankan SIA-UC05 «extend»	Pengajuan tetap tersimpan; bukti terunduh
A5	Langkah 6	Validasi berhasil + mahasiswa TIDAK unduh	Tidak memicu extend	Pengajuan tetap tersimpan; proses selesai

SIA-UC04 — Validasi KRS
Elemen	Isi
ID dan nama	SIA-UC04 — Validasi KRS
Sumber kebutuhan	SIA-R04
Tujuan	Memastikan KRS memenuhi kelengkapan, prasyarat mata kuliah, dan bebas benturan jadwal
Aktor utama	— (dipanggil sebagai «include» dari SIA-UC03)
Aktor pendukung	—
Pemicu	Dipanggil oleh SIA-UC03 pada langkah 4
Prasyarat	Data mata kuliah, prasyarat, dan jadwal tersedia; isian KRS sudah lengkap
Pascakondisi berhasil	Status "valid" dikembalikan kepada SIA-UC03
Pascakondisi gagal	Status "tidak valid" beserta alasan (prasyarat/benturan) dikembalikan
Aturan bisnis/asumsi	Validasi gagal menyebabkan pengajuan belum berhasil tersimpan

Alur utama
Langkah	Tindakan	Respons Sistem
1	—	Menerima data KRS dari SIA-UC03
2	—	Memeriksa kelengkapan data
3	—	Memeriksa prasyarat setiap mata kuliah
4	—	Memeriksa benturan jadwal antar mata kuliah
5	—	Mengembalikan status "valid" ke SIA-UC03

Alur alternatif / pengecualian
Kode	Rujukan Langkah	Kondisi	Aksi	Hasil
A1	Langkah 2	Data tidak lengkap	Kembalikan "tidak valid" + alasan	SIA-UC03 lanjut A1
A2	Langkah 3	Prasyarat tidak terpenuhi	Kembalikan "tidak valid" + daftar MK	SIA-UC03 lanjut A2
A3	Langkah 4	Benturan jadwal	Kembalikan "tidak valid" + detail	SIA-UC03 lanjut A3

SIA-UC05 — Unduh bukti pengajuan KRS
Elemen	Isi
ID dan nama	SIA-UC05 — Unduh bukti pengajuan KRS
Sumber kebutuhan	SIA-R05
Tujuan	Menyediakan berkas bukti pengajuan KRS yang dapat diunduh mahasiswa
Aktor utama	Mahasiswa
Aktor pendukung	—
Pemicu	Mahasiswa memilih unduh bukti pada konfirmasi penyimpanan
Prasyarat	Pengajuan KRS berhasil tersimpan (SIA-UC03 selesai sampai langkah 6)
Extend	SIA-UC05 «extend» SIA-UC03
Extension point	Bukti pengajuan tersedia
Kondisi	[mahasiswa memilih unduh]
Pascakondisi berhasil	Berkas bukti terunduh; pengajuan tetap tersimpan
Pascakondisi gagal	Bukti tidak terunduh; pengajuan tetap tersimpan (tidak memengaruhi keberhasilan)
Aturan bisnis/asumsi	Unduh bukti tidak menjadi syarat keberhasilan pengajuan

Alur utama
Langkah	Tindakan Mahasiswa	Respons Sistem
1	Memilih unduh bukti pada konfirmasi	Menyiapkan berkas bukti pengajuan
2	Menunggu proses unduh	Mengirim berkas ke perangkat mahasiswa
3	Menerima berkas	Menampilkan notifikasi unduhan berhasil

Alur alternatif / pengecualian
Kode	Rujukan Langkah	Kondisi	Aksi	Hasil
A1	Langkah 2	Unduhan gagal (jaringan/berkas)	Tampilkan pesan gagal unduh	Pengajuan tetap tersimpan; mahasiswa dapat mencoba lagi

SIA-UC06 — Proses keputusan KRS
Elemen	Isi
ID dan nama	SIA-UC06 — Proses keputusan KRS
Sumber kebutuhan	SIA-R06
Tujuan	Menetapkan persetujuan atau penolakan KRS beserta catatan keputusan
Aktor utama	Dosen wali
Aktor pendukung	—
Pemicu	Dosen wali memilih KRS berstatus menunggu
Prasyarat	Dosen wali telah terautentikasi; terdapat pengajuan KRS berstatus Menunggu persetujuan
Pascakondisi berhasil	Status KRS berubah menjadi Disetujui atau Ditolak; catatan keputusan tersimpan
Pascakondisi gagal	Status KRS tidak berubah; keputusan tidak tersimpan
Aturan bisnis/asumsi	KRS tersimpan belum berarti disetujui

Alur utama
Langkah	Tindakan Dosen Wali	Respons Sistem
1	Membuka daftar KRS menunggu	Menampilkan daftar pengajuan KRS
2	Memilih satu pengajuan	Menampilkan detail KRS mahasiswa
3	Memeriksa isi KRS	Menampilkan mata kuliah, prasyarat, jadwal
4	Menetapkan keputusan	Menerima keputusan (setuju/tolak)
5	Mengisi catatan keputusan	Menampung catatan
6	Mengirim keputusan	Menyimpan status baru & catatan
7	—	Menampilkan konfirmasi perubahan status

Alur alternatif / pengecualian — Persetujuan
Kode	Rujukan Langkah	Kondisi	Aksi	Hasil
P1	Langkah 4	Dosen memilih "Setujui"	Menetapkan status Disetujui	Status KRS menjadi Disetujui
P2	Langkah 6	Penyimpanan berhasil	Simpan status + catatan	Pascakondisi berhasil tercapai

Alur alternatif / pengecualian — Penolakan
Kode	Rujukan Langkah	Kondisi	Aksi	Hasil
T1	Langkah 4	Dosen memilih "Tolak"	Menetapkan status Ditolak	Status KRS menjadi Ditolak
T2	Langkah 5	Catatan wajib untuk penolakan	Meminta/menampung catatan	Catatan tersimpan bersama keputusan
T3	Langkah 6	Gagal simpan	Tampilkan pesan gagal	Status tidak berubah; dosen dapat mengulang
T4	Langkah 2	KRS sudah pernah diputuskan	Sistem menolak pemrosesan ulang