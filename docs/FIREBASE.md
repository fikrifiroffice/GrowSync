# Setup Firebase

GrowSync memakai **Firebase Realtime Database** sebagai penghubung antara aplikasi dan ESP32.

## 1. Buat project Firebase

1. Buka [Firebase Console](https://console.firebase.google.com) lalu **Add project**.
2. Tambahkan aplikasi **Android** dengan package name `com.growsync.greenhouse`.
3. Buat **Realtime Database** dan pilih lokasi terdekat (mis. `asia-southeast1`).
4. Unduh `google-services.json` dan **jangan** meng-commit file ini ke GitHub (sudah ada di `.gitignore`). Bentuk file ada di [`source/google-services.json.example`](../source/google-services.json.example).

## 2. Hubungkan ke Kodular

- Upload `google-services.json` milikmu ke bagian **Assets** project di Kodular.
- Pada komponen `fbRealtimeDatabse` (layar `Dashboard`), isi pengaturan Firebase sesuai project-mu.

## 3. Kunci data yang dipakai aplikasi

Aplikasi membaca dan menulis nilai berikut lewat komponen `fbRealtimeDatabse`. Firmware ESP32 harus memakai **nama kunci yang sama**.

| Kunci | Arah | Keterangan |
|---|---|---|
| `Suhu` | ESP32 → aplikasi | Suhu (°C) |
| `Udara` | ESP32 → aplikasi | Kelembapan udara (%) |
| `Tanah` | ESP32 → aplikasi | Kelembapan tanah (%) |
| `Cahaya` | ESP32 → aplikasi | Intensitas cahaya (%) |
| `SuhuSP` | aplikasi → ESP32 | Set point suhu |
| `TanahSP` | aplikasi → ESP32 | Set point kelembapan tanah |
| `CahayaSP` | aplikasi → ESP32 | Set point cahaya |
| `isAutoMode` | aplikasi → ESP32 | `true` = AUTO, `false` = MANUAL |
| `isPumpActive` | aplikasi → ESP32 | Perintah pompa (mode MANUAL) |
| `isFanActive` | aplikasi → ESP32 | Perintah kipas (mode MANUAL) |
| `isLampActive` | aplikasi → ESP32 | Perintah lampu (mode MANUAL) |

> Catatan: tipe data dan lokasi (tag/path) tepatnya mengikuti firmware ESP32 yang kamu pakai. Sesuaikan tabel ini dengan implementasi aslimu agar dokumentasi akurat.

## 4. Aturan keamanan (penting)

Jangan biarkan database dalam mode terbuka untuk publik. Minimal, batasi akses dengan aturan seperti berikut lalu perketat sesuai kebutuhan (mis. dengan Firebase Authentication):

```json
{
  "rules": {
    ".read": "auth != null",
    ".write": "auth != null"
  }
}
```

Jika aplikasi belum memakai login, kamu perlu menyesuaikan aturan ini (atau menambahkan autentikasi) agar tetap bisa berjalan, tetapi hindari `".read": true, ".write": true` pada database yang URL-nya publik.
