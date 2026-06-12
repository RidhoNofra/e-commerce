# 🍉 Toko Ariri - Sistem Informasi Toko Buah

![Banner Project](assets/images/1775012132_BUAH_ALPUKAT_MENTEGA_jpg.webp)

## 📌 Deskripsi Project

**Toko Ariri** adalah aplikasi web sederhana untuk mengelola katalog dan transaksi toko buah berbasis PHP native dan MySQL. Aplikasi ini menyediakan fitur autentikasi pengguna, katalog buah, pembelian melalui keranjang, serta halaman admin untuk mengelola data produk.

Project ini dibuat sebagai media pembelajaran dan implementasi konsep pengembangan aplikasi web full-stack, terutama penerapan CRUD, database relasional, autentikasi, validasi form, dan desain web responsif.

## 🎯 Tujuan Pembelajaran / Produksi

- Memahami alur kerja aplikasi web dari frontend hingga backend.
- Menerapkan konsep CRUD (Create, Read, Update, Delete) pada data produk.
- Menghubungkan aplikasi PHP dengan database MySQL.
- Membuat sistem login dengan pembagian hak akses user dan admin.
- Menerapkan struktur folder aplikasi yang lebih terorganisir.

---

# 🛠️ Teknologi yang Digunakan

## Backend
- PHP Native 8.x
- MySQLi untuk koneksi database

## Frontend
- HTML5
- CSS3
- Responsive layout menggunakan CSS Media Query

## Database
- MySQL 5.7 / MariaDB
- Database: `toko_buah`

## Tools
- XAMPP (Apache + MySQL)
- phpMyAdmin
- Visual Studio Code
- Git & GitHub

---

# 🚀 Instalasi dan Konfigurasi

## 1. Clone Repository

```bash
git clone https://github.com/username/toko-buah.git
```

Masuk ke folder project:

```bash
cd toko-buah
```

## 2. Jalankan Server Lokal

Gunakan XAMPP:

- Aktifkan Apache
- Aktifkan MySQL
- Letakkan folder project pada:

```
htdocs/toko-buah
```

## 3. Membuat Database

1. Buka phpMyAdmin.
2. Pilih menu Import.
3. Masukkan file:

```
database/toko_buah.sql
```

Database akan otomatis membuat:

- tabel users
- tabel buah
- tabel keranjang

## 4. Konfigurasi Database

Edit file:

```
config/koneksi.php
```

Sesuaikan:

```php
$host = "localhost";
$user = "root";
$pass = "";
$db   = "toko_buah";
```

## 5. Menjalankan Aplikasi

Buka browser:

```
http://localhost/toko-buah
```

---

# 📸 Dokumentasi Tampilan Aplikasi

> Letakkan screenshot hasil running aplikasi pada folder `docs/screenshots/`.

## Halaman Login

![Login Screenshot](docs/screenshots/login.png)

Fitur:
- Validasi username dan password.
- Sistem session login.
- Pembagian akses admin dan user.

---

## Katalog Buah

![Katalog Screenshot](docs/screenshots/katalog.png)

Fitur:
- Menampilkan daftar buah dari database.
- Pencarian produk.
- Menampilkan gambar, harga, stok, dan informasi buah.

---

## Halaman Admin CRUD

![Admin Screenshot](docs/screenshots/admin-crud.png)

Fitur:
- Tambah data buah.
- Melihat data buah.
- Mengubah data buah.
- Menghapus data buah.
- Upload gambar produk.

---

# 🔄 Mengapa CRUD Penting Dalam Aplikasi Web?

CRUD merupakan konsep dasar dalam hampir semua aplikasi berbasis data.

- **Create** memungkinkan pengguna/admin menambahkan data baru.
- **Read** memungkinkan sistem menampilkan informasi yang tersimpan.
- **Update** memungkinkan perubahan data tanpa membuat ulang data.
- **Delete** memungkinkan penghapusan data yang sudah tidak diperlukan.

Pada aplikasi toko buah, CRUD sangat penting karena data produk selalu berubah. Admin harus dapat menambahkan buah baru, memperbarui harga atau stok, melihat katalog, dan menghapus produk yang sudah tidak tersedia.

Tanpa CRUD, aplikasi hanya dapat menampilkan data statis dan sulit digunakan untuk kebutuhan bisnis nyata.

---

# ✅ Pemetaan Rubrik Penilaian

| Rubrik | Implementasi |
|---|---|
| HTML Semantik | Menggunakan struktur HTML seperti `header`, `nav`, `main`, `table`, `form`, dan elemen yang sesuai |
| Validasi Form | Input menggunakan pengecekan data sebelum diproses |
| Responsivitas | CSS menggunakan layout fleksibel agar dapat digunakan pada layar berbeda |
| CRUD | Admin dapat melakukan Create, Read, Update, Delete data buah |
| Authentication | Sistem login menggunakan session dengan role admin/user |
| Database | MySQL dengan relasi tabel users, buah, dan keranjang |
| Upload File | Admin dapat mengunggah gambar buah |

---

# 📂 Struktur Direktori

```
toko-buah/
│
├── admin/
│   ├── kelola_buah.php
│   └── pesanan.php
│
├── auth/
│   ├── login.php
│   └── logout.php
│
├── config/
│   └── koneksi.php
│
├── database/
│   └── toko_buah.sql
│
├── includes/
│   ├── navbar.php
│   └── helper_gambar.php
│
├── pages/
│   ├── katalog.php
│   ├── beli.php
│   └── harga.php
│
└── assets/
    ├── css/
    └── images/
```

---

# 🔁 Alur Data Aplikasi

```
User
 |
 | Request melalui browser
 ↓
PHP Page
 |
 | Memanggil
 ↓
Controller Logic
 |
 | Query Database
 ↓
MySQL
 |
 | Mengembalikan data
 ↓
HTML View
 |
 ↓
Tampilan pengguna
```

Contoh alur katalog:

```
User membuka katalog
        ↓
katalog.php menerima request
        ↓
Mengambil data buah dari MySQL
        ↓
Data diproses PHP
        ↓
Ditampilkan dalam bentuk kartu produk
```

---

# ⚠️ Known Issues

Beberapa hal yang masih dapat dikembangkan:

- Password masih menggunakan penyimpanan sederhana dan belum menggunakan hashing.
- Validasi keamanan input masih dapat diperkuat menggunakan prepared statement.
- Tampilan frontend masih sederhana.
- Belum terdapat sistem pembayaran online.
- Belum ada notifikasi otomatis ketika stok habis.

---

# 🔮 Rencana Pengembangan Selanjutnya

- Implementasi password hashing menggunakan `password_hash()`.
- Menggunakan framework seperti Laravel untuk struktur MVC.
- Menambahkan dashboard statistik admin.
- Menambahkan fitur pembayaran.
- Menambahkan riwayat transaksi pengguna.

---

# 📝 Pengujian CRUD

Checklist pengujian:

✅ Create: Admin berhasil menambahkan produk baru.  
✅ Read: Produk tampil pada katalog.  
✅ Update: Data produk dapat diedit dengan data sebelumnya muncul kembali.  
✅ Delete: Produk dapat dihapus dengan konfirmasi.  
✅ Error Handling: Sistem memberikan pesan ketika data tidak valid.

---

# 👨‍💻 Repository Maintenance

Standar yang diterapkan:

- Tidak menyimpan credential database asli.
- Commit menggunakan pesan yang jelas.
- Struktur folder konsisten.
- File sensitif tidak dimasukkan ke repository.

