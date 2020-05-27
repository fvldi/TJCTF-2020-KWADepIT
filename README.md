# Dokumentasi TJCTF 2020 - KWA Dep IT
[![Fvldi code style](https://img.shields.io/badge/Author-Fvldi-6886c5)](https://github.com/fvldi)
[![Name](https://img.shields.io/badge/Name-Muhamad%20Rifaldi-ffacb7)](https://github.com/fvldi)
[![NRP](https://img.shields.io/badge/NRP-05311840000022-feceab)](https://github.com/fvldi)
[![Lecturer](https://img.shields.io/badge/Lecturers-Mr.%20Ridho%20Rahman%20Hariadi,%20S.Kom.,%20M.Sc.-ffe0ac)](https://github.com/fvldi)

<br>

# Daftar ISi
- [I. Miscellaneous](#I-Miscellaneous)
    - [1.1. Zipped Up](#11-Zipped-Up)
    - [1.2. Censorship](#12-Censorship)
    - [1.3. Discord](#13-Discord)
    - [1.4. A First Step](#14-A-First-Step)
- [II. Web](#II-Web)
    - [2.1. Gamer W](#21-Gamer-W)
    - [2.2. Sarah Palin Fanpage](#22-Sarah-Palin-Fanpage)
    - [2.3. Login](#23-Login)
    - [2.4. Broken Button](#24-Broken-Button)
- [III. Cryptography](#III-Cryptography)
    - [3.1. Is This Crypto?](#31-Is-This-Crypto?)
    - [3.2. Titanic](#32-Titanic)
    - [3.3. Login](#23-Login)
    - [3.4. Broken Button](#24-Broken-Button)
    - [3.5. Broken Button](#24-Broken-Button)
    - [3.6. Broken Button](#24-Broken-Button)
    - [3.7. Broken Button](#24-Broken-Button)

# I. Penjelasan Singkat Aplikasi

Dovid (Donasi COVID-19) merupakan website sederhana yang digunakan untuk mendata bantuan selama terjadi pandemi saat ini. Website ini memiliki beberapa fitur berikut:

1. Bantuan memiliki jenis/kategori berupa uang tunai, bahan makanan, obat-obatan, dll.)
2. Setiap orang dapat memberikan bantuan. Dalam satu transaksi bantuan bisa jadi ada beberapa jenis bantuan yang diberikan.
3. Terdapat menu melihat rekap daftar bantuan berdasarkan kategorinya.

## 1.1. Controllers

Controller yang digunakan yaitu [**`DonasiController`**](https://github.com/fvldi/EAS_PI_022/blob/master/app/controllers/DonasiController.php). Dalam controller tersebut terdapat beberapa method:
* **`home()`**: digunakan untuk mengatur `$_SESSION` yang akan digunakan dan mengarahkan view yang digunakan jika belum mengisi dan sudah mengisi informasi donatur.
* **`rekap()`**: digunakan untuk mengatur rekapan yang akan ditampilkan. Rekapan yang ditampilkan bisa seluruh kategori atau berdasarkan kategori yang diinginkan.
* **`tambahData()`**: digunakan untuk menambahkan data pada `$_SESSION` kedalam database dan mengatur `FlashMessage` yang ditampilkan.
* **`deleteDonasi()`**: digunakan untuk menghilangkan entry `donasi` spesifik pada `$_SESSION`.
* **`destroy()`**: digunakan untuk menghilangkan data `$_SESSION`.

## 1.2. Models

Terdapat 2 model yang digunakan untuk masing-masing tabel, yaitu [**`Donasi`**](https://github.com/fvldi/EAS_PI_022/blob/master/app/models/Donasi.php) dan [**`Kategori`**](https://github.com/fvldi/EAS_PI_022/blob/master/app/models/Kategori.php).

Struktur dari tabel **`Donasi`** sebagai berikut:
* **`id`**: menyimpan id masing-masing donasi.
* **`id_transaksi`**: menyimpan id untuk masing-masing transaksi.
* **`donatur`**: menyimpan nama donatur.
* **`email_donatur`**: menyimpan alamat email donatur.
* **`id_kategori`**: menyimpan id dari kategori yang didonasikan (foreign key ke tabel **`Kategori`**).
* **`deskripsi`**: penjelasan mengenai barang yang didonasikan (misal uang, beras, masker, dll).
* **`kuantitas`**: kuantitas dari barang yang didonasikan (kalau uang dimasukkan nominal).
* **`date`**: menyimpan tanggal dan waktu transaksi.

Struktur dari tabel **`kategori`** sebagai berikut:
* **`id`**: menyimpan id kategori.
* **`nama_kategori`**: menyimpan nama kategori.

Pada model **`Donasi`** terdapat beberapa method:
* **`create()`**: digunakan memasukkan setiap data donasi tiap transaksi kedalam tabel sesuai dengan inputnya.
* **`getAll()`**: digunakan untuk mendapatkan seluruh entry pada tabel **`Donasi`** dengan mengambil `nama_kategori` pada tabel **`Kategori`**.
* **`getByCategory()`**: mirip dengan method `getAll()`, tetapi mengambil berdasarkan `id_kategori` yang diinputkan.
* **`getLatestIdTransaksi()`**: digunakan untuk mendapatkan `id_transaksi` terakhir pada tabel **`Donasi`**.

Pada model **`Kategori`** terdapat beberapa method:
* **`getById()`**: digunakan untuk mendapatkan `nama_kategori` berdasarkan `id` yang diinputkan.
* **`getAll()`**: digunakan untuk mendapatkan seluruh entry pada tabel **`Kategori`**.

## 1.3. Views

Terdapat 3 view untuk beberapa fungsionalitas. View yang di gunakan yaitu [**`index`**](https://github.com/fvldi/EAS_PI_022/blob/master/app/views/donasi/index.html), [**`donasi`**](https://github.com/fvldi/EAS_PI_022/blob/master/app/views/donasi/donasi.html), dan [**`rekap`**](https://github.com/fvldi/EAS_PI_022/blob/master/app/views/donasi/rekap.html).

* **`index`**: digunakan untuk menambahkan informasi mengenai donatur (nama donatur dan alamat email). Berikut screenshot pada view **`index`**
* **`donasi`**: digunakan untuk menambahkan data donasi yang dikirimkan oleh donatur. Berikut screenshot pada view **`donasi`**
* **`rekap`**: digunakan untuk melihat rekapan data donasi. Berikut screenshot pada view **`rekap`**

# II. Penjelasan fitur aplikasi

Pada halaman utama website Dovid, para donatur akan diberikan tampilan form field yang kemudian akan mereka isi dengan nama serta email mereka. Kemudian para donatur akan mengisi form tersebut dan meng-klik ```Submit``` untuk lanjut ke tahap berikutnya.

# ![DOVID! (DONASI COVID-19](image/01.gif)

Pada page berikutnya, para donatur dapat mendata barang donasi mereka dengan meng-klik ```Tambah Donasi```. Setelah itu mereka dapat mengisi form field yang telah disediakan, yaitu terdiri atas kategori donasi, keterangan, hingga banyak donasi. Para donatur dapat berdonasi lebih dari satu jenis. Jika dirasa sudah cukup, klik ```Kirim 🔥``` untuk memproses donasi.

# ![DOVID! (DONASI COVID-19](image/02.gif)

Setelah donasi berhasil dilakukan, maka akan muncul kotak dialog pada halaman utama Dovid. Kemudian, jika para donatur ingin melihat rekap data donasi pada website Dovid, mereka dapat meng-klik link ```Rekap data donasi 📝``` untuk kemudian diarahkan ke page rekap donasi.

# ![DOVID! (DONASI COVID-19](image/03.gif)