Tugas Praktikum: Integrasi Notifikasi & API Perangkat Keras

Nama: Tsaqif Kanz Ahmad
Program Studi: Teknik Informatika
Kelas: IF-11-02

Gambaran Umum Aplikasi
Proyek ini merupakan sebuah aplikasi berbasis Flutter yang dirancang untuk mendemonstrasikan penggunaan fitur bawaan perangkat (kamera dan galeri) melalui implementasi package image_picker. Selain itu, aplikasi ini juga disematkan fitur pemberitahuan lokal menggunakan package flutter_local_notifications. Alur kerjanya cukup interaktif: setelah pengguna sukses menjepret foto atau memilih gambar dari galeri, antarmuka utama akan langsung memuat gambar tersebut, yang secara bersamaan akan memicu munculnya notifikasi lokal pada perangkat secara real-time.

Rincian Fungsi Widget
Scaffold: Merupakan fondasi atau struktur dasar dari halaman aplikasi yang bertugas menampung elemen-elemen visual utama seperti body dan bilah navigasi.

AppBar: Komponen navigasi atas yang menampilkan teks judul halaman, yakni "Notifikasi & Hardware API".

Center: Widget pembungkus yang berfungsi untuk menempatkan seluruh elemen yang ada di dalamnya (seperti layout utama) agar berada tepat di tengah-tengah layar.

Column: Berperan mengatur tata letak widget secara vertikal, menyusun area penampil gambar dan barisan tombol agar berurut dari atas ke bawah.

Image.file: Komponen visual yang bertugas membaca, memuat, dan menampilkan file gambar yang tersimpan di dalam memori lokal perangkat ke layar aplikasi.

Text: Berfungsi untuk menampilkan tulisan atau string statis. Biasanya dimanfaatkan sebagai label teks pada tombol atau sebagai pesan placeholder ketika pengguna belum memilih gambar.

SizedBox: Digunakan untuk menyisipkan ruang kosong atau jarak vertikal sebesar 40 piksel. Ini berguna untuk memisahkan area gambar dengan area tombol agar antarmuka tidak terlihat menumpuk.

Row: Mengatur tata letak komponen secara horizontal sehingga tombol "Kamera" dan "Galeri" dapat diletakkan rapi berdampingan dari kiri ke kanan.

ElevatedButton.icon: Komponen tombol bergaya Material Design yang memiliki efek timbul (bayangan), serta memungkinkan penggabungan ikon dan teks di dalam satu tombol.

Icon: Menampilkan simbol grafis (ikon bawaan Material) guna memberikan petunjuk visual yang intuitif pada tombol-tombol yang tersedia.

Konfigurasi Khusus & Troubleshooting
Untuk memastikan kompatibilitas dan kelancaran aplikasi pada sistem operasi Android modern, diterapkan beberapa penyesuaian teknis berikut:

Izin Notifikasi (Android 13+ / API 33): Terdapat penambahan pemanggilan fungsi requestNotificationsPermission() pada tahap inisialisasi di main.dart. Penyesuaian ini bertujuan untuk memicu pop-up dialog yang meminta persetujuan pengguna secara langsung (runtime permission) agar aplikasi diizinkan mengirimkan notifikasi pada saat pertama kali dibuka.

Dukungan Core Library Desugaring (Kotlin DSL): Agar plugin notifikasi dapat beroperasi dengan baik pada Gradle versi terbaru, fitur bawaan Java 8 harus didukung. Oleh karena itu, pengaturan isCoreLibraryDesugaringEnabled = true diaktifkan dan dependensi coreLibraryDesugaring ditambahkan secara manual ke dalam fail konfigurasi build.gradle.kts (level app).
