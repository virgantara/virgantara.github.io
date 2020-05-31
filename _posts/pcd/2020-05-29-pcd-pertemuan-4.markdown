---
layout: post
permalink: /course/pengolahan-citra-digital/pertemuan-4
title: Image Enhancement Domain Spasial Histogram Operation
description: materi singkat tentang peningkatan kualitas citra. # Add post description (optional)
img: software.jpg # Add image post (optional)
tags: [image, citra, digital, enhancement, contoh, histogram] # add tag
backlink: course/pengolahan-citra-digital
---

Konten:
1. [Pengertian Histogram](#pengertian-histogram)
1. [Adaptive Thresholding](#adaptive-thresholding)
1. [Histogram Equalization](#histogram-equalization)
1. [Referensi](#referensi)
### Pengertian Histogram ###

Dalam dunia statistik, histogram berarti frekuensi kemunculan suatu data. Dalam PCD, histogram juga memiliki arti sama. Hanya saja, histogram di sini lebih spesifik ke frekuensi intensitas citra. Contohnya seperti ini. Anggap ada citra 8-bit, frekuensi kemunculan berkisar antar 0 - 255. Kisaran ini disebar dalam bentuk grafik dimulai dari 0 hingga 255. Kemudian, dihitung, berapa jumlah piksel dengan intensitas 0, 1, 2, dan seterusnya hingga 255. Kita lihat contoh histogram dari sebuah citra pada Gambar 4.1

![image info]({{site_url}}/images/histogram.png) 
*Gambar 4.1* (a) Citra asli, (b) histogram dari (a)


Histogram juga berfungsi sebagai dasar teknik pemrosesan spasial [[1](#ref1)]. Manipulasi histogram sangat efektif untuk peningkatan dan perbaikan citra. Pada pertemuan ini, dibahas beberapa teknik pemanfaatan histogram.

---

### Adaptive Thresholding ###

Pada pertemuan 3, sudah dibahas tentang konsep *threshold* pada citra biner. Namun, dalam penentuan nilai ambang batasnya masih manual. Pembahasan kali ini akan memanfaatkan teknik adaptif untuk *thresholding*. Apa itu adaptif? Adaptif artinya memiliki sifat adaptasi terhadap sesuatu. Sifat adaptif ini bisa dipakai untuk penentuan nilai ambang batas / *threshold*-nya. Tentunya, setiap citra memiliki kasus dan keunikan sendiri. Sehingga, *adaptive thresholding* sangat diperlukan untuk mengatasi kasus-kasus ini.

#### Local Adaptive ####

Pemrosesan adaptif ini ada dua jenis, yaitu: local dan global. *Local Adaptive* ini memanfaatkan pemrosesan dengan sub-citra. Sub-citra ini diperoleh dengan membuat citra kecil dengan ukuran tertentu. Istilah lainnya dari sub-citra adalah kernel, *masking*, atau *patch*. Contoh teknik yang menerapkan konsep ini, yaitu: *local mean adaptive* dan *gaussian adaptive*. *Local adaptive* ini menghitung intensitas piksel-piksel yang berdekatan / *neighbouring pixels*. Secara khusus, nilai ambang batas adaptif $$ t $$ ini berdasarkan pada nilai statistik [[2](#ref2)]. Nilai bisa berasal dari $$ t=mean + C $$, $$ t=median + C $$, atau $$ t = floor((\max - \min) / 2 ) + C $$ dengan ukuran *patch* N x N piksel. Gambar 4.2 adalah contoh penerapan *local thresholding* dengan ukuran *patch* 15 dan $$ C = 7 $$.

![image info]({{site_url}}/images/local_thresholding.png) 
*Gambar 4.2* (a) Citra asli, (b) *local adaptive mean threshold*, (c) *local adaptive gaussian threshold*

#### Global Adaptive ####

Pada kasus *global thresholding*, biasanya nilai ambang batas $$ t $$ ditentukan secara acak. Namun, ada metode, yang bernama Otsu, menentukan nilai $$ t $$ secara otomatis. Kok bisa? 

Metode Otsu membagi citra menjadi dua bagian, *background* dan *foreground*. Metode Otsu mengiterasi semua nilai $$ t $$ yang memungkinkan dan mengukur penyebaran intensitas per piksel pada citra *background* dan *foreground*. Tujuannya adalah untuk menemukan nilai ambang batas di mana jumlah penyebaran *background* dan *foreground* adalah minimal. *Well*, tahap awal penentuan $$ t $$ ini juga manual tentunya. Selanjutnya, yuk kita lihat bagaimana perbandingan antara *global thresholding* manual dengan Otsu pada Gambar 4.3.

![image info]({{site_url}}/images/global_thresholding.png) 
*Gambar 4.3* (a) Citra asli, (b) *global threshold*, (c) *Otsu threshold*


---

### Histogram Equalization ###

Anggap ada citra dengan kontras yang rendah, entah citra dengan kecerahan rendah atau *low brightness* (LB) atau kecerahan tinggi atau *high brightness* (HB), kemudian kita amati histogramnya. Pada citra LB, histogram akan cenderung berada pada intensitas rendah. Dan sebaliknya untuk citra HB, maka akan berada pada intensitas tinggi. 

---
### Referensi ###

<a id="ref1">[1]</a> Gonzalez, R., & Woods, R. (2002). Digital image processing. Prentice Hall.

<a id="ref2">[2]</a> Solomon, C., & Breckon, T. (2011). Fundamentals of Digital Image Processing. Wiley-Blackwell.

  


<a href="#top">&#8593; Back to top</a>