# Pagekit

## Sekilas Tentang:
Pagekit adalah aplikasi yang digunakan untuk mempermudah para penggunanya dalam membangun web baru. Pagekit sendiri memiliki beragam fitur yang bisa anda gunakan seperti membuat tampilan halaman baru untuk membuat blog dan personalisasi web. Aplikasi yang dibuat oleh @yoohotheme ini dibangun dengan teknologi modern dengan CMS modular dan ringan.

## Instalasi
Proses instalasi Pagekit cepat dan mudah serta hanya membutuhkan waktu beberapa menit.

- Langkah 1: Unduh dan buka Penginstal
  
  Pertama-tama, Anda perlu mengunduh paket Pagekit terbaru dan mengekstrak isinya ke server web Anda, anda bisa mengekstraknya ke direktori root web atau ke subfolder, contoh ```/pagekit```.
  
  NOTE: jika anda mengekstrak paket secara lokal sebelum mengunggah pastikan bahwa sertakan file ```.htaccess``` yang tersembunyi.
  
  Lalu open browser yang tadi sudah di ekstrak, lalu itulah tampilan pertama dari penginstalan web dan anda harus melihatnya.

- Langkah 2: Bahasa

  Selanjutnya anda harus memilih bahasa utama untuk situs tersebut. Ini akan menjadi bahasa default yang digunakan di panel admin dan frontend. Namun bahasa ini dapat diubah kapan saja.

- Langkah 3: Database

  Pada langkah ini anda diharuskn untuk menyambungkannya ke database. Secara default, Pagekit menggunakan SQLite untuk menyimpan data situs anda.  Di sini Anda perlu mengisi kolom Nama Database dan Awalan Tabel. Awalan default tabel adalah ```pk_```.
  
  Sebagai alternatif, Anda juga dapat memilih untuk menggunakan MySQL. Dalam hal ini, detail berikut perlu dimasukkan.
  
  <table>
    <tbody>
        <tr>
            <td>BIDANG</td>
            <td>DESKRIPSI</td>
        </tr>
        <tr>
            <td>Driver</td>
            <td colspan=3 style="text-align:center">Maukkan database driver. Bergantung pada database yang digunakan</td>
        </tr>
        <tr>
            <td>Hostname</td>
            <td colspan=3 style="text-align:center">Masukkan host name dari database server kalian. Jika data base dan web server berada pada mesin yang sama, berarti berada pada localhost atau 127.0.0.1 </td>
        </tr>
        <tr>
            <td>User</td>
            <td colspan=3 style="text-align:center">Masukkan nama pengguna MySQL yang memiliki akses ke database</td>
        </tr>
        <tr>
            <td>Password</td>
            <td colspan=3 style="text-align:center">Masukkan password Mysql</td>
        </tr>
      <tr>
            <td>Database Name</td>
            <td colspan=3 style="text-align:center">Masukkan nama database</td>
        </tr>
      <tr>
            <td>Table Prefix</td>
            <td colspan=3 style="text-align:center">Anda dapat mengubah prefiks yang digunakan untuk tabel database. Awalan default adalah pk_</td>
        </tr>
      </tbody>
    </table>

  CATATAN Pagekit akan mencoba membuat database selama instalasi. Anda juga dapat melakukan ini sendiri menggunakan alat seperti phpMyAdmin. Jangan ragu untuk menggunakan database yang sudah ada. Pagekit mengawali tabelnya untuk menghindari konflik.
  
- Langkah 4: Penyiapan situs

Setelah memasukkan judul situs Anda, Anda perlu membuat akun pengguna untuk Pagekit. Pengguna ini akan memiliki akses admin dan dapat masuk ke panel kontrol Pagekit, setelah penginstalan selesai.

 <table>
    <tbody>
        <tr>
            <td>BIDANG</td>
            <td>DESKRIPSI</td>
        </tr>
        <tr>
            <td>Site Title</td>
            <td colspan=3 style="text-align:center">Judul site tersebut</td>
        </tr>
        <tr>
            <td>Username</td>
            <td colspan=3 style="text-align:center">Masukkan username admin </td>
        </tr>
        <tr>
            <td>Password</td>
            <td colspan=3 style="text-align:center">Masukkan password admin</td>
        </tr>
        <tr>
            <td>Email</td>
            <td colspan=3 style="text-align:center">Masukkan email admin</td>
        </tr>
      </tbody>
    </table>
    
Setelah penginstalan berhasil, Anda akan diarahkan ke layar login. Anda dapat masuk ke panel admin Pagekit dengan akun yang Anda buat. Jika Anda ingin masuk ke area admin di masa mendatang, Anda selalu dapat mencapai layar login dengan menambahkan ```/ admin``` ke URL situs Anda.

## Konfigurasi
Untuk file konfigurasi dari Pagekit sendiri file konfigurasi sudah akan terbuat saat anda menginstall. Jika anda ingin mengubah konfigurasi dengan pengaturan manual, artikel ini menjelaskan sintaks dan konten file.

Biasanya, Anda tidak perlu mengutak-atik file konfigurasi ```config.php``` setelah dibuat oleh penginstal. Cara normal untuk mengubah konfigurasi adalah melalui ```System> Settings``` di panel admin Pagekit.

Terkadang mengedit file ini secara manual masih diperlukan dan bermanfaat, contohnya pada saat memecahkan masalah penginstalan yang rusak atau saat memindahkan penginstalan Pagekit yang ada ke server baru. Dalam daftar kode berikut Anda melihat contoh konfigurasi dengan pengaturan yang paling umum.

Biasanya Anda hanya memiliki satu koneksi database. Contoh tersebut menyertakan kedua contoh untuk menunjukkan cara kerja konfigurasi untuk driver database yang berbeda. Hanya koneksi ```default``` yang akan digunakan oleh Pagekit (dalam contoh ini digunakan ```sqlite```).

'database' => [
  'default' => 'sqlite',     // default database connection
  
  'database' => [
  'default' => 'sqlite',     // default database connection
  'connections' => [         // array of database connections
    'sqlite' => [            // database driver name, here: sqlite
      'prefix' => 'pk_',     // prefix in front of every table
    ],
    'mysql' => [             // database driver name, here: mysql
      'host' => 'localhost', // server host name
      'user' => 'user',      // server user name
      'password' => 'pass',  // server user password
      'dbname' => 'pagekit', // database name
      'prefix' => 'pk_'      // prefix in front of every table
    ],
  ]
],
'system' => [
  'secret' => 'secret'       // a secret string generated during installation
],
'system/cache' => [
  'caches' => [
    'cache' => [
      'storage' => 'auto'    // the cache method to be used, if enabled
    ]
  ],
  'nocache' => false         // the cache state - disable entirely by setting to true
],
'system/finder' => [
  'storage' => '/storage'    // relative path to a folder used for uploads, cache etc.
],
'application' => [
  'debug' => false           // debug mode state, enable while developing to get debug output
],
'debug' => [
  'enabled' => false         // debug toolbar state, enable to get information, about requests, routes etc.
]
