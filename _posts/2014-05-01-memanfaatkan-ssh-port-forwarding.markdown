---
layout: post
title:  "Memanfaatkan SSH Port Forwarding"
date:   2014-05-01 16:54:43
categories: ssh
---
[SSH (secure shell)][ssh] bukan hanya digunakan untuk melakukan remote shell saja, tapi kita bisa manfaatkan sebagai port forwarding maupun sebagai proxy.

misalkan kita saat mengembangkan sebuah aplikasi, kita perlu mengakses sebuah resources dari suatu server, namun server tersebut hanya bisa diakses oleh satu IP saja, bagaimana caranya kita akses resource tersebut. Saya beri contoh dalam kasus saya, saya perlu mengakses [svn (subversion)][svn] dengan alamat https://svnserver.com (192.168.1.3), namun server tersebut hanya membuka akses untuk alamat tertentu misalnya sshtunnelserver.com (192.168.1.5). Dari sini kita bisa akses server svn tersebut tapi hanya melalui server sshtunnelserver.com dengan menggunakan ssh, dengan syarat ssh server tersebut bisa kita akses. Bagaimana cara melakukanya?

```
ssh -L 8443:svnserver.com:443 user@sshtunnelserver.com
```

Dengan menggunakan command tersebut saya telah memforward svnserver.com ke localhost dengan port 8443. Dengan itu saya bisa mengakses halaman svnserver.com:443 melalui localhost:8443. Selanjutnya saya melakukan clone repository seperti biasa dengan menggunakan subversion.

```
svn co https://localhost:8443/path/to/folder
```
Ok saya akan coba jelaskan sebenarnya apa yang kita lakukan dengan command tersebut.
dengan menggunakan perintah `ssh -L [bindport]:[targethost]:[targetport] [sshuser]@[sshserver]` kita memerintahkan ssh untuk menangkap semua request ke localhost dengan port yang kita tentunkan, dan meneruskanya ke targethost melalui sshserver. Dan mengembalikan response ke pada client.

Saat melakukan tunneling, kita akan ikut masuk ke sshserver, dan ketika kita memutuskan hubungan ke sshserver, maka tunneling kita akan berakhir.

selain untuk melakukan tunneling, kita juga bisa menggunakan ssh server tersebut sebagai proxy. dengan cara menjalankan perintah berikut

```
ssh -D8181 user@sshtunnelserver.com
```

selanjutnya anda tinggal melakukan pengaturan proxy menggunakan [SOCKS][socks] dengan host localhost dan port 8181. dan telah membuat proxy sederhana.
Selamat Mencoba

~faitz

[svn]:http://en.wikipedia.org/wiki/Apache_Subversion
[ssh]:http://en.wikipedia.org/wiki/Secure_Shell‎
[socks]:http://en.wikipedia.org/wiki/SOCKS