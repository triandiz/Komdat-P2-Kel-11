# Pagekit

## Sekilas Tentang:
Pagekit adalah aplikasi yang digunakan untuk mempermudah para penggunanya dalam membangun web baru. Pagekit sendiri memiliki beragam fitur yang bisa anda gunakan seperti membuat tampilan halaman baru untuk membuat blog dan personalisasi web. Aplikasi yang dibuat oleh @yoohotheme ini dibangun dengan teknologi modern dengan CMS modular dan ringan.

## Instalasi
Proses instalasi Pagekit cepat dan mudah serta hanya membutuhkan waktu beberapa menit.

- Langkah 1: Unduh dan buka Penginstal
- Langkah 2: Bahasa
- Langkah 3: Database
- Langkah 4: Penyiapan situs

## Konfigurasi
Konfigurasi dan membuat tabel secara manual, dapat dilakukan dengan peintah perintah berikut (tidak disarankn)

Salin ```resources/views/env.blade.php``` ke ```.env``` di direktori root dan perbarui nilainya dengan benar. Jangan lupa untuk memakai tanda kurung kurawal di ```.env``` baru yang dimiliki.

Anda dapat menjalankan perintah ```artisan``` untuk membuat tabel yang diperlukan.

```
php artisan migrate --force
php artisan geoip:update
```
