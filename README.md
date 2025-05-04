# <p align="center" style="margin-bottom: 0px;">MotoSticker</p>
## <p align="center" style="margin-top: 0;">APLIKASI PENJUALAN STIKER MOTOR CUSTOM ONLINE</p>

<p align="center">
  <img src="LOGO-UNSULBAR.png" width="300" alt="Deskripsi gambar" />
</p>

### <p align="center">RENDIAWAN</p>
### <p align="center">D0223045</p></br>
### <p align="center">Framework Web Based</p>
### <p align="center">2025</p>

---
## Role dan Fitur
### 1. Admin
| Fitur                 | Deskripsi                               |
| --------------------- | --------------------------------------- |
| Kelola Produk         | CRUD data stiker motor                  |
| Kelola Pengguna       | Lihat dan hapus user                    |
| Kelola Pesanan        | Pantau dan ubah status pesanan          |
| Lihat Desain Custom   | Akses file desain dari customer         |
| Kelola Status Pesanan | Ubah status: diproses, dikirim, selesai |


### 2. Customer / Pengguna
| Fitur               | Deskripsi                 |
| ------------------- | ------------------------- |
| Registrasi & Login  | Akses sistem              |
| Lihat Produk        | Jelajahi katalog stiker   |
| Tambah ke Keranjang | Simpan produk sementara   |
| Upload Desain       | Unggah file desain custom |
| Checkout            | Kirim pesanan             |
| Lacak Pesanan       | Cek status pesanan        |
| Edit Profil         | Ubah info akun            |


### 3. Guest / Pengunjung
| Fitur          | Deskripsi             |
| -------------- | --------------------- |
| Lihat Produk   | Jelajahi semua produk |
| Detail Produk  | Lihat detail & harga  |
| Login / Daftar | Akses fitur lainnya   |


---
## Tabel-tabel database beserta field dan tipe datanya

### 1. Tabel ```{users}```
| Field       | Tipe Data                 | Keterangan     |
| ----------- | ------------------------- | -------------- |
| id          | INT (PK)                  | Primary Key    |
| name        | VARCHAR(100)              | Nama pengguna  |
| email       | VARCHAR(100)              | Email unik     |
| password    | VARCHAR(255)              | Password       |
| role        | ENUM('admin', 'customer') | Peran pengguna |
| created\_at | TIMESTAMP                 | Waktu dibuat   |
| updated\_at | TIMESTAMP                 | Waktu diubah   |


### 2. Tabel ```{products}```
| Field       | Tipe Data    | Keterangan    |
| ----------- | ------------ | ------------- |
| id          | INT (PK)     | Primary Key   |
| name        | VARCHAR(100) | Nama stiker   |
| price       | DOUBLE       | Harga         |
| image\_url  | VARCHAR(255) | Gambar produk |
| created\_at | TIMESTAMP    | Waktu dibuat  |
| updated\_at | TIMESTAMP    | Waktu diubah  |


### 3. Tabel ```{order}```
| Field        | Tipe Data                                      | Keterangan                        |
| ------------ | ---------------------------------------------- | --------------------------------- |
| id           | INT (PK)                                       | Primary Key                       |
| user\_id     | INT (FK)                                       | Relasi ke `users.id`              |
| product\_id  | INT (FK)                                       | Relasi ke `products.id`           |
| quantity     | INT                                            | Jumlah item yang dibeli           |
| total\_price | DOUBLE                                         | Total harga (qty x price)         |
| custom\_url  | VARCHAR(255)                                   | URL file desain custom (opsional) |
| notes        | TEXT                                           | Catatan pembeli                   |
| status       | ENUM('pending','diproses','dikirim','selesai') | Status pesanan                    |
| created\_at  | TIMESTAMP                                      | Waktu dibuat                      |
| updated\_at  | TIMESTAMP                                      | Waktu diubah                      |


---
## Jenis relasi dan tabel yang berelasi
| Tabel Asal  | Tabel Tujuan       | Relasi      | Keterangan                          |
| ----------- | ------------------ | ----------- | ----------------------------------- |
| users.id    | orders.user\_id    | One to Many | 1 user bisa memiliki banyak pesanan |
| products.id | orders.product\_id | One to Many | 1 produk bisa dipesan berkali-kali  |
