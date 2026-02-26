# My Apptest (Flutter Project)

Aplikasi ini adalah proyek Flutter baru yang bernama **my_apptest**. Dokumen ini berisi panduan lengkap tentang cara menginstal, menjalankan, dan membangun proyek ini baik di perangkat virtual (emulator) maupun di perangkat fisik (HP asli).

## 📋 Persyaratan Sistem

Sebelum memulai, pastikan komputer Anda telah memenuhi persyaratan berikut:
- **Flutter SDK**: Versi 3.10.8 atau yang lebih baru. ([Cara Install Flutter](https://docs.flutter.dev/get-started/install))
- **Dart SDK**: Sudah termasuk dalam instalasi Flutter.
- **IDE (Integrated Development Environment)**: Direkomendasikan menggunakan [Visual Studio Code](https://code.visualstudio.com/) atau [Android Studio](https://developer.android.com/studio).
- **Plugin IDE**: Pastikan Anda telah menginstal ekstensi/plugin Flutter dan Dart pada IDE yang Anda pilih.

## 🛠️ Cara Instalasi (Setup Awal)

1. Buka terminal atau command prompt.
2. Navigasikan ke direktori tempat Anda menyimpan proyek ini (jika Anda belum berada di dalamnya):
   ```bash
   cd path/to/my_apptest
   ```bash
   flutter pub get
   ```

## 🔄 Cara Melanjutkan Pekerjaan (Setelah Menutup Project)

Jika Anda sudah pernah membuka project ini, menutup VS Code/Android Studio, lalu ingin melanjutkannya di lain hari, berikut langkah-langkahnya:

1. Buka kembali aplikasi **VS Code** (atau **Android Studio**).
2. Pergi ke menu `File` > `Open Folder...` (atau `Open...`).
3. Cari dan pilih folder `my_apptest` (pastikan Anda memilih folder utama project, bukan sub-foldernya).
4. Buka terminal di dalam VS Code (tekan `Ctrl` + `` ` `` atau pilih menu `Terminal` > `New Terminal`).
5. Pastikan emulator Anda sudah menyala atau HP Android sudah tersambung (Anda bisa mengeceknya dengan melihat pojok kanan bawah VS Code atau mengetik `flutter devices` di terminal).
6. Jalankan perintah `flutter run` di terminal untuk mulai mengerjakan ulang aplikasi Anda.
7. Anda siap melanjutkan mengedit kode (terutama di `lib/main.dart`). Jangan lupa gunakan **Hot Reload** (tekan `r` di terminal atau tekan tombol petir/hot reload di VS Code) setiap kali menyimpan file agar perubahan langsung terlihat!

## 🌍 Cara Clone & Setup Project dari GitHub (Khusus Pemula)

Jika Anda ingin mengunduh ulang project ini dari GitHub ke komputer baru atau komputer teman Anda, ikuti langkah-langkah ini dari awal:

**1. Persiapan Awal (Hanya sekali di komputer baru):**
*   Komputer tersebut **wajib** sudah terinstall [Git](https://git-scm.com/downloads) dan [Flutter SDK](https://docs.flutter.dev/get-started/install). 
*   Komputer wajib terkoneksi internet.

**2. Download (Clone) Project:**
1. Buka Terminal atau Command Prompt (`cmd`) di komputer Anda.
2. Arahkan direktori (menggunakan perintah `cd`) ke tempat Anda ingin menyimpan project ini, contoh:
   ```bash
   cd Documents
   ```
3. Copy link repositori GitHub project ini (bisa didapatkan dengan menekan tombol hijau "Code" di GitHub, lalu copy URL `.git`).
4. Ketik perintah `git clone` diikuti dengan link tersebut. Contoh:
   ```bash
   git clone https://github.com/username-anda/my_apptest.git
   ```
5. Tunggu proses download hingga selesai.

**3. Setup Project (Sangat Penting!):**
Saat men-download dari GitHub, folder-folder bawaan dan dependensi tidak ikut ter-download (untuk menghemat ukuran file). Anda **wajib** melakukan setup dengan langkah berikut:

1. Masuk ke folder project yang baru saja didownload:
   ```bash
   cd my_apptest
   ```
2. Unduh ulang semua *package* (dependensi) yang diperlukan oleh project:
   ```bash
   flutter pub get
   ```
   *(Tunggu hingga proses selesai dan tidak ada error).*
3. Buka folder `my_apptest` tersebut di IDE Anda (VS Code/Android Studio).
4. Jalankan aplikasi seperti biasa dengan perintah `flutter run` (Pastikan emulator/HP sudah siap).

## 🚀 Cara Menjalankan Aplikasi

Flutter memungkinkan Anda menjalankan aplikasi di berbagai platform. Ikuti panduan di bawah ini sesuai dengan perangkat yang akan Anda gunakan.

### 1. Menjalankan di Emulator / HP Virtual (Android/iOS)

**Langkah-langkah:**
1. Buka Android Studio.
2. Pergi ke **Device Manager** (atau AVD Manager).
3. Buat emulator baru atau jalankan emulator yang sudah ada dengan mengklik ikon 'Play'.
   > *Catatan: Jika Anda menggunakan Mac dan ingin menjalankan di iOS simulator, buka terminal dan ketik `open -a Simulator`.*
4. Pastikan emulator sudah menyala dan siap digunakan.
5. Di terminal atau IDE Anda (VS Code/Android Studio), jalankan perintah:
   ```bash
   flutter run
   ```
6. Jika ada lebih dari satu perangkat yang terdeteksi, Flutter akan meminta Anda untuk memilih perangkat. Ketik nomor yang sesuai dengan emulator Anda.

### 2. Menjalankan di Perangkat Asli / HP Fisik (Android)

Untuk menjalankan langsung di HP Android Anda, Anda harus mengaktifkan **Developer Options (Opsi Pengembang)** dan **USB Debugging**.

**Langkah-langkah di HP Android Anda:**
1. Buka **Pengaturan (Settings)** > **Tentang Ponsel (About Phone)**.
2. Cari **Nomor Bentukan (Build Number)** dan ketuk 7 kali secara cepat hingga muncul notifikasi "Anda sekarang adalah seorang pengembang".
3. Kembali ke layar Pengaturan utama, buka menu **Sistem (System)** (atau Pengaturan Tambahan) > **Opsi Pengembang (Developer Options)**.
4. Aktifkan **Opsi Pengembang**, lalu scroll ke bawah dan aktifkan **Debugging USB (USB Debugging)**.

**Langkah-langkah di Komputer Anda:**
1. Hubungkan HP Anda ke komputer menggunakan kabel USB data yang baik.
2. Di layar HP Anda, mungkin akan muncul prompt konfirmasi *"Izinkan debugging USB?"*, pilih **Izinkan (Allow)**.
3. Buka terminal pada folder proyek ini, lalu pastikan perangkat Anda terdeteksi oleh Flutter dengan perintah:
   ```bash
   flutter devices
   ```
4. Jika perangkat Anda muncul dalam daftar, jalankan aplikasi dengan:
   ```bash
   flutter run
   ```

## 📁 Struktur Folder Proyek

Berikut adalah penjelasan singkat tentang struktur folder utama dalam proyek ini:

- `lib/` : **Ini adalah folder paling penting**. Semua kode program Dart (UI, logika) Anda berada di sini. File utama adalah `lib/main.dart`.
- `android/` : Berisi konfigurasi dan build spesifik untuk aplikasi native Android.
- `ios/` : Berisi konfigurasi dan build spesifik untuk aplikasi native iOS.
- `web/`, `linux/`, `macos/`, `windows/` : Berisi konfigurasi spesifik jika Anda ingin membangun aplikasi untuk web atau desktop.
- `pubspec.yaml` : File konfigurasi proyek tempat Anda mendaftarkan *package* (dependensi pihak ketiga), font, dan aset (gambar/ikon).

## 📦 Build untuk Produksi (Membuat file APK)

Jika Anda sudah selesai mengembangkan aplikasi dan ingin membagikan file instalasinya (.apk) kepada orang lain untuk diinstal di HP Android mereka, Anda bisa melakukan build rilis.

Jalankan perintah berikut di terminal:
```bash
flutter build apk --release
```

Jika proses build selesai dan berhasil, Anda dapat menemukan file `app-release.apk` di dalam folder:
`build/app/outputs/flutter-apk/app-release.apk`

---
Untuk bantuan lebih lanjut terkait pengembangan dengan Flutter, Anda bisa mengunjungi dokumentasi resminya:
- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Flutter Cookbook](https://docs.flutter.dev/cookbook)
- [Online Documentation](https://docs.flutter.dev/)
