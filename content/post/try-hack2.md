+++
author = "Dicky S"
title = "Try Hack Me Nmap Challenge Part 2"
date = "2021-03-22"
tags = [
    "CTF", "Learn"
]
categories = [ "Challenge" ]
+++

![img](https://miro.medium.com/max/2400/1*NqeovuV6RWG0-iK5yZYv6g.png)

Oke kita lanjutkan di part 2 untuk yang belom membaca di [Part 1](https://dickydiko.space/post/try-hack/). Dipart 1 saya menjawab soal dari task 2 sampai task 7. Jadi mari kita lanjutkan the next roomnya 

#### Task 8 NUL, FIN and Xmas
1. Which of the three shown scan types uses the URG flag?

```
Xmas
```

2. Why are NULL, FIN and Xmas scans generally used?

```
Firewall Evasion
```
3. Which common OS may respond to a NULL, FIN or Xmas scan with a RST for every port?

```
Microsoft Windows
```
#### Task 9 ICMP Network Scanning

1. How would you perform a ping sweep on the 172.16.x.x network (Netmask: 255.255.0.0) using Nmap? (CIDR notation)

```
nmap -sn 172.16.0.0/16
```
#### Task 10 Overview

1. What language are NSE scripts written in?

```
Lua
```
2. Which category of scripts would be a very bad idea to run in a production environment?

```
Intrusive
```

#### Task 11 Working With The NSE

1. What optional argument can the ftp-anon.nse script take?

![img](https://miro.medium.com/max/700/1*md55igslyVVvNe6kd799oQ.png)

Di DOC ini kamu dapat melihatnya bahwa DOC mengambil *arg call maxlist*

```
maxlist
```
#### Task 12 Searching for Scripts

1. What is the filename of the script which determines the underlying OS of the SMB server?

![img](https://miro.medium.com/max/700/1*3-273oWtLc8rEwQHjGu9Sg.png)

Jika kamu menjalankan perintah di atas, kamu akan mendapatkan daftar seperti ini dan menemukan satu sebuah file OS 

```
smb-os-discovery.nse
```
2. Read through this script. What does it depend on?

![img](https://miro.medium.com/max/524/1*Vt4zrVIa1KTcqOnT1nwKSg.png)

Soal ini adalah bagaimana kamu dapat melihat source code dari *smb-os-discovery.nse*. Pertama-tama kamu harus cari smb-os-discovery.nse dan gunakan cat <file_loation>

```
smb-brute
```
#### Task 13 Firewall Evasion

1. Which simple (and frequently relied upon) protocol is often blocked, requiring the use of the -Pn switch?

```
ICMP
```
2. [Research] Which Nmap switch allows you to append an arbitrary length of random data to the end of packets?

```
--data-length
```

Untuk menemukan kamu dapat mengetik *man nmap* dan pergi ke tab *Firewall Evasion* kamu dapat melihatnya sendiri

#### Task 14 Practical

1. Does the target (MACHINE_IP)respond to ICMP (ping) requests (Y/N)?

```
N
```
2. Perform an Xmas scan on the first 999 ports of the target -- how many ports are shown to be open or filtered?

![img](https://miro.medium.com/max/700/1*8img4xqdMzBTgfR0LZgdog.png)

```
999
```
3. There is a reason given for this -- what is it?

__Note:__ The answer will be in your scan results. Think carefully about which switches to use -- and read the hint before asking for help!

```
No Response
```

4. Perform a TCP SYN scan on the first 5000 ports of the target -- how many ports are shown to be open?

![img](https://miro.medium.com/max/700/1*EAxzIB0TOqFjZciqwNa_Mw.png)

kamu dapat melihat ada berapa ports yang terbuka

```
5
```
5. Deploy the ftp-anon script against the box. Can Nmap login successfully to the FTP server on port 21? (Y/N)

```
Y
```

![img](https://miro.medium.com/max/700/1*unWQSnObxjCMiERqUbnFEw.png)

ini adalah bagaimana kamu harus menggunakan skrip di Nmap sehingga kamu dapat melihat login anonim diizinkan sekarang mari kita coba login

![img](https://miro.medium.com/max/584/1*EYJICKN-MluxvUzYd-ltkA.png)

Ini adalah bagaimana kamu harus masuk ke sesi FTP

jadi saya harap kamu belajar bagaimana melakukan tugas ini, sampai jumpa di blog lain 😉😉😉