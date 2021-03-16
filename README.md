# Polr

## Sekilas Tentang:
Polr adalah aplikasi web pemendek link atau tautan yang dapat di hosting dengan API yang kuat. Aplikasi ini berguna untuk mengedit link url agar link url tersebut dapat menjadi lebih pendek dan memudahkan para pengakses untuk membukanya. Porl sangat mudah digunakan dan mempunyai nuansa tema yang modern.

## Instalasi
Berikut yang diperlukan server anda untuk menjalankan Porl.
- Apache, nginx, IIS, or lighttpd (Apache preferred)
- PHP >= 5.5.9
- MariaDB or MySQL >= 5.5, SQLite alternatively
- composer
- PHP requirements:
   - OpenSSL PHP Extension
   - PDO PHP Extension
   - PDO MySQL Driver (php5-mysql on Debian & Ubuntu, php5x-pdo_mysql on FreeBSD)
   - Mbstring PHP Extension
   - Tokenizer PHP Extension
   - JSON PHP Extension
   - PHP curl extension

## Konfigurasi
Konfigurasi dan membuat tabel secara manual, dapat dilakukan dengan peintah perintah berikut (tidak disarankn)

Salin resources/views/env.blade.php ke .env di direktori root dan perbarui nilainya dengan benar. Jangan lupa untuk memakai tanda kurung kurawal di .env baru yang dimiliki.

Anda dapat menjalankan perintah artisan untuk membuat tabel yang diperlukan.

<table>
    <tbody>
        <tr>
            php artisan migrate --force
            php artisan geoip:update
        </tr>
