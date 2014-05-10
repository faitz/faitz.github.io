---
layout: post
title:  "Tips Untuk Menghilangkan Caching Paksa Pada Chrome"
categories: chrome tips
tags:	chrome webhack tips
---
Web developer biasanya selalu mendapatkan masalah ketika menggunakan Google Chrome, yaitu chrome melakukan cache terhadap javascript kita. Dan kadang-kadang kita terpaksa untuk melakukan clear cache terhadap browser, tapi ketika hal tersebut dilakukan maka setiap kita tidak sendang mendevelop web, dan mengakses halaman lain dengan terpaksa chrome akan melakukan pengunduhan total terhadap website yang kita tuju. Ada beberapa cara untuk memerintahkan chrome untuk melakukan clear cache.

###1. Hard Refresh
Metode ini sangan mudah dilakukan pada browser chrome dengan cara, menekan tombol `Shift+Ctrl+R` atau dengan melakukan klik kanan pada tombol refresh,seperti gambar berikut.

![Hard Refresh (Muat Ulang Keras)]({{site.url}}/assets/images/chrome-hard-refresh.jpeg)

untuk melakukan hal ini kita harus mengaktifkan developer mode dengan cara menekan tombol `Shift+Ctrl+I` atau dengan memilih `Menu->Tools(Alat)->Developer Tool(Alat Pengembang)`.

![Open up developer mode]({{site.url}}/assets/images/chrome-developertools.jpg)



###2. Disable Cache (Setting Developer Tools)
Metode berikutnya adalah dengan melakukan pengaturan pada developer tools dengan cara mencentang Disable Cache(while DevTool is open), ketika option ini decentang maka ketika kita merefresh halaman web yang ada kembangkan, Chrome akan selalu mengambil resource web dari sumbernya tanpa melalui cache.
![Configure developer tools]({{site.url}}/assets/images/chrome-setting-developer.jpeg)



###3. Mode Penyamaran (Incognito Mode)
Dengan menggunakan mode penyamaran (Incognito) maka Chrome tidak akan menggukan kontent-kontent yang telah di-cache oleh google ketika kita browsing.
![Incognito Mode]({{site.url}}/assets/images/chrome-incognito.jpeg)

Dengan tiga cara tersebut kita tidak perlu lagi untuk melaukan clear cache paksa pada Google Chrome, dan dapat melakukan koding secara nyaman, tak perlu bingung lagi soal cache.