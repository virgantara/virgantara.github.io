---
layout: post
permalink: /course/pengolahan-citra-digital/prasyarat
title: Prasyarat Matakuliah PCD
date: 2020-05-28 00:00:00 +0300
description: prasyarat. # Add post description (optional)
img: software.jpg # Add image post (optional)
tags: [prasyarat, citra, digital] # add tag
---

<a href="{{ site.baseurl }}/course/pengolahan-citra-digital">&#8592; kembali</a>

Untuk mengikuti mata kuliah ini, ada beberapa prasyarat yang harus dipenuhi:
1. Memahami konsep dasar matriks
1. Memahami konsep dasar Aljabar Linier
1. Memahami beberapa fungsi Statistik
1. Memahami beberapa konsep Kalkulus
1. Memiliki dasar pemrograman terutama Python

---

Untuk materi praktikum, ada beberapa hal yang harus dilakukan:
1. Menginstal Python versi 3.6 ke atas 
1. Menginstal OpenCV 3.4 di komputer / PC masing-masing
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

## Instalasi OpenCV di Ubuntu ##

1. Refresh package index
    ```shell
    $ sudo apt update
    $ sudo apt install python3-opencv
    ```

1. Cek jika opencv sudah terinstal dengan:
    ```shell
    python3 -c "import cv2; print(cv2.__version__)"
    ```

    ```
    Output

    3.2.0
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

Instalasi di Windows

1. <a href="https://www.howtogeek.com/197947/how-to-install-python-on-windows/" target="_blank">Instalasi di Windows
 Python di Windows</a>
1. <a href="https://docs.opencv.org/master/d5/de5/tutorial_py_setup_in_windows.html" target="_blank">Instalasi OpenCV di Windows</a>
1. Instalasi Numpy di Windows

    ```shell
    pip3 install numpy
    ```
1. Instalasi Matplotlib di Windows
    ```shell
    pip3 install matplotlib
    ```
