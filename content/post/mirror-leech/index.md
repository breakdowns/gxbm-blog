+++
author = "Breakdowns"
title = "Mirror & Leech"
date = "2023-10-13"
description = "Cara menggunakan beberapa fitur Mirror dan Leech"
categories = [
    "Tutorial"
]
tags = [
    "Mirror Bot"
]
image = "banner.jpg"
+++

## Mengestrak dan Pengarsipan
Untuk Mengestrak atau Mengarsipkan, Anda hanya perlu mengirim perintah Mirror atau Leech, Lalu akan muncul beberapa opsi seperti gambar di bawah.
![Preview](extract-archive.jpg)

## Mengekstrak file yang dilindungi kata sandi
**NOTE:** Di sini kita memiliki File Arsip `.zip` yang kata sandinya adalah `Breakdowns`.
- Tanpa membalas link/file:
![Preview](extract-protected-pw-without-reply.jpg)
- Dengan membalas link/file:
![Preview](extract-protected-pw-with-reply.jpg)

## Menambah Kustom NamaFile saat Mirror atau Leech
**NOTE:** Kustom NamaFile tidak mendukung saat Mirror dan Leech Torrent atau Magnet.

Untuk menggunakan Kustom pada NamaFile Anda harus menambah argumen `n:`.
- Tanpa membalas link/file:
![Preview](custom-filename-without-reply.jpg)
- Dengan membalas link/file:
![Preview](custom-filename-with-reply.jpg)

## MultiDownload
**NOTE:** Hanya bekerja saat Anda membalas pesan linknya.

Untuk menggunakannya Anda perlu menambah angka jumlah link Anda setelah command. Contoh di sini saya memiliki 2 link.
![Preview](multidownload-1.jpg)
![Preview](multidownload-2.jpg)

## BulkDownload (Download dalam jumlah sekaligus banyak)
**NOTE:** Hanya bekerja saat Anda membalas pesan linknya.

Untuk download dalam jumlah besar Anda harus menambahkan argumen `b` setelah perintah. Dan untuk download dalam jumlah tertentu, gunakan `:` setelah `b` tanpa spasi. 
**Misalnya:** `b:0:7` (dimulai dari 0 berakhir hingga 7 secara massal) awal default adalah nol (tautan pertama).
![Preview](bulkdownload.jpg)

## Mirror di Direktori yang sama
**NOTE:** Argumen `m:` dengan nama folder harus tanpa spasi. 
Direktori yang sama akan berguna untuk Mengekstrak file yang dipisah. 
Gabungkan argumen ini dengan Multi atau BulkDownload.
![Preview](mirror-same-directory.jpg)

## Memilih file pada Torrent
Untuk memilih file pada Torrent sebelum download Anda perlu menambahkan argumen `s` setelah command.
- Tekan tombol **Pincode** untuk mendapatkan Kode Pin.
![Preview](torrentselect-pincode.jpg)
- Tekan tombol **Select Files** lalu akan di arahkan ke Web, setelah itu masukkan Kode Pin yang Anda dapatkan, lalu tekan tombol **Submit**.
![Preview](torrentselect-enterpin.jpg)
- Pilih file yang ingin Anda download, lalu tekan tombol **Kirim/Send**.
![Preview](torrentselect-selectfile.jpg)
- Selesai!
![Preview](torrentselect-done.jpg)

## Tugas Seeding
Untuk menggunakan fitur Seeding Anda perlu menambahkan argumen `d` setelah command, Untuk rasio spesifik adalah `d:1.0`, Untuk rasio dan waktu tertentu `d:1.0:10`, Anda juga hanya dapat menambahkan waktu > `d::10` pada menit.
![Preview](seeding-task.jpg)
