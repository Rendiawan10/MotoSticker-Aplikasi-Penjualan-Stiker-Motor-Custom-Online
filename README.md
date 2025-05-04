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
| id          | INT(PK)                   | Primary Key    |
| name        | VARCHAR(100)              | Nama pengguna  |
| email       | VARCHAR(100)              | Email unik     |
| password    | VARCHAR(255)              | Password       |
| role        | ENUM('admin', 'customer') | Peran pengguna |
| created\_at | TIMESTAMP                 | Waktu dibuat   |
| updated\_at | TIMESTAMP                 | Waktu diubah   |


### 2. Tabel ```{Products}```
| Field       | Tipe Data    | Keterangan         |
| ----------- | ------------ | ------------------ |
| id          | INT(PK)      | Primary Key        |
| name        | VARCHAR(100) | Nama stiker        |
| description | TEXT         | Deskripsi          |
| price       | DOUBLE       | Harga              |
| image\_url  | VARCHAR(255) | Link gambar produk |
| created\_at | TIMESTAMP    | Waktu dibuat       |
| updated\_at | TIMESTAMP    | Waktu diubah       |


### 3. Tabel ```{Carts}```
| Field       | Tipe Data | Keterangan              |
| ----------- | --------- | ----------------------- |
| id          | INT(PK)   | Primary Key             |
| user\_id    | INT(FK)   | Relasi ke `users.id`    |
| product\_id | INT(FK)   | Relasi ke `products.id` |
| quantity    | INT       | Jumlah produk           |
| created\_at | TIMESTAMP | Waktu dibuat            |


### 4. Tabel ```{Orders}```
| Field        | Tipe Data                                         | Keterangan           |
| ------------ | ------------------------------------------------- | -------------------- |
| id           | INT(PK)                                           | Primary Key          |
| user\_id     | INT(FK)                                           | Relasi ke `users.id` |
| total\_price | DOUBLE                                            | Total harga pesanan  |
| status       | ENUM('pending', 'diproses', 'dikirim', 'selesai') | Status pesanan       |
| created\_at  | TIMESTAMP                                         | Waktu dibuat         |
| updated\_at  | TIMESTAMP                                         | Waktu diubah         |


### 5. Tabel ```{order_items}```
| Field       | Tipe Data | Keterangan              |
| ----------- | --------- | ----------------------- |
| id          | INT(PK)   | Primary Key             |
| order\_id   | INT(FK)   | Relasi ke `orders.id`   |
| product\_id | INT(FK)   | Relasi ke `products.id` |
| quantity    | INT       | Jumlah item             |


### 6. Tabel ```{custom_designs}```
| Field       | Tipe Data    | Keterangan            |
| ----------- | ------------ | --------------------- |
| id          | INT(PK)      | Primary Key           |
| user\_id    | INT(FK)      | Relasi ke `users.id`  |
| order\_id   | INT(FK)      | Relasi ke `orders.id` |
| image\_url  | VARCHAR(255) | URL desain custom     |
| notes       | TEXT         | Catatan pengguna      |
| created\_at | TIMESTAMP    | Waktu dibuat          |




---
## Jenis relasi dan tabel yang berelasi
| Tabel Asal    | Tabel Tujuan              | Relasi      | Keterangan                              |
| ------------- | ------------------------- | ----------- | --------------------------------------- |
| `users.id`    | `orders.user_id`          | One to Many | 1 user bisa memiliki banyak order       |
| `users.id`    | `custom_designs.user_id`  | One to Many | 1 user bisa kirim banyak desain         |
| `orders.id`   | `order_items.order_id`    | One to Many | 1 order memiliki banyak item            |
| `products.id` | `order_items.product_id`  | One to Many | 1 produk bisa masuk ke banyak item      |
| `users.id`    | `carts.user_id`           | One to Many | 1 user bisa punya banyak keranjang      |
| `products.id` | `carts.product_id`        | One to Many | 1 produk bisa masuk ke banyak keranjang |
| `orders.id`   | `custom_designs.order_id` | One to One  | 1 order hanya punya 1 desain custom     |

