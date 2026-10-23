<!-- SKENARIO P04 -->
Skenario berikut merupakan bahan latihan yang ditetapkan untuk jobsheet, bukan hasil pengumpulan kebutuhan laboratorium nyata. Skenario ini melanjutkan potongan model Pertemuan 3.
 Selain mahasiswa, dosen juga meminjam peralatan laboratorium untuk kegiatan praktikum dan penelitian. Mahasiswa dan dosen sama-sama dapat melihat ketersediaan peralatan dan mengajukan peminjaman. Petugas laboratorium mengelola data peralatan: menambah peralatan baru, mengubah data peralatan, dan menghapus data peralatan yang tidak lagi dipakai. Setelah peminjaman disetujui dan alat diambil, petugas
mencatat pengembalian peralatan. Pada saat mencatat pengembalian, petugas memeriksa dan mencatat kondisi peralatan. Dua use case utama pada potongan model ini, Ajukan Peminjaman dan Catat Pengembalian Peralatan, ditunjukkan realisasinya oleh collaboration yang bersesuaian.
Seluruh fungsi Pertemuan 3 tetap berlaku dan tetap digambar: pemeriksaan ketersediaan di dalam pengajuan, pencetakan bukti pengajuan oleh mahasiswa, proses keputusan peminjaman oleh petugas,dan laporan peminjaman untuk kepala laboratorium. Diagram Pertemuan 4 adalah diagram Pertemuan 3 yang ditambah, bukan diagram baru yang menggantikannya.


<!-- Aktor umum dan khusus -->

| Aktor                | Kedudukan                                    |                       Tujuan terhadap sistem                                                   |
|---------------------------------------------------------------------|--------------|---------------------------------------------------------------------------------|
| Mahasiswa            | Khusus dari Peminjam, tetap dari Pertemuan 3 | Melihat ketersediaan dan mengajukan peminjaman (diwarisi dari Peminjam), ditambah mencetak bukti pengajuan sebagai asosiasi khususnya sendiri. |
| Dosen                | Khusus dari Peminjam, baru pada Pertemuan 4  | Melihat ketersediaan dan mengajukan peminjaman (diwarisi dari Peminjam).                       |
| Kepala Laboratorium  | Tetap dari Pertemuan 3                       | Melihat laporan peminjaman. |
| Petugas Laboratorium | Tetap dari Pertemuan 3                       | Mengelola data peralatan, memproses keputusan peminjaman, dan mencatat pengembalian peralatan. |
| Peminjam             | Umum (general), baru pada Pertemuan 4        | Peran umum bagi peminjam peralatan. Mewariskan fungsinya kepada Mahasiswa dan Dosen. |


<!-- katalog use case -->
| ID       | Nama use case                |                                     Peran dalam model                                             | Sumber kebutuhan |
|----------|------------------------------|---------------------------------------------------------------------------------------------------|------------------|
| LAB-UC01 | Lihat Ketersediaan Peralatan | Tetap dari Pertemuan 3; fungsi aktor umum Peminjam                                                | LAB-R01, LAB-R07 |
| LAB-UC02 | Kelola Data Peralatan        | Tetap dari Pertemuan 3; use case UMUM bagi LAB-UC08, LAB-UC09, LAB-UC10                           | LAB-R02, LAB-R08 |
| LAB-UC03 | Ajukan Peminjaman            | Tetap dari Pertemuan 3; fungsi aktor umum Peminjam; menyertakan LAB-UC04; direalisasikan LAB-CO01 | LAB-R03, LAB-R07 |
| LAB-UC04 | Periksa Ketersediaan         | Tetap dari Pertemuan 3; perilaku yang disertakan LAB-UC03                                         | LAB-R03 |        |
| LAB-UC05 | Cetak Bukti Pengajuan        | Tetap dari Pertemuan 3; tambahan bersyarat pada LAB-UC03 melalui «extend»                         | LAB-R04 |        |
| LAB-UC06 | Proses Keputusan Peminjaman  | Tetap dari Pertemuan 3; fungsi utama petugas                                                      | LAB-R05 |        |
| LAB-UC07 | Lihat Laporan Peminjaman     | Tetap dari Pertemuan 3; fungsi utama kepala laboratorium                                          | LAB-R06 |        |
| LAB-UC08 | Tambah Data Peralatan        | Baru pada Pertemuan 4; use case KHUSUS dari LAB-UC02                                              | LAB-R08 |        |
| LAB-UC09 | Ubah Data Peralatan          | Baru pada Pertemuan 4; use case KHUSUS dari LAB-UC02                                              | LAB-R08 |        |
| LAB-UC10 | Hapus Data Peralatan         | Baru pada Pertemuan 4; use case KHUSUS dari LAB-UC02                                              | LAB-R08 |        |
| LAB-UC11 | Catat Pengembalian Peralatan | Baru pada Pertemuan 4; fungsi utama petugas; direalisasikan LAB-CO02                              | LAB-R09 |        |
| LAB-UC12 | Periksa Kondisi Peralatan    | Baru pada Pertemuan 4; perilaku yang disertakan LAB-UC11                                          | LAB-R10 |        |

<!-- Tetapkan collaboration dan realization  -->
| ID       | Nama collaboration (sama dengan nama use case) | Use case yang direalisasikan           |
|----------|------------------------------------------------|----------------------------------------|
| LAB-CO01 | Ajukan Peminjaman                              | LAB-UC03: Ajukan Peminjaman            |
| LAB-CO02 | Catat Pengembalian Peralatan                   | LAB-UC11: Catat Pengembalian Peralatan |

<!-- Tulis use case description baru -->

Elemen LAB-UC11: Catat Pengembalian Peralatan
ID dan nama LAB-UC11: Catat Pengembalian Peralatan
Institut Teknologi Garut S1 Teknik Informatika
Praktikum Analisis dan Desain Berorientasi Objek | 58
Elemen LAB-UC11: Catat Pengembalian Peralatan
Sumber kebutuhan LAB-R09 dan LAB-R10
Tujuan Pengembalian tercatat dan status peminjaman serta kondisi
peralatan terbarui
Aktor utama Petugas Laboratorium
Pemicu Petugas memilih fungsi pencatatan pengembalian dan
menentukan peminjaman yang akan dikembalikan
Prasyarat Petugas telah terautentikasi; peminjaman terpilih berstatus
Dipinjam
Pascakondisi
berhasil
Pengembalian tercatat dengan tanggal kembali dan kondisi
peralatan; status peminjaman menjadi Selesai
Pascakondisi gagal Tidak ada pengembalian baru yang tercatat; status
peminjaman tidak berubah
Include LAB-UC12: Periksa Kondisi Peralatan
Collaboration LAB-CO02: Catat Pengembalian Peralatan
