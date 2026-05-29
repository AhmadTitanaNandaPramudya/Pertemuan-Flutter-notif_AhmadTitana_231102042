# 📱 Notifikasi & API Perangkat Keras (Flutter)

Aplikasi berbasis Flutter ini dirancang untuk mendemonstrasikan integrasi fitur bawaan perangkat keras (kamera dan galeri) sekaligus memicu notifikasi lokal secara *real-time*.

---

## 👤 Informasi Mahasiswa

- **Nama:** Ahmad Titana Nanda Pramudya
- **Program Studi:** Teknik Informatika
- **Kelas:** IF-11-02

---

## 📖 Gambaran Umum Aplikasi

Proyek ini memanfaatkan dua *package* utama:
1. `image_picker`: Untuk mengakses kamera dan memori lokal (galeri).
2. `flutter_local_notifications`: Untuk mengirimkan pemberitahuan lokal ke sistem Android.

**Alur Kerja:**
Pengguna menjepret foto atau memilih gambar dari galeri ➡️ Gambar dimuat secara dinamis di antarmuka utama ➡️ Aplikasi secara bersamaan memunculkan notifikasi lokal pada perangkat.

---

## 🧩 Rincian Fungsi Widget

Berikut adalah struktur penyusun antarmuka aplikasi ini:

| Komponen / *Widget* | Fungsi & Deskripsi |
| :--- | :--- |
| `Scaffold` | Fondasi utama halaman aplikasi yang menampung elemen-elemen visual dasar (seperti *body* dan bilah navigasi). |
| `AppBar` | Komponen navigasi atas yang menampilkan teks judul halaman: **"Notifikasi & Hardware API"**. |
| `Center` | *Widget* pembungkus untuk memastikan seluruh elemen di dalamnya berada tepat di tengah-tengah layar. |
| `Column` | Mengatur tata letak *widget* secara vertikal, menyusun area gambar dan barisan tombol berurut dari atas ke bawah. |
| `Image.file` | Komponen visual untuk membaca, memuat, dan menampilkan *file* gambar yang tersimpan di dalam memori perangkat ke layar. |
| `Text` | Menampilkan teks statis, dimanfaatkan sebagai label tombol atau pesan *placeholder* ketika gambar belum dipilih. |
| `SizedBox` | Menyisipkan ruang kosong atau jarak vertikal sebesar 40 piksel agar antarmuka tidak menumpuk antara area gambar dan tombol. |
| `Row` | Mengatur tata letak secara horizontal sehingga tombol "Kamera" dan "Galeri" diletakkan sejajar berdampingan. |
| `ElevatedButton.icon` | Tombol bergaya *Material Design* dengan efek timbul yang menggabungkan ikon dan teks di dalamnya. |
| `Icon` | Menampilkan simbol grafis (*Material Icons*) guna memberikan petunjuk visual yang intuitif pada tombol-tombol yang tersedia. |

---

## ⚙️ Konfigurasi Khusus & *Troubleshooting*

Untuk memastikan kelancaran aplikasi pada sistem operasi Android modern (khususnya Android 13 ke atas), beberapa penyesuaian teknis telah diterapkan pada *source code*:

### 1. Izin Notifikasi (Android 13+ / API 33)
> Memanggil fungsi `requestNotificationsPermission()` pada tahap inisialisasi di `main.dart`. Penyesuaian ini memicu *pop-up runtime permission* yang meminta persetujuan pengguna agar aplikasi diizinkan mengirimkan notifikasi saat pertama kali dijalankan.

### 2. Dukungan *Core Library Desugaring* (Kotlin DSL)
> Agar *plugin* notifikasi beroperasi maksimal pada Gradle versi terbaru (yang membutuhkan fitur bawaan Java 8), pengaturan `isCoreLibraryDesugaringEnabled = true` telah diaktifkan. Selain itu, dependensi `coreLibraryDesugaring` telah ditambahkan secara manual ke dalam fail konfigurasi `build.gradle.kts` (level *app*).

---
