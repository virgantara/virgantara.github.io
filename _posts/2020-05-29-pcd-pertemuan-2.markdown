---
layout: post
permalink: /course/pengolahan-citra-digital/pertemuan-2
title: Akuisisi Citra
date: 2020-05-28 00:00:00 +0300
description: materi singkat tentang akuisisi citra digital. # Add post description (optional)
img: software.jpg # Add image post (optional)
tags: [akuisisi, citra, digital, definisi, contoh] # add tag
---

<a href="{{ site.baseurl }}/course/pengolahan-citra-digital">&#8592; kembali</a>

Daftar Isi:
1. [Model Kamera Pinhole](#model-kamera-pinhole)
1. [Model Kamera Thin Lens](#model-kamera-thin-lens)
1. [Sensor Array](#sensor-array)
1. [Sampling dan Quantization](#sampling-dan-quantization)
1. [Referensi](#referensi)

Akuisisi Citra dikatakan sebagai proses mengubah objek ataupun latar (*scene*) menjadi ke dalam bentuk digital. Pembahasan pada materi ini dimulai dari model akuisisi citra yang paling sederhana.  

### Model Kamera Pinhole ###

![image info]({{site_url}}/images/pinhole_camera.png)   
*Gambar 2.1*. Model kamera pinhole yang memproyeksikan terbalik objek atau latar.

Kamera pinhole merupakan model kamera yang paling sederhana dan telah digunakan sejak abad ke-13 <sup>[[1]](#ref1)</sup>. Saat ini, model ini sudah tidak lagi digunakan. Namun, model ini sangat berguna untuk membantu dalam pemahaman terhadap komponen optik dari kamera. 

Kamera pinhole berbentuk kotak seperti kubus atau balok tertutup dengan lubang kecil di salah satu sisi. Lubang ini berfungsi sebagai jalan masuk cahaya yang kemudian akan memproyeksikan objek atau latar menjadi terbalik di sisi dalam yang berlawanan dengan sisi lubang. Perhatikan Gambar 2.1.

---

### Model Kamera Thin Lens ###


![image info]({{site_url}}/images/thin_lens.jpg)   
*Gambar 2.2*. Model kamera Thin Lens. (B) adalah **bidang citra**

Model kamera pinhole memang sangat memudahkan dalam pemahaman konsep geometri kamera. Namun, model ini tidak pernah dipakai untuk praktik. Hasil proyeksi dari model pinhole tidak terlalu tajam. Kelemahan dari pinhole ini dipecahkan dengan model lensa tipis yang menggantikan posisi lubang jarum. 

Masih ingatkan kalian dengan hukum pembiasan cahaya? Perhatikan Gambar 2.2. Sinar datang sejajar dengan sumbu, dibiaskan menuju titik fokus. Sinar datang melalui titik fokus, akan dibiaskan sejajar sumbu utama. Dan yang terakhir, sinar datang melalui pusat optik, tidak mengalami pembiasan. 

---

### Sensor Array ###

![image info]({{site_url}}/images/imaging.png)   
*Gambar 2.3*. Ilustrasi pencitraan dengan Sensor Array.

Pada Gambar 2.3, objek latar memantulkan cahaya dari sumbernya (contoh: cahaya matahari dan pantulan cahaya dari permukaan objek). Pantulan cahaya ini kemudian ditangkap oleh sensor. Di dalam sensor ini, ada dua proses yang berjalan. Pertama. pemfokusan cahaya oleh lensa terhadap objek ke dalam bidang citra. Kedua, konversi dari data analog ke dalam bentuk digital.

---

### *Sampling* dan *Quantization* ###

Pada subbab sebelumnya, kalian sudah mempelajari proses terjadinya akuisisi citra. Tujuan utama dari semua ini adalah mendapatkan citra digital. Demi mendapatkan citra digital, dua proses yang perlu dilalui, yaitu *sampling* dan *quantization*. 



---

### Referensi ###


   <a id="ref1">[1]</a> Burger, W., & Burge, M. (2009). Principles of Digital Image Processing. Springer London.

   <a id="ref2">[2]</a> Zhu, Q., Mai, J., & Shao, L. (2015). A Fast Single Image Haze Removal Algorithm Using Color Attenuation PriorIEEE Transactions on Image Processing, 24(11), 3522–3533.





<a href="#top">&#8593; Back to top</a>

