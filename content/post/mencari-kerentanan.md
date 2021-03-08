+++
author = "Hugo Authors"
title = "Mencari Kerentanan Web Server Memakai Nikto"
date = "2021-03-08"
description = "Guide to emoji usage in Hugo"
tags = [
    "exploit",
]
+++

## Pengertian Nikto Dan Perkembangannya
Di artikel ini saya akan membahas __cara mencari kerentanan di web server menggunakan nikto__. Tapi sebelum bermain mungkin sedikit saya jelaskan apa nikto ? Nikto sendiri adalah sebuah scanner web berbasis open-source  yang melakukan tes komprehensif terhadap server web untuk beberapa item. kamu dapat menggunakan Nikto dengan server web apa pun seperti Apache, Nginx, IHS, OHS, Litespeed, dan sebagainya. Nikto dapat memeriksa item konfigurasi server seperti keberadaan beberapa file index, opsi server HTTP, dan akan mencoba mengidentifikasi server web dan perangkat lunak yang diinstal. Item dan plugin yang dipindai oleh Nikto sering diperbarui dan dapat diperbarui secara otomatis.

Nikto pertama kali dikembangkan oleh Chris Sullo, tetapi sekarang berada di bawah naungan David Lodge, dan organisasi keamanan siber lainnya juga terlibat. Alat ini dapat dengan mudah diinstal pada sistem Unix yang mampu menjalankan Perl, karena alat ini didasarkan pada bahasa Perl.

Alat ini banyak digunakan oleh pentester dan peretas untuk menjelajahi banyak kerentanan. Ini mengeksplorasi jenis kerentanan berikut :

* File dan Program yang tidak aman
* Program dan Server yang sudah tidak layak pakai / perlu update
* Kesalahan Konfigurasi Server
* Dan masih banyak lagi

itu mencari hampir semua jenis file yang dapat dianggap berbahaya ke server web kamu. Ini juga dapat digunakan untuk menangkap dan mencetak cookie.

## Install Nikto 
Instalasi Nikto cukup mudah di semua sistem berbasis Unix, sudah diinstal sebelumnya di Kali Linux, dalam beberapa kasus jika tidak ada di bagian Analisis Kerentanan, maka kamu dapat menginstalnya secara manual.

Untuk menginstal Nikto, kamu cukup mendapatkannya dari sumber resmi [GitHub Nikto](https://github.com/sullo/nikto). kamu hanya perlu menjalankan perintah berikut untuk menginstal Nikto.

```
apt-install nikto
```
![img](https://www.ceos3c.com/wp-content/uploads/2019/11/word-image.png?ezimgfmt=ng:webp/ngcb43)

### Install Nikto Using Github
Pertama-tama, kamu harus mengunduh Nikto dari tautan [GitHub](https://github.com/sullo/nikto) mereka dengan mengetikkan perintah di terminal Ubuntu. Gunakan perintah berikut untuk melakukannya :
```
wget https://github.com/sullo/nikto/archive/master.zip
```
![img](https://www.ceos3c.com/wp-content/uploads/2019/11/word-image-1.png?ezimgfmt=ng:webp/ngcb43)

Setelah kamu meng extract file dengan menggunakan pengelola arsip apa pun, jalankan perintah berikut untuk melanjutkan.

```
unzip master.zip
```

![img](https://www.ceos3c.com/wp-content/uploads/2019/11/word-image-2.png?ezimgfmt=ng:webp/ngcb43)

```
cd nikto-master/program
```

```
perl nikto.pl
```
![img](https://www.ceos3c.com/wp-content/uploads/2019/11/word-image-3.png?ezimgfmt=ng:webp/ngcb43)

Setelah menjalankan perintah ini, Nikto kamu akan berhasil diinstal pada sistem Ubuntu kamu, dan kamu akan mendapatkan keluaran yang dihasilkan oleh alat Nikto.

## Cara Menggunakan Nikto

Setelah kamu menginstal Nikto dengan benar dan berfungsi dengan baik, sekarang saatnya untuk mengambil langkah pertama kamu menuju penggunaan Nikto. Untuk memulai dengan Nikto, gunakan perintah berikut, dan lihat saja opsi yang digunakan dalam Nikto.

```
nikto -Help
```

![img](https://www.ceos3c.com/wp-content/uploads/2019/11/word-image-4-768x571.png?ezimgfmt=ng:webp/ngcb43)

kalian bisa explore sendiri untuk perintah dalam menggunakan nikto

## Basic Scan

Melakukan Basic Scan melalui Nikto cukup mudah. Cukup masukkan URL atau alamat IP situs web yang ingin kamu pindai. Mari kita gunakan [testphp.vulnweb.com](http://testphp.vulnweb.com/) sebagai contoh. Sekarang untuk memindai situs web, kamu perlu menggunakan sintaks berikut:

```
nikto -h <server-address> -p <port>
```

Dalam hal ini, ada dua opsi di mana:

-h menentukan alamat IP situs web atau server yang ingin kamu pindai.

-p menentukan port, sebagian besar 80 secara default, tetapi beberapa server mungkin menggunakan port yang berbeda.

kamu harus ingat bahwa sekelompok situs web mungkin dihosting di server yang sama, yang berarti bahwa semua situs web akan memiliki alamat IP yang sama. Jadi, kamu harus menggunakan nama host untuk menentukan target yang ingin kamu pindai. Akan ada port berbeda untuk situs web yang menggunakan SSL untuk keamanannya.

Dalam kasus [testphp.vulnweb.com](http://testphp.vulnweb.com/), kita cukup menggunakan perintah berikut untuk melakukan pemindaian dasar dengan opsi dasar.

```
nikto -h testphp.vulnweb.com -p 80
```
![img](https://www.ceos3c.com/wp-content/uploads/2019/11/word-image-5.png?ezimgfmt=ng:webp/ngcb43)

Sekarang, jika situs web diamankan dengan SSL, maka kamu mungkin akan melihat informasi mengenai SSL, dan untuk situs web yang diamankan ini, Nikto akan menjalankan pemindaian kerentanan lain untuk menemukan kemungkinan cacat yang ada dalam sistem. Proses pemindaian tidak selalu begitu cepat, dan jelas akan membutuhkan waktu untuk menyelesaikannya karena Nikto memindainya secara mendalam, dan untuk pemindaian yang dalam, perlu beberapa saat untuk menyelesaikannya.

Setelah Nikto menyelesaikan pemindaian, kamu sekarang akan melihat daftar kerentanan yang ada di situs web dan server web. Beberapa kerentanan hanya bersifat informasional, sementara yang lain mungkin sangat kritis.

Nikto memberi tahu kita tentang banyak kerentanan, masalah, dan informasi, termasuk:

1. Web-server details
2. Installation files for Apache server
3. Access to backend files with the help of Directory indexing
4. Number of entries in a text file

Biasanya para peretas menggunakan nikto untuk memindai kerentanan situs web dan menganalis keamanan informasi kemudian dia akan melaporkan kepada pemilik situs web untuk segera di perbaiki ini biasa yang di sebut *whitehat*
