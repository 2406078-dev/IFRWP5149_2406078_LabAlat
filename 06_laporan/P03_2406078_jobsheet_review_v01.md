Mahasiswa mengajukan peminjaman peralatan dengan memilih alat,jumlah, dan rentang waktu. Sistem memeriksa ketersediaan. Jika
tersedia dan data lengkap, sistem menyimpan pengajuan berstatus menunggu keputusan. Pada tampilan konfirmasi, mahasiswa dapatmemilih mencetak bukti pengajuan. Petugas mengelola data peralatan serta menyetujui atau menolak pengajuan. Kepala laboratorium melihat laporan peminjaman.

NIM: 2406078
Pertemuan: 3 — Use Case Diagram dan Use Case Description
Kasus: SIA (tugas praktik)
Versi: v01


| Situasi | Diagram | Deskripsi | Konsisten? |
|---|---|---|---|
| a. Validasi berhasil & mahasiswa TIDAK unduh bukti | SIA-UC03 selesai (langkah 1–7). SIA-UC05 tidak dipicu karena kondisi [mahasiswa memilih unduh] tidak terpenuhi. | Alur utama UC03 langkah 1–7, tanpa cabang A4; pascakondisi berhasil tercapai (KRS tersimpan). | ✅ Konsisten |
| b. Validasi gagal | SIA-UC04 mengembalikan "tidak valid". UC03 berhenti di langkah 4. Tidak ada penyimpanan. | Alur alternatif UC04 A1/A2/A3 → UC03 A1/A2/A3. Pascakondisi gagal: tidak ada pengajuan baru tersimpan. | ✅ Konsisten |
| c. Validasi berhasil & mahasiswa MEMILIH unduh bukti | SIA-UC05 «extend» dipicu pada extension point "Bukti pengajuan tersedia" di UC03 langkah 6. | UC03 alur utama s.d. langkah 6 → cabang A4 memicu UC05 alur utama → pengajuan tetap tersimpan. | ✅ Konsisten |



| Butir Diperiksa | Temuan | Status |
|---|---|---|
| Arah panah include | UC03 → UC04 (penyerta → disertakan) | ✅ Benar |
| Arah panah extend | UC05 → UC03 (tambahan → dasar) | ✅ Benar |
| Kondisi extend tercantum di diagram | note di UC05: `[mahasiswa memilih unduh]` | ✅ Ada |
| Kondisi extend tercantum di deskripsi | UC03 Extend + A4; UC05 Kondisi | ✅ Ada |
| Extension point berada pada UC dasar | "Bukti pengajuan tersedia" ada di UC03 langkah 6 | ✅ Benar |
| Pascakondisi berhasil & gagal | UC03, UC04, UC05, UC06 masing-masing punya | ✅ Ada |
| Prasyarat dibedakan dari include | Autentikasi ditulis sebagai prasyarat UC03, bukan «include» Login | ✅ Benar |
| Pengajuan tetap berhasil tanpa tambahan | A5 memastikan pengajuan tetap tersimpan bila tidak unduh | ✅ Benar |
| Alur alternatif rujuk nomor langkah | A1–A5 merujuk langkah 3, 4, 6 | ✅ Ada |
| ID/nama sama antara diagram & deskripsi | SIA-UC03/04/05/06 konsisten | ✅ Benar |
| Sumber dapat dibuka kembali | .drawio disimpan di 04_model_analisis/P03/SIA/ | ✅ Ada |
| Ekspor sesuai sumber terkini | .png v01 dari .drawio v01 | ✅ Ada |

**Temuan & Revisi:**
- v01: tidak ada temuan kritis. Semua checklist lulus.
- Bila ada catatan rekan/asisten di kemudian hari, simpan sebagai `v02`
  tanpa menghapus `v01`, dan catat perubahannya di bagian ini.



| No | Butir | Status |
|----|-------|--------|
| 1 | Setiap aktor punya interaksi jelas | ✅ (Mahasiswa → UC03, UC05; Dosen wali → UC06) |
| 2 | Use case sesuai kebutuhan & di dalam batas sistem | ✅ (UC03–UC06 di dalam rectangle) |
| 3 | Include mengarah ke perilaku yang disertakan | ✅ (UC03 → UC04) |
| 4 | Extend mengarah ke use case dasar | ✅ (UC05 → UC03) |
| 5 | Extension point berada pada use case dasar | ✅ (UC03 langkah 6) |
| 6 | Kondisi extend di diagram & deskripsi | ✅ |
| 7 | Pengajuan tetap berhasil tanpa perilaku tambahan | ✅ (A5) |
| 8 | Prasyarat dibedakan dari perilaku include | ✅ |
| 9 | Alur alternatif menjelaskan kegagalan & hasil akhir | ✅ (A1–A5, P1–P2, T1–T4) |
| 10 | Diagram & deskripsi memakai nama/ID sama | ✅ |
| 11 | Sumber dapat dibuka kembali | ✅ (.drawio) |
| 12 | Ekspor sesuai sumber terkini | ✅ (.png v01) |
| 13 | Kebutuhan belum dimodelkan ditandai | ✅ (lihat bagian di bawah) |


