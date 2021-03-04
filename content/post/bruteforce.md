+++
author = "Dicky Setiono"
title = "Brute force dan mengatasinya"
date = "2021-03-04"
tags = [ "Cyber Security","Penetration Testing" ]
categories = [ "Cyber Security" ]
series = ["Themes Guide"] 
aliases = ["migrate-from-jekyl"]
+++

![img](https://miro.medium.com/max/700/1*4khHUbpW4rp4f9u6Jo0xtg.jpeg)

## Apa Itu Brute Force 

Serangan brute force adalah metode cracking yang populer menurut beberapa akun, serangan brute force menyumbang 5% confirmed security breaches. Serangan brute force melibatkan __"Menebak"__ nama pengguna dan sandi untuk mendapatkan akses tidak sah ke sistem. Brute force merupakan metode serangan yang sederhanadan memiliki tingkat keberhasilan yang tinggi

Beberapa penyerang menggunakan aplikasi dan skrip sebagai alat brute force. Alat-alat ini mencoba berbagai kombinasi kata sandi untuk melewati proses otentikasi. Dalam kasus lain, penyerang mencoba mengakses aplikasi web dengan mencari ID sesi yang tepat. Motivasi penyerang mungkin termasuk mencuri informasi, menginfeksi situs dengan malware, atau mengganggu layanan.

Sementara beberapa penyerang masih melakukan serangan brute force secara manual, saat ini hampir semua serangan brute force saat ini dilakukan oleh bot. Penyerang memiliki daftar kredensial yang umum digunakan, atau kredensial pengguna asli, yang diperoleh melalui __*security breaches*__ atau __*dark web*__. Bot secara sistematis menyerang situs web dan mencoba daftar kredensial ini, dan memberi tahu penyerang ketika mereka mendapatkan

## Jenis Serangan Brute Force

* Metode Sederhana : Metode yang digunakan sebelum menggunakan tools yaitu dengan menebak kata sandi kotban. Mulai dari tanggal lahir korban, keluarga korban atau temen terdekat korban

* Metode Hybrid : Metode ini dengan cara menggabungkan metode kamus dan metode sederhana. Artinya, hacker telah memiliki daftar password untuk menebak login tapi biasanya mereka juga mengombinasikan angka maupun huruf yang di anggap celah

* Metode Kamus : Cara selanjutnya dengan metode kamus biasanya hacker sudah menyiapkan sebuah file.txt yang berisi bermacam macam kata sandi dari yang pernah ia dapatkan maupun dari tools yang sudah di sediakan

* Metode Rainbow Table : Rainbow table adalah table yang dihitung sebelumnya untuk *reversing* fungsi hash kriptografi. Ini dapat digunakan untuk menebak fungsi hingga panjang tertentu yang terdiri dari sekumpulan karakter

* Metode Reverse Attack : Menggunakan kata sandi umum atau kumpulan kata sandi terhadap banyak kemungkinan nama pengguna. Menargetkan jaringan pengguna yang datanya telah diperoleh penyerang sebelumnya.

* Metode credential : menggunakan pasangan kata sandi-nama pengguna yang sebelumnya dikenal, mencobanya di beberapa situs web. Memanfaatkan fakta bahwa banyak pengguna memiliki nama pengguna dan sandi yang sama di berbagai sistem.

## Brute Force Tools
### Hydra 
Analis keamanan menggunakan alat THC-Hydra untuk mengidentifikasi kerentanan dalam sistem klien. Hydra dengan cepat menjalankan sejumlah besar kombinasi kata sandi, baik brute force sederhana atau berbasis kamus. Itu dapat menyerang lebih dari 50 protokol dan beberapa sistem operasi. Hydra adalah *open source platform*. Komunitas keamanan dan penyerang terus mengembangkan modul baru.

![img](https://www.imperva.com/learn/wp-content/uploads/sites/13/2018/01/hydra-brute-force-attack-768x315.png.webp)

### Aircrack 
Aircrack dapat digunakan di Windows, Linux, iOS, dan Android. Ini menggunakan kamus kata sandi yang banyak digunakan untuk menembus jaringan nirkabel.

### John the Ripper
berjalan pada 15 platform berbeda termasuk Unix, Windows, dan OpenVMS. Mencoba semua kemungkinan kombinasi menggunakan kamus kemungkinan kata sandi.

Dan masih banyak lagi tools untuk brute force sendiri atau kamu bisa explore sendiri

## Cara mencegah Brute Force Hacking 

Untuk melindungi privasi kamu dari brute force, terapkan penggunaan kata sandi yang kuat. Kata sandi harus:

* Jangan pernah menggunakan informasi yang dapat ditemukan online (seperti nama anggota keluarga).
* Miliki karakter sebanyak mungkin.
* Gabungkan huruf, angka, dan simbol.

![img](https://miro.medium.com/max/415/1*wwh8cMYrtIuoAuPrZBBZFw.png)

* Berbeda untuk setiap akun pengguna.
* Hindari pola umum.

Sebagai administrator sebuah organisasi/perusahaan, ada metode yang dapat Anda terapkan untuk melindungi pengguna dari peretasan kata sandi brute force:

* __Lockout policy__ : Kamu dapat mengunci akun setelah beberapa upaya login yang gagal dan kemudian membuka kuncinya sebagai administrator.
* __Progressive delays__ : Anda dapat mengunci akun untuk jangka waktu terbatas setelah upaya login yang gagal. Setiap upaya membuat penundaan lebih lama.
* __Captcha__ : alat seperti reCAPTCHA mengharuskan pengguna menyelesaikan tugas sederhana untuk masuk ke sistem. Pengguna dapat dengan mudah menyelesaikan tugas-tugas ini sementara alat brute force tidak bisa.
* __Requiring strong passwords__ : Kamu dapat memaksa pengguna untuk menentukan sandi yang panjang dan rumit. Kamu juga harus menerapkan perubahan sandi secara berkala.
* __Two-factor authentication__ : Anda dapat menggunakan beberapa faktor untuk mengautentikasi identitas dan memberikan akses ke akun.

Demikian tulisan kali ini.

Terima kasih dan semoga bermanfaat.