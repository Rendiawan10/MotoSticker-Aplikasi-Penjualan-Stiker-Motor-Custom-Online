<<<<<<< HEAD
<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the [Laravel Partners program](https://partners.laravel.com).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[DevSquad](https://devsquad.com/hire-laravel-developers)**
- **[Redberry](https://redberry.international/laravel-development/)**
- **[Active Logic](https://activelogic.com)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
=======
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
| name        | STRING                    | Nama pengguna  |
| email       | STRING                    | Email unik     |
| password    | STRING                    | Password       |
| role        | ENUM('admin', 'customer') | Peran pengguna |
| created\_at | TIMESTAMP                 | Waktu dibuat   |
| updated\_at | TIMESTAMP                 | Waktu diubah   |


### 2. Tabel ```{Products}```
| Field       | Tipe Data    | Keterangan         |
| ----------- | ------------ | ------------------ |
| id          | INT(PK)      | Primary Key        |
| name        | STRING       | Nama stiker        |
| description | TEXT         | Deskripsi          |
| price       | DOUBLE       | Harga              |
| image\_url  | STRING       | Link gambar produk |
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
| image\_url  | STRING       | URL desain custom     |
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

>>>>>>> 2f5034a934f1791bc0a7b483b04ea5afdf93218d
