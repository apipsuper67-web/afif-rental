# afif-rental
Afif Rental
Aplikasi web berbasis Laravel untuk menampilkan daftar peralatan dan mencatat peminjaman peralatan berdasarkan nama kelompok serta jumlah unit yang dipinjam.
> README ini disusun berdasarkan struktur dan kode yang tersedia pada repository. Sesuaikan konfigurasi database dan deployment dengan lingkungan yang digunakan.
Fitur
Menampilkan daftar peralatan.
Menampilkan riwayat peminjaman beserta informasi peralatan.
Membuka formulir peminjaman untuk peralatan yang dipilih.
Mencatat nama kelompok dan jumlah unit yang dipinjam.
Validasi nama kelompok (wajib diisi, maksimal 100 karakter).
Validasi jumlah pinjaman (bilangan bulat, minimal 1 unit).
Menampilkan notifikasi setelah peminjaman berhasil dicatat.
Teknologi
Backend: PHP 8.3+ dan Laravel 13
Database: Database yang didukung Laravel, dikonfigurasi melalui `.env`
Frontend build: Vite
CSS: Tailwind CSS 4
Persyaratan
Pastikan perangkat sudah memiliki:
PHP 8.3 atau lebih baru
Composer
Node.js dan npm
Database, misalnya MySQL atau SQLite
Git
Instalasi
1. Clone repository
```bash
git clone https://github.com/apipsuper67-web/afif-rental.git
cd afif-rental
```
2. Install dependency PHP
```bash
composer install
```
3. Buat file environment
Linux/macOS:
```bash
cp .env.example .env
```
Windows PowerShell:
```powershell
Copy-Item .env.example .env
```
4. Atur konfigurasi aplikasi dan database
Buka file `.env`, lalu sesuaikan konfigurasi berikut dengan database lokal:
```env
APP_NAME="Afif Rental"
APP_ENV=local
APP_DEBUG=true
APP_URL=http://127.0.0.1:8000

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=afif_rental
DB_USERNAME=root
DB_PASSWORD=
```
Buat database `afif_rental` terlebih dahulu pada server database. Jika menggunakan SQLite, sesuaikan `DB_CONNECTION` dan konfigurasi database dengan kebutuhan Laravel.
5. Generate application key
```bash
php artisan key:generate
```
6. Jalankan migration
```bash
php artisan migrate
```
7. Install dependency frontend
```bash
npm install
```
8. Jalankan aplikasi
Buka dua terminal dari folder project.
Terminal pertama:
```bash
php artisan serve
```
Terminal kedua:
```bash
npm run dev
```
Buka aplikasi melalui browser:
```text
http://127.0.0.1:8000
```
Untuk membuat asset frontend production:
```bash
npm run build
```
Alur Penggunaan
Buka halaman utama untuk melihat daftar peralatan dan riwayat peminjaman.
Pilih peralatan yang ingin dipinjam.
Isi nama kelompok dan jumlah unit yang akan dipinjam.
Kirim formulir peminjaman.
Jika data valid, peminjaman disimpan dan pengguna diarahkan kembali ke halaman utama dengan notifikasi berhasil.
Route Utama
Method	URL	Keterangan
`GET`	`/`	Menampilkan daftar peralatan dan riwayat peminjaman
`GET`	`/pinjam/{equipment}`	Menampilkan formulir peminjaman peralatan
`POST`	`/pinjam/{equipment}`	Menyimpan data peminjaman
Struktur Folder
```text
afif-rental/
├── app/              # Controller, model, dan logic aplikasi
├── bootstrap/        # Bootstrap aplikasi Laravel
├── config/           # Konfigurasi aplikasi
├── database/         # Migration, factory, dan seeder
├── public/           # Entry point dan asset publik
├── resources/        # View dan asset frontend
├── routes/           # Definisi route
├── storage/          # File, cache, dan log aplikasi
├── tests/            # Automated tests
├── .env.example      # Contoh konfigurasi environment
├── composer.json     # Dependency dan script PHP
├── package.json      # Dependency dan script frontend
└── vite.config.js    # Konfigurasi Vite
```
Testing
Jalankan test suite Laravel:
```bash
php artisan test
```
Atau gunakan script Composer:
```bash
composer test
```
Catatan Pengembangan
Jangan mengunggah file `.env` atau kredensial database ke repository.
Untuk production, atur `APP_ENV=production` dan `APP_DEBUG=false`.
Pastikan database sudah dikonfigurasi dan migration telah dijalankan sebelum aplikasi digunakan.
Jalankan `npm run build` untuk menghasilkan asset frontend production.
Kontribusi
Fork repository.
Buat branch fitur atau perbaikan:
```bash
   git checkout -b feature/nama-fitur
   ```
Commit perubahan:
```bash
   git commit -m "Add: nama fitur"
   ```
Push branch dan buat Pull Request.
Repository
https://github.com/apipsuper67-web/afif-rental
