# Changelog

Format mengikuti [Keep a Changelog](https://keepachangelog.com/id/1.1.0/).

## [Belum dirilis]

### Ditambahkan
- **Panduan Penggunaan** (PDF, 11 halaman) di `docs/Panduan-Penggunaan-GrowSync.pdf`: langkah pemakaian dengan panah pada screenshot, logika AUTO bertoleransi, arti status koneksi, pemecahan masalah, dan penjelasan logo.
- Screenshot asli aplikasi di `docs/screenshots/` dengan nama yang deskriptif.

### Diubah
- Struktur dan penamaan file dirapikan: APK dipindah ke `release/GrowSync-v1.3.15.apk`, mockup desain dipisah ke `docs/mockup/`, logo vektor `..._color.svg` menjadi `..._warna.svg`, dan `docs/aset-pratinjau.png` menjadi `docs/pratinjau-aset-ui.png`.
- README diperbarui: status koneksi (Offline, Connecting..., Online, Error), alur set point terkunci (Setting lalu Simpan), perilaku perpindahan mode, serta aturan AUTO beserta toleransinya.

### Dihapus
- `docs/logo.png` (duplikat identik dari `assets/logo_app_icon_512.png`).

## [1.3.15] - 2026-11-08

### Ditambahkan
- Halaman **Proses**: monitoring suhu, kelembapan udara, kelembapan tanah, dan cahaya beserta nilai set point.
- Kontrol output **Pompa Air**, **Kipas**, dan **Lampu** dengan mode **AUTO / MANUAL**.
- Halaman **Setting**: pengaturan set point suhu, kelembapan tanah, dan cahaya dengan tombol +/− dan simpan.
- Indikator status koneksi (WiFi, Firebase, ESP32, Online) dan waktu update terakhir.
- Splash screen dan identitas visual GrowSync (logo, aset UI 3x).
