+++
author = "Breakdowns"
title = "User Setting"
date = "2023-12-12"
description = "Cara menggunakan beberapa fitur yang ada di User Setting"
categories = [
    "Tutorial"
]
tags = [
    "Mirror Bot"
]
image = "banner.jpg"
+++
## 1. YT-DLP Options
- **Catatan Opsi:** Tambahkan `^` sebelum integer atau float, beberapa nilai harus berupa numerik dan beberapa string.
Seperti `playlist_items:10` berfungsi dengan string, jadi tidak perlu menambahkan `^` sebelum angka tetapi `playlistend` hanya berfungsi dengan bilangan bulat jadi Anda harus menambahkan `^` sebelum angka seperti contoh di atas.
Anda juga dapat menambahkan Tuple dan dict. Gunakan tanda kutip ganda di dalam dict.
- **bol-meledag** adalah Kustom FFMPEG.
- Anda selalu dapat menambahkan kualitas video dari opsi api YT-DLP.
- **Jangan menambahkan ekstensi file saat mengganti nama menggunakan** `n:`.
- args(Ganti Nama, Kata Sandi) harus ditambahkan dengan posisi acak setelah tautan jika bersama dengan perintah dan argumen apa pun.
- Saat Anda menggunakan perintah dengan membalas pesan/tautan. jangan menambahkan argumen apa pun pada tautan Anda. masukkan argumen yang digunakan saat Anda memulai perintah dengan membalas pesan/tautan.
- **Contoh Opsi:** `opt: embedsubtitles:true|writesubtitles:true|allsubtitles:true`
![Preview](ytdlp-options.jpg)

Periksa semua opsi api YT-DLP dari [FILE ini](https://github.com/yt-dlp/yt-dlp/blob/master/yt_dlp/YoutubeDL.py#L184) atau gunakan skrip di bawah ini untuk mengonversi argumen cli menjadi opsi api.

```python
import sys

import yt_dlp

NO_DIFFERENCE = object()


def deep_diff(a, b):
    if not isinstance(b, type(a)):
        return b

    if isinstance(a, dict):
        assert isinstance(b, dict)
        result = {}
        for key, value in b.items():
            difference = deep_diff(a.get(key), value)
            if difference is not NO_DIFFERENCE:
                result[key] = difference

        return result if result else NO_DIFFERENCE

    if isinstance(a, (list, tuple)):
        assert isinstance(b, (list, tuple))
        result = [
            b_val for b_val in b
            if not any(deep_diff(a_val, b_val) is NO_DIFFERENCE for a_val in a)
        ]

        return type(a)(result) if result else NO_DIFFERENCE

    return b if a != b else NO_DIFFERENCE


def cli_to_api(options):
    default_options = yt_dlp.parse_options([]).ydl_opts
    parsed_options = yt_dlp.parse_options(options).ydl_opts

    diff = deep_diff(default_options, parsed_options)
    return {} if diff is NO_DIFFERENCE else diff

import pprint

try:
    pprint.pprint(cli_to_api(sys.argv[1:]))
except Exception as error:
    print(error)
    sys.exit(1)

sys.exit(0)
```

## 2. Rclone
**NOTE:** Fitur Rclone tidak aktif secara default, Jadi Anda harus kontak Admin untuk mengaktifkannya untuk Anda.

Untuk cara menggunakan fitur Rclone, Anda dapat melihat artikel mengenai Rclone [Disini](/p/rclone).

## 3. Leech Manager
### Send As Document
Untuk mengirim file menjadi Dokumen.
![Preview](send-as-document.jpg)

### Thumbnail
Untuk menambah Thumbnail pada file video.
![Preview](thumbnail.jpg)

### Leech Splits
Untuk membelah file.
![Preview](leech-splits.jpg)

### Leech Prefix
Untuk menambah Prefix pada nama file.
![Preview](leech-prefix-1.jpg)
![Preview](leech-prefix-2.jpg)

### Leech Suffix
Untuk kostumisasi caption pada file.
![Preview](leech-suffix.jpg)

### Mediainfo
Untuk mengaktifkan tombol Mediainfo dan membuat info file Anda.
![Preview](mediainfo.jpg)

### Media Spoiler
Untuk menyembunyikan Spoiler pada media.
![Preview](media-spoiler.jpg)

### Html Style
Untuk kostumisasi style caption.
![Preview](html-style-1.jpg)
![Preview](html-style-2.jpg)

### Saved Button
Untuk mengaktifkan tombol Save File dan menyimpan file di Bot PM.
![Preview](saved-button-1.jpg)
![Preview](saved-button-2.jpg)
