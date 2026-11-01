# SiOptik — Demo Retail dan Operasional Optik

Demo open access siap GitHub Pages. Referensi desain: galeri SiOptik pada portfolio Nestiara, dengan sidebar putih, aksen biru, kartu dashboard, katalog POS dan data prescription.

## Akun demo publik
Username: demo@dapurkreatif.com
Password: dapurkreatifSCODERS26!
Kredensial ditampilkan pada halaman login. Klik Isi akun demo lalu Masuk ke SiOptik.

## Publikasi GitHub Pages
1. Ekstrak ZIP terlebih dahulu.
2. Buat repository PUBLIC bernama sioptik-demo pada GitHub.
3. Add file > Upload files. Unggah ISI folder SiOptik-Demo, termasuk assets. index.html harus langsung berada pada root repository, sejajar dengan app.js dan style.css. Jangan unggah ZIP sebagai pengganti isi folder.
4. Commit changes.
5. Settings > Pages > Deploy from a branch > main > / (root) > Save.
6. Tunggu deployment selesai. Buka alamat yang ditampilkan di halaman Pages.
7. Jika repository berada pada akun artesiannest dan bernama sioptik-demo, pola alamatnya https://artesiannest.github.io/sioptik-demo/. Alamat tersebut belum dipublikasikan oleh paket ini; gunakan URL yang benar-benar tampil pada GitHub Pages Anda.
8. Pada data kartu portfolio dengan id sioptik, isi demoUrl menggunakan URL deployment tersebut. Jika portofolio memakai CMS, isi kolom URL demo pada CMS. Paket ini tidak mengubah repository portfolio secara otomatis.

Tidak membutuhkan Node.js, npm, build, Supabase atau backend.

## Fitur
- Dashboard: jumlah pelanggan/produk, transaksi hari ini, pesanan diproses, tren tujuh hari, peringatan stok dan transaksi terbaru.
- Pelanggan: tambah, edit, pencarian, detail, riwayat prescription dan riwayat pembelian.
- Prescription: tambah/edit hasil pemeriksaan OD/OS dengan SPH, CYL, AXIS, ADD, PD total, tanggal, nama pemeriksa, dan catatan. OD adalah mata kanan, OS mata kiri. PD menggunakan total binokular dalam mm, bukan PD terpisah per mata. Tidak ada diagnosis atau rekomendasi otomatis.
- Produk: tambah/edit SKU unik, kategori Frame/Lensa/Softlens/Aksesoris, harga modal, harga jual dan stok minimum. Produk baru memiliki stok 0.
- Inventori: penyesuaian stok masuk/keluar dengan alasan dan riwayat mutasi. Stok akhir tidak boleh negatif. Halaman menampilkan 100 mutasi terbaru.
- POS: keranjang multi produk, pilih pelanggan dan prescription miliknya, diskon Rupiah, simulasi metode pembayaran, uang pas, validasi pembayaran, kembalian dan pengurangan stok otomatis. Lensa dijual per unit produk; masukkan kuantitas sesuai kebutuhan.
- Nota: detail transaksi, nama toko/kontak, cetak/PDF lewat dialog browser dan penandaan pesanan selesai. Pembayaran QRIS/transfer/kartu hanya berupa pencatatan metode, tidak menghubungkan payment gateway.
- Laporan: filter tanggal, penjualan bersih setelah diskon, harga pokok saat transaksi, laba kotor, dan export Excel. Workbook berisi Penjualan, Detail Penjualan dan Stok Saat Ini (stok tidak mengikuti filter tanggal).
- Pengaturan: ubah nama/alamat/kontak, cadangkan JSON, pulihkan cadangan tervalidasi dan reset data demo.

## Alur demo
1. Masuk menggunakan akun publik.
2. Pelanggan > Tambah Pelanggan.
3. Prescription > Tambah Prescription, pilih pelanggan tersebut.
4. Produk > tambah produk jika perlu, kemudian Inventori > Penyesuaian Stok untuk stok awalnya.
5. POS Transaksi > pilih produk > pilih pelanggan/resep > isi diskon jika perlu > Isi Uang Pas > Simpan Transaksi.
6. Periksa nota dan stok, lalu lihat Laporan atau export Excel.

## Penyimpanan dan batasan
Data fiktif tersimpan di localStorage masing-masing browser. Perubahan tidak tersinkronisasi antar perangkat/pengunjung. Keluar akun hanya mengakhiri sesi. Reset atau penghapusan data browser menghapus perubahan; unduh cadangan JSON dahulu jika ingin mempertahankannya. Akun publik ini adalah login demonstrasi frontend, bukan autentikasi produksi. Gunakan data pelanggan dan pemeriksaan fiktif. Data awal: 3 pelanggan, 9 produk, 1 prescription dan 10 transaksi historis. Stok awal demo merupakan saldo setelah transaksi historis tersebut; transaksi baru mencatat mutasi pengurangan stok.

## Pemeriksaan
Sintaks JavaScript lulus. Pengujian logika: total transaksi, pengurangan stok, pencatatan mutasi, validasi cadangan, penolakan stok berlebih, diskon berlebih dan pembayaran kurang lulus. Login, ukuran kolom login, transaksi POS dan nota diperiksa melalui browser preview desktop. Belum dipublikasikan ke GitHub; pengujian perangkat fisik belum dilakukan.

Kolom username dan password memiliki lebar serta tinggi sama. Tombol lihat password berada di dalam kolom.

SheetJS Community Edition 0.20.3 disertakan lokal di assets. Lisensi: assets/LICENSE-SheetJS.txt (Apache 2.0).
Dapur Kreatif / SCODE.
