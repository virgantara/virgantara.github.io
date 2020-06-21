---
layout: post
permalink: /course/kecerdasan-buatan/prasyarat
title: Prasyarat Matakuliah Kecerdasan Buatan
date: 2020-05-28 00:00:00 +0300
description: prasyarat. # Add post description (optional)
img: software.jpg # Add image post (optional)
tags: [prasyarat, citra, digital] # add tag
---

<a href="{{ site.baseurl }}/course/kecerdasaan-buatan">&#8592; kembali</a>

Untuk mengikuti mata kuliah ini, ada beberapa prasyarat yang harus dipenuhi:
1. Memahami konsep dasar matriks
1. Memahami konsep dasar Aljabar Linier
1. Memahami beberapa fungsi Statistik
1. Memahami beberapa konsep Kalkulus
1. Memiliki dasar pemrograman terutama Python

---

Untuk materi praktikum, ada beberapa hal yang harus dilakukan:
1. Menginstal Python versi 3.6 ke atas 
1. Menginstal scikit-learn di komputer / PC masing-masing
1. Menginstal Numpy
1. Menginstal Matplotlib

---

## Instalasi Python 3.6 di Ubuntu ##

1. Mengecek versi Python yang sudah terinstal
   
    ```shell
    python --version
    ```

1. Jalankan apt-get update dulu
   ```shell   
    $ sudo apt-get update
   ```

1. Jika Anda menggunakan versi lain dari Ubuntu (mis. Rilis LTS terbaru), kami sarankan untuk menggunakan PPA deadsnakes untuk menginstal Python 3.6:
    ```shell
    $ sudo apt-get install software-properties-common
    $ sudo add-apt-repository ppa:deadsnakes/ppa
    $ sudo apt-get update
    $ sudo apt-get install python3.6
    ```
---

## Instalasi Numpy di Ubuntu ##

Cara yang disarankan adalah menginstal modul Numpy langsung dari repositori Ubuntu:

```shell
$ sudo apt install python3-numpy
```

---

## Instalasi Matplotlib di Ubuntu ##

Cara yang disarankan adalah menginstal modul Numpy langsung dari repositori Ubuntu:

```shell
$ sudo apt install python3-matplotlib
```
<a href="#top">&#8593; Back to top</a>

---
