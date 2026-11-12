# Import dan Build di Kodular

## Import project

1. Masuk ke [creator.kodular.io](https://creator.kodular.io).
2. Klik **Import project (.aia)** lalu pilih `source/GrowSync.aia`.
3. Aset gambar ikut ter-import dari dalam `.aia`.

> `.aia` di repositori ini sudah **dibersihkan dari `google-services.json`**. Upload file milikmu sendiri setelah import (lihat [FIREBASE.md](FIREBASE.md)).

## Import per layar (opsional)

File `source/GrowSync_Screen1.ais` dan `source/GrowSync_Dashboard.ais` adalah export per layar. Impor lewat menu **Screens → Import screen** bila ingin memakai satu layar saja.

## Ekstensi yang dibutuhkan

Pastikan ekstensi berikut tersedia di project (sudah terbawa di `.aia`):

- KodularFirebaseDatabase
- KodularBottomNavigation
- MakeroidCardView
- MakeroidLinearProgressbar

## Build APK

1. Menu **Build → Android App (.apk)**.
2. Setelah selesai, unduh APK dan uji di perangkat Android 6.0 (API 23) atau lebih baru.
3. Untuk rilis, naikkan `VersionName` dan `VersionCode` lalu catat perubahan di [CHANGELOG.md](../CHANGELOG.md).

## Aset UI

Seluruh aset di folder [`assets/`](../assets) dibuat dalam kerapatan 3x. Pratinjau semuanya ada di [`docs/pratinjau-aset-ui.png`](pratinjau-aset-ui.png).

## Panduan pengguna

Cara memakai aplikasi (monitoring, mode AUTO/MANUAL, set point) dijelaskan lengkap dengan petunjuk panah di [`Panduan-Penggunaan-GrowSync.pdf`](Panduan-Penggunaan-GrowSync.pdf).
