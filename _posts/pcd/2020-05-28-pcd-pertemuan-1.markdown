---
layout: post
permalink: /course/pengolahan-citra-digital/pertemuan-1
title: Pendahuluan
date: 2020-05-28 00:00:00 +0300
description: materi singkat pengatar pengenalan citra digital. # Add post description (optional)
img: software.jpg # Add image post (optional)
tags: [introduction, pengenalan, citra, digital, definisi, contoh] # add tag
backlink: course/pengolahan-citra-digital
---

Konten:
1. [Definisi PCD](#definisi-pcd)
1. [Contoh penerapan PCD](#contoh-penerapan-pcd)
1. [Tahapan-tahapan dalam PCD](#tahapan-tahapan-dalam-pcd)
1. [Komponen dalam PCD](#komponen-dalam-pcd)
1. [Kompresi Citra](#kompresi-citra)
1. [Latihan](#latihan)
1. [Referensi](#referensi)

---

### Definisi PCD ### 


#### Definisi Singkat dari Citra
Sebelum terjun ke materi, kita kenalan dulu dengan apa yang disebut **citra**. Mungkin, kalian bertanya-tanya, kenapa ***image*** ketika diterjemahkan ke dalam bahasa Indonesia menjadi citra? Kenapa terjemahannya bukan gambar? *Well*, citra secara makna memiliki konteks yang lebih luas karena citra bisa bermakna citra satu dimensi (1D), dua dimensi (2D), tiga dimensi (3D) dan sebagainya. Sedangkan gambar merupakan citra 2D. Contohnya, citra 2 dimensi (2D) bisa kalian temukan pada foto digital yang biasa kalian ambil dengan kamera, citra 3 dimensi seperti pada model objek 3 dimensi dari AutoCAD, dan sebagainya.

#### Model dari Citra
Teman-teman yang telah mengambil mata kuliah Aljabar Linier (AL) masih ingat kan dengan beberapa fungsi matematis dan matriks? Di dalam mata kuliah AL, kalian belajar tentang matriks dua dimensi (2D). Coba kalian bayangkan sebuah citra dalam bentuk matriks 2D. Sulit gak? Oke, kita ilustrasikan fungsi tersebut ke dalam bentuk fungsi $$ f(x,y) $$. Sehingga, didapat matriks pada Persamaan 1:  



$$ f(x,y) =  \begin{bmatrix} x_0y_0 & x_1y_0 & \cdots & x_ny_0 \\  x_0y_1 & x_1y_1 & \cdots & x_ny_1 \\ \vdots & \vdots & \vdots & \vdots \\ x_0y_n & x_1y_1 & \cdots & x_ny_n \\ \end{bmatrix} $$


Tenang, tidak perlu panik. Kita bedah rumus pada Persamaan 1 ya. Kita ingat kembali bahwa citra pada dasarnya adalah sebuah matriks 2D. Bayangkan matriks 2D dalam bentuk koordinat spasial kartesian dengan sumbu x dan sumbu y. Oiya, yang perlu diingat adalah adanya perbedaan koordinat sumbu $$ (x,y) $$ pada citra dengan koordinat kartesian. Perbedaannya adalah letak titik 0 (nol). Pada citra digital, titik nol berada di atas (Gambar 1.1A). Sedangkan kartesian berada di bawah (Gambar 1B). Fungsi $$ f(x,y) $$ pada Pers. 1 adalah fungsi **intensitas** pada tiap titik citra. Satuan titik pada citra digital disebut dengan **piksel** (pixel). Nilai intensitas pada tiap piksel memiliki nilai yang sifatnya **diskrit**. Adapun rentang nilai intensitas ini antara **0 hingga 255**.

![image info]({{site_url}}/images/koordinat_citra.png)   
*Gambar 1.1*. (A) Koordinat Kartesian pada selain citra digital. (B) Koordinat kartesian pada citra digital

Untuk lebih memudahkan pemahaman, kita *crop* sebagian kecil dengan ukuran 5 x 6 piksel dari sebuah citra (Gambar 2A). Kemudian, diilustrasikan besarnya intensitas tiap titik (Gambar 2B).

![image info]({{site_url}}/images/cropping.jpg)   
*Gambar 1.2*. (A) Citra sampel dalam grayscale. (B) Citra hasil *cropping* dari (A) dengan ukuran 5x6 piksel.

Setiap blok pada Gambar 1.2B berukuran 1 piksel. Setiap piksel memiliki nilai intensitas. Contoh: pada Gambar 2B titik (0,0) memiliki intesitas sebesar 70. Jika ada citra memiliki koordinat x,y serta nilai intensitas yang terbatas dan diskrit maka disebut sebagai **citra digital**. 

---

### Contoh Penerapan PCD ###

Saat ini, banyak sekali ditemukan contoh dari implementasi PCD dalam kehidupan sehari-hari. Bahkan, sulit rasanya kita lepas dari PCD. Dalam media sosial contohnya: dari bangun tidur, membuka Instagram di **smartphone**, selfie, jepret, buka Facebook pun juga demikian, Snapchat, dan sebagainya. Contoh lain yang tidak kalah penting adalah dalam bidang kesehatan. PCD dalam kesehatan bisa dikatakan mengalami peningkatan secara signifikan. [[1]](#ref1)  


1. #### Kesehatan ####

   1. Sinar Gamma   
Metode Pencitraan dengan Sinar Gamma atau *Gamma Ray* sudah ditemukan di awal abad 20. Teknologi ini bisa diterapkan pengobatan dengan bahan nuklir. Secara teknis, pengobatan ini dilakukan dengan menyuntik tubuh pasien dengan Isotop Radioaktif. Kemudian, citra dari kamera khusus, yang bisa mendeteksi sinar gamma, dianalisis (Gambar 1.3). 

       ![image_info]({{site_url}}/images/gamma.png)
*Gambar 1.3*. Pencitraan dengan Sinar Gamma (A) Scan tulang. (B) citra PET. Sumber gambar (A) G.E. Medical Systems, (B) Dr. Michael E. Casey, CTI PET Systems

   1. Sinar X 
    Sinar X adalah salah satu teknologi pemanfaatan gelombang elektromagnetik dalam pencitraan. Alat yang mungkin pernah kalian jumpai adalah Rontgen. 
    
1. #### Media Sosial ####
   1. Pengenalan Wajah di Facebook
   
      Ketika kalian pernah menggunggah foto ke Facebook yang isinya foto kalian dengan beberapa teman atau keluarga, Facebook akan memberikan saran untuk menandai atau *tag* nama teman berdasarkan wajah. Pernah tidak kalian terpikir bagaimana Facebook bisa tahu bahwa itu foto temanmu, kakakmu, atau adikmu? Boro-boro tahu bahwa itu wajah teman, kebayang gak bagaimana Facebook tahu bahwa itu wajah manusia? Teknologi ini disebut dengan **Face Recognition** atau **Pengenalan Wajah**. Teknik ini dibuat berdasarkan penelitian ilmiah yang dipublikasikan di Computer Vision and Pattern Recognition (CVPR) pada tahun 2014 oleh Yaniv Taigman *et al*. <sup>[[2]](#ref2)</sup>  
   1. Telinga dan Lidah di Snapchat
   
      Hayo, siapa yang pernah iseng-iseng mainan filter telinga dan lidah hewan di Snapchat? Teknologi yang dipakai Snapchat sudah ada sejak tahun 2001 lho. Teknik yang dikembangkan oleh Viola & Jones (VJ) ini memanfaatkan keunikan dari wajah manusia. Mata, hidung, bibir, lidah, dan telinga jika dilihat secara digital memiliki intensitas yang berbeda dengan area sekitarnya. VJ menggunakan beberapa blok citra dengan ukuran tertentu yang hanya terdiri atas dua intensitas warna, yaitu gelap dan terang. Contoh: mata selalu memiliki intensitas lebih rendah daripada dahi. <sup>[[3]](#ref3)</sup> 


---

### Tahapan-tahapan dalam PCD ###

Dalam kuliah ini, pembahasan PCD akan dibagi menjadi beberapa langkah (lihat Gambar 1.4). Pembagian langkah ini bertujuan agar memudahkan pemahaman. Tidak semua langkah dalam PCD diterapkan pada citra digital <sup>[[1]](#ref1)</sup>. Ada kalanya hanya perlu dua langkah, ada tiga langkah, ada pula lebih dari tiga langkah. Adapun pembagiannya adalah sebagai berikut:

   A. Akuisisi Citra (*Image Acquisition*)
   
   Setiap pengolahan citra pasti melewati fase ini. Fase ini fase pertama yang menjalankan beberap proses *scaling*, *sampling*, dan sebagainya.

   B. Peningkatan Citra (*Image Enhancement*) 

   Tujuan dari tahap ini adalah menonjolkan informasi baik sebagian maupun keseluruhan dari citra. 

   C. Restorasi Citra (*Image Restoration*)

   Dalam beberapa kondisi, citra digital yang diakuisisi mengandung banyak *noise*, seperti noda hitam, putih yang sangat mengganggu. Tahap ini berfungsi mengembalikan kondisi citra mendekati kondisi awal atau ideal.

   D. Pemrosesan Citra Berwarna (*Color Image Processing*)

   Tahap ini memiliki tantangan tersendiri. Tidak hanya satu kanal (*channel*) warna, melainkan tiga atau empat kanal warna. 

   E. Pemrosesan Domain Frekuensi

   Tahap ini mengolah citra digital dalam domain frekuensi. Salah satu cara dalam tahap ini adalah menggunakan teknik Fourier Transform. 

   F. *Image Dehazing*

   Tahapan ini berfungsi untuk meningkatan visibilitas dari citra berkabut memperjelas objek yang ada dibelakang kabut.

   G. Segmentasi Citra (*Image Segmentation*)

   Segmentasi citra membagi atau mempartisi citra menjadi beberapa bagian berdasarkan karakteristik tertentu. Segmentasi sering dipakai untuk membedakan objek dengan latar.

   H. Pengenalan Citra (*Image Recognition*)

   Pengenalan citra bisa dikatakan sebagai proses pelabelan terhadap suatu objek dari citra.

![image_info]({{site_url}}/images/knowledge_base.png)
*Gambar 1.4*. Knowledge Base dari PCD

Pembagian ini bukanlah batasan. Tentunya, seiring berkembangnya zaman dan teknologi, pembagian ini bisa jadi ada penambahan atau sudah kadaluarsa.

---
### Komponen dalam PCD ###

![image_info]({{site_url}}/images/komponen_pcd.png)
*Gambar 1.5*. Komponen dari PCD

*Image sensors*, memiliki dua elemen yang diperlukan untuk memperoleh citra digital. Yang pertama adalah perangkat pengindera fisik yang peka terhadap energi yang dipancarkan oleh objek yang dicitrakan. Yang kedua disebut *digitizer*, adalah perangkat yang berfungsi untuk mengubah output perangkat penginderaan fisik menjadi bentuk digital.

*Specialized image processing hardware* biasanya terdiri dari perangkat *digitizer* dan hardware yang melakukan operasi primitif lainnya seperti operasi *arithmetic logic unit* (ALU). Misalnya, pengurangan kebisingan.

*Computer* pada sistem pemrosesan citra bisa berfungsi seperti *Personal Computer* (PC) biasa atau sekelas super komputer.

*Image Display* yang digunakan saat ini adalah monitor TV berwarna.

*Hardcopy Devices* bisa berupa alat untuk merekam gambar termasuk printer laser, kamera film, unit inkjet dan CD-ROM.

---

### Kompresi Citra ###

Bagi kalian yang hobi desain, fotografi, atau edit foto pasti sudah tahu dengan beberapa format kompresi citra seperti: JPEG, PNG, GIF, TIFF, dan sebagainya. Tapi, tahukah kalian perbedaan yang mendasar diantara format kompresi tersebut? Kita bedah satu-satu ya.

1. Joint Photographic Experts Group (JPEG)

   JPEG saat ini merupakan format kompresi yang paling banyak dipakai dalam dunia internet maupun kamera digital. JPEG memiliki kemampuan kompresi untuk membuang informasi yang tidak bisa dideteksi oleh mata manusia sehingga JPEG bisa memiliki ukuran file yang kecil. Kemampuan ini dinamakan dengan *Lossy Compression*.  

1. Portable Network Graphics (PNG)

   Kemampuan kompresi PNG sedikit di bawah JPEG. PNG memiliki kemampuan menyimpan satu informasi lagi yaitu alpha. Alpha ini berfungsi sebagai nilai transparansi dari citra. Tentunya, ukuran file PNG lebih besar dari JPEG dengan resolusi sama. 

1. Graphics Interchange Format (GIF)

   Format kompresi GIF hanya mendukung 8-bit warna tiap pikselnya. Tentunya, tidak disarankan membuat desain banner, logo, foto dengan format kompresi GIF. Namun, GIF bisa untuk animasi tanpa audio.

1. Tagged Image File Format (TIFF)

   TIFF merupakan format kompresi yang tidak hanya mendukung RGB-alpha, tetapi juga format desimal dan nilai kedalaman citra.

---

### Latihan ###

---

### Referensi ###


   <a id="ref1">[1]</a> Gonzalez, R., & Woods, R. (2002). Digital image processing. Prentice Hall.

   <a id="ref2">[2]</a> Y. Taigman, M. Yang, M. Ranzato and L. Wolf, "DeepFace: Closing the Gap to Human-Level Performance in Face Verification," 2014 IEEE Conference on Computer Vision and Pattern Recognition, Columbus, OH, 2014, pp. 1701-1708, doi: 10.1109/CVPR.2014.220.

   <a id="ref3">[3]</a> Viola, P., & Jones, M. (2001). Rapid object detection using a boosted cascade of simple features. In Proceedings of the 2001 IEEE Computer Society Conference on Computer Vision and Pattern Recognition. CVPR 2001 (pp. I–511–I–518). IEEE Comput. Soc.

<a href="#top">&#8593; Back to top</a>

