---
layout: post
title: Pengolahan Citra Digital
date: 2020-05-28 00:00:00 +0300
description: materi singkat pengatar pengenalan citra digital. # Add post description (optional)
img: software.jpg # Add image post (optional)
tags: [pengenalan, citra, digital, definisi, contoh] # add tag
---

# Pengolahan Citra Digital
Github ini berisi tentang materi perkuliahan Pengolahan Citra Digital (PCD)

Daftar Isi:
1. Pengenalan PCD
   1. [Definisi PCD](#definisi-pcd)
   1. [Contoh penerapan PCD](#contoh-penerapan-pcd)
   1. Tahapan-tahapan dalam PCD
   1. Komponen dalam PCD
1. Item 2
1. Item 3


##  Pengenalan PCD ##
### Definisi PCD ### 


#### Definisi Singkat dari Citra
Sebelum terjun ke materi, kita kenalan dulu dengan apa yang disebut **citra**. Mungkin, kalian bertanya-tanya, kenapa ***image*** ketika diterjemahkan ke dalam bahasa Indonesia menjadi citra? Kenapa terjemahannya bukan gambar? *Well*, citra secara makna memiliki konteks yang lebih luas dibandingkan dengan gambar. Sederhananya, gambar itu merupakan bagian dari citra. Contohnya, citra 2 dimensi (2D) bisa kalian temukan pada foto digital yang biasa kalian ambil dengan kamera, citra 3 dimensi seperti pada model objek 3 dimensi dari AutoCAD, dan sebagainya. Selanjutanya dalam materi ini, istilah **citra 2D** saya sederhanakan menjadi **citra**. Artinya, setiap ada kata **citra** berarti citra 2D.

#### Model dari Citra
Teman-teman yang telah mengambil mata kuliah Aljabar Linier (AL) masih ingat kan dengan beberapa fungsi matematis dan matriks? Di dalam mata kuliah AL, kalian belajar tentang matriks dua dimensi (2D). Coba kalian bayangkan sebuah citra dalam bentuk matriks 2D. Sulit gak? Oke, kita ilustrasikan fungsi tersebut ke dalam bentuk fungsi <img src="https://render.githubusercontent.com/render/math?math=f(x,y)">. Sehingga, didapat matriks pada Persamaan 1:  



![$ f(x,y) =  \begin{bmatrix} x_0y_0 & x_1y_0 & \cdots & x_ny_0 \\  x_0y_1 & x_1y_1 & \cdots & x_ny_1 \\ \vdots & \vdots & \vdots & \vdots \\ x_0y_n & x_1y_1 & \cdots & x_ny_n \\ \end{bmatrix} $](https://render.githubusercontent.com/render/math?math=%24%20f(x%2Cy)%20%3D%20%20%5Cbegin%7Bbmatrix%7D%20x_0y_0%20%26%20x_1y_0%20%26%20%5Ccdots%20%26%20x_ny_0%20%5C%5C%20%20x_0y_1%20%26%20x_1y_1%20%26%20%5Ccdots%20%26%20x_ny_1%20%5C%5C%20%5Cvdots%20%26%20%5Cvdots%20%26%20%5Cvdots%20%26%20%5Cvdots%20%5C%5C%20x_0y_n%20%26%20x_1y_1%20%26%20%5Ccdots%20%26%20x_ny_n%20%5C%5C%20%5Cend%7Bbmatrix%7D%20%24) 


Tenang, tidak perlu panik. Kita bedah rumus pada Persamaan 1 ya. Kita ingat kembali bahwa citra pada dasarnya adalah sebuah matriks 2D. Bayangkan matriks 2D dalam bentuk koordinat spasial kartesian dengan sumbu x dan sumbu y. Oiya, yang perlu diingat adalah adanya perbedaan koordinat sumbu (x,y) pada citra dengan koordinat kartesian. Perbedaannya adalah letak titik 0 (nol). Pada citra digital, titik nol berada di atas (Gambar 1A). Sedangkan kartesian berada di bawah (Gambar 1B). Fungsi f(x,y) pada Pers. 1 adalah fungsi **intensitas** pada tiap titik citra. Satuan titik pada citra digital disebut dengan **piksel** (pixel). Nilai intensitas pada tiap piksel memiliki nilai yang sifatnya **diskrit**. Adapun rentang nilai intensitas ini antara **0 hingga 255**.

![image info]({{site_url}}/assets/img/koordinat_citra.png)   
*Gambar 1*. (A) Koordinat Kartesian pada selain citra digital. (B) Koordinat kartesian pada citra digital

Untuk lebih memudahkan pemahaman, kita *crop* sebagian kecil dengan ukuran 5 x 6 piksel dari sebuah citra (Gambar 2A). Kemudian, diilustrasikan besarnya intensitas tiap titik (Gambar 2B).

![image info]({{site_url}}/assets/img/cropping.jpg)   
*Gambar 2*. (A) Citra sampel dalam grayscale. (B) Citra hasil *cropping* dari (A) dengan ukuran 5x6 piksel.

Setiap blok pada Gambar 2B berukuran 1 piksel. Setiap piksel memiliki nilai intensitas. Contoh: pada Gambar 2B titik (0,0) memiliki intesitas sebesar 70. Jika ada citra memiliki koordinat x,y serta nilai intensitas yang terbatas dan diskrit maka disebut sebagai **citra digital**. 

<a href="#top">Back to top</a>

### Contoh Penerapan PCD ###

Saat ini, banyak sekali ditemukan contoh dari implementasi PCD dalam kehidupan sehari-hari. Bahkan, sulit rasanya kita lepas dari PCD. Dalam media sosial contohnya: dari bangun tidur, membuka Instagram di **smartphone**, selfie, jepret, buka Facebook pun juga demikian, Snapchat, dan sebagainya. Contoh lain yang tidak kalah penting adalah dalam bidang kesehatan. PCD dalam kesehatan bisa dikatakan mengalami peningkatan secara signifikan. [[1]](#ref1)  


1. #### Kesehatan ####

   1. Sinar Gamma   
Metode Pencitraan dengan Sinar Gamma atau *Gamma Ray* sudah ditemukan di awal abad 20. Teknologi ini bisa diterapkan pengobatan dengan bahan nuklir. Secara teknis, pengobatan ini dilakukan dengan menyuntik tubuh pasien dengan Isotop Radioaktif. Kemudian, citra dari kamera khusus, yang bisa mendeteksi sinar gamma, dianalisis (Gambar 3). 

       ![image_info]({{site_url}}/assets/img/gamma.png)
*Gambar 3*. Pencitraan dengan Sinar Gamma (A) Scan tulang. (B) citra PET. Sumber gambar (A) G.E. Medical Systems, (B) Dr. Michael E. Casey, CTI PET Systems

   1. Sinar X 
    Sinar X adalah salah satu teknologi pemanfaatan gelombang elektromagnetik dalam pencitraan. Alat yang mungkin pernah kalian jumpai adalah Rontgen. 
    
1. #### Media Sosial ####
   1. Pengenalan Wajah di Facebook
   
      Ketika kalian pernah menggunggah foto ke Facebook yang isinya foto kalian dengan beberapa teman atau keluarga, Facebook akan memberikan saran untuk menandai atau *tag* nama teman berdasarkan wajah. Pernah tidak kalian terpikir bagaimana Facebook bisa tahu bahwa itu foto temanmu, kakakmu, atau adikmu? Boro-boro tahu teman, kebayang gak bagaimana Facebook tahu bahwa itu wajah manusia? Teknologi ini disebut dengan **Face Recognition** atau **Pengenalan Wajah**. Teknik ini dibuat berdasarkan penelitian ilmiah yang dipublikasikan di Computer Vision and Pattern Recognition (CVPR) pada tahun 2014 oleh Yaniv Taigman *et al.* dengan judul "DeepFace: Closing the Gap to Human-Level Performance in Face Verification". <sup>[[2]](#ref2)</sup>  
   1. Telinga dan Lidah di Snapchat
   
      Hayo, siapa yang pernah iseng-iseng mainan filter telinga dan lidah hewan di Snapchat? Teknologi yang dipakai Snapchat sudah ada sejak tahun 2001 lho. Teknik yang dikembangkan oleh Viola & Jones (VJ) ini memanfaatkan keunikan dari wajah manusia. Mata, hidung, bibir, lidah, dan telinga jika dilihat secara digital memiliki intensitas yang berbeda dengan area sekitarnya. VJ menggunakan beberapa blok citra dengan ukuran tertentu yang hanya terdiri atas dua intensitas warna, yaitu gelap dan terang. Contoh: mata selalu memiliki intensitas lebih rendah daripada dahi. <sup>[[3]](#ref3)</sup> 


<a href="#top">Back to top</a>


### Referensi ###


   <a id="ref1">[1]</a> Gonzalez, R., & Woods, R. (2002). Digital image processing. Prentice Hall.

   <a id="ref2">[2]</a> Y. Taigman, M. Yang, M. Ranzato and L. Wolf, "DeepFace: Closing the Gap to Human-Level Performance in Face Verification," 2014 IEEE Conference on Computer Vision and Pattern Recognition, Columbus, OH, 2014, pp. 1701-1708, doi: 10.1109/CVPR.2014.220.

   <a id="ref3">[3]</a> Viola, P., & Jones, M. (2001). Rapid object detection using a boosted cascade of simple features. In Proceedings of the 2001 IEEE Computer Society Conference on Computer Vision and Pattern Recognition. CVPR 2001 (pp. I–511–I–518). IEEE Comput. Soc.

