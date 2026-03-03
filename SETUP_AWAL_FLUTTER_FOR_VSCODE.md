# 🚀 SETUP AWAL FLUTTER & DART UNTUK VS CODE (WINDOWS)

> **Panduan LENGKAP dari NOL** — Cocok untuk yang **belum pernah install Flutter atau Dart sama sekali**.  
> Terakhir diperbarui: **26 Februari 2026**

---

## 📋 DAFTAR ISI

1. [Prasyarat (System Requirements)](#1--prasyarat-system-requirements)
2. [Install Git](#2--install-git)
3. [Install Visual Studio Code (VS Code)](#3--install-visual-studio-code-vs-code)
4. [Install Flutter SDK](#4--install-flutter-sdk)
5. [Setting Environment Variable (PATH)](#5--setting-environment-variable-path)
6. [Install Extension Flutter & Dart di VS Code](#6--install-extension-flutter--dart-di-vs-code)
7. [Install Android Studio (untuk Android SDK & Emulator)](#7--install-android-studio-untuk-android-sdk--emulator)
8. [Konfigurasi Android SDK & Accept Licenses](#8--konfigurasi-android-sdk--accept-licenses)
9. [Setup Emulator Android (AVD)](#9--setup-emulator-android-avd)
10. [Jalankan `flutter doctor` untuk Verifikasi](#10--jalankan-flutter-doctor-untuk-verifikasi)
11. [Membuat Project Flutter Pertama](#11--membuat-project-flutter-pertama)
12. [Menjalankan Aplikasi Flutter](#12--menjalankan-aplikasi-flutter)
13. [Troubleshooting & Masalah Umum](#13--troubleshooting--masalah-umum)
14. [Tips & Trik Tambahan](#14--tips--trik-tambahan)
15. [Menampilkan Layar HP ke Laptop (Screen Mirroring)](#15--menampilkan-layar-hp-ke-laptop-screen-mirroring)


---

## 1. 💻 Prasyarat (System Requirements)

Sebelum memulai, pastikan komputer kamu memenuhi syarat berikut:

| Kebutuhan               | Minimum                              |
| ------------------------ | ------------------------------------ |
| **Sistem Operasi**       | Windows 10 (64-bit) atau lebih baru  |
| **Disk Space**           | Minimal **2.5 GB** (belum termasuk Android Studio & emulator) |
| **RAM**                  | Minimal **8 GB** (disarankan 16 GB)  |
| **Prosesor**             | 64-bit (x86-64)                      |
| **Resolusi Layar**       | 1366 x 768 ke atas                   |

> [!IMPORTANT]
> Pastikan Windows kamu sudah **64-bit**. Flutter **tidak support** Windows 32-bit.

### Cara Cek Windows 64-bit:
1. Tekan **`Win + I`** → buka **Settings**
2. Pilih **System** → **About**
3. Lihat bagian **System type** — harus tertulis **64-bit operating system**

---

## 2. 📦 Install Git

Flutter membutuhkan **Git** untuk mengelola dependensi dan SDK-nya.

### Langkah-langkah:

1. **Download Git** dari situs resmi:  
   👉 [https://git-scm.com/download/win](https://git-scm.com/download/win)

2. **Jalankan installer** yang sudah didownload (`Git-x.xx.x-64-bit.exe`)

3. **Ikuti wizard instalasi** dengan pengaturan berikut:

   | Halaman Wizard                        | Pilihan yang Disarankan                     |
   | ------------------------------------- | ------------------------------------------- |
   | Select Components                     | Biarkan default, centang semua              |
   | Choosing the default editor           | Pilih **Use Visual Studio Code as Git's default editor** |
   | Adjusting your PATH environment       | Pilih **Git from the command line and also from 3rd-party software** (Recommended) |
   | Choosing HTTPS transport backend      | Pilih **Use the OpenSSL library**           |
   | Configuring the line ending conversions | Pilih **Checkout Windows-style, commit Unix-style line endings** |
   | Configuring the terminal emulator     | Pilih **Use Windows' default console window** |
   | Lainnya                               | Biarkan default, klik **Next** terus        |

4. Klik **Install** dan tunggu sampai selesai.

### Verifikasi Git:
Buka **Command Prompt** (tekan `Win + R`, ketik `cmd`, Enter) lalu jalankan:

```bash
git --version
```

Output yang diharapkan:
```
git version 2.xx.x.windows.x
```

> [!TIP]
> Jika `git --version` tidak dikenali, **restart Command Prompt** atau **restart komputer** dulu.

---

## 3. 🖥️ Install Visual Studio Code (VS Code)

### Langkah-langkah:

1. **Download VS Code** dari situs resmi:  
   👉 [https://code.visualstudio.com/download](https://code.visualstudio.com/download)  
   Pilih versi **Windows (User Installer, 64-bit)**

2. **Jalankan installer** (`VSCodeUserSetup-x64-x.xx.x.exe`)

3. **Pengaturan saat instalasi**:
   - ✅ Centang **"Add to PATH"** (PENTING!)
   - ✅ Centang **"Register Code as an editor for supported file types"**
   - ✅ Centang **"Add 'Open with Code' action to Windows Explorer file context menu"**
   - ✅ Centang **"Add 'Open with Code' action to Windows Explorer directory context menu"**

4. Klik **Install** → Tunggu selesai → Klik **Finish**

### Verifikasi VS Code:
Buka **Command Prompt** baru dan jalankan:

```bash
code --version
```

Output yang diharapkan:
```
1.xx.x
<hash>
x64
```

---

## 4. 📥 Install Flutter SDK

### Metode 1: Download Manual (DISARANKAN untuk pemula)

1. **Buka halaman download Flutter SDK**:  
   👉 [https://docs.flutter.dev/get-started/install/windows/mobile](https://docs.flutter.dev/get-started/install/windows/mobile)

2. Klik tombol **"Download Flutter SDK"** — file `.zip` akan terdownload.

3. **Buat folder tujuan** untuk menyimpan Flutter SDK.

   > [!CAUTION]
   > **JANGAN** simpan Flutter di lokasi berikut:
   > - `C:\Program Files\` (butuh admin permission)
   > - `C:\Program Files (x86)\`
   > - Folder yang path-nya mengandung **spasi** atau **karakter khusus**
   > - Di dalam folder **OneDrive**, **Google Drive**, atau cloud storage lainnya

   **Lokasi yang DISARANKAN:**
   ```
   C:\src\flutter
   ```
   atau
   ```
   C:\flutter
   ```
   atau
   ```
   D:\dev\flutter
   ```

4. **Buat folder** (jika belum ada):
   - Buka **File Explorer**
   - Masuk ke drive `C:\`
   - Klik kanan → **New** → **Folder** → beri nama `src`
   - Buka folder `src`

5. **Extract file ZIP Flutter** yang sudah didownload ke dalam folder `C:\src\`  
   Hasilnya akan menjadi: `C:\src\flutter\`

   Cara extract:
   - Klik kanan file `.zip`
   - Pilih **"Extract All..."**
   - Pilih destination: `C:\src\`
   - Klik **Extract**

### Metode 2: Clone via Git

Buka **Command Prompt** dan jalankan:

```bash
mkdir C:\src
cd C:\src
git clone https://github.com/flutter/flutter.git -b stable
```

> [!NOTE]
> Metode git clone akan mengunduh sekitar **1-2 GB** data. Pastikan koneksi internet stabil.

### Verifikasi Folder Flutter:

Pastikan struktur foldernya seperti ini:
```
C:\src\flutter\
├── bin\
│   ├── flutter          ← ini yang kita butuhkan
│   ├── flutter.bat
│   ├── dart
│   ├── dart.bat
│   └── ...
├── packages\
├── dev\
├── examples\
└── ...
```

---

## 5. 🔧 Setting Environment Variable (PATH)

Ini adalah langkah **PALING PENTING** agar perintah `flutter` dan `dart` bisa dikenali di mana saja lewat Command Prompt / Terminal.

### Langkah-langkah:

1. Tekan **`Win + S`** (atau klik Search di taskbar)
2. Ketik: **`environment variables`**
3. Klik **"Edit the system environment variables"**

   ![System Properties akan terbuka]

4. Di jendela **System Properties**, klik tombol **"Environment Variables..."** (di bagian bawah)

5. Di bagian **"User variables for [NamaUser]"** (bagian atas), cari variabel bernama **`Path`**, lalu **klik 2x** (double-click) untuk mengeditnya.

6. Klik **"New"** dan tambahkan path berikut:
   ```
   C:\src\flutter\bin
   ```
   
   > [!IMPORTANT]
   > Sesuaikan path di atas dengan lokasi folder Flutter SDK kamu.  
   > Misalnya jika kamu extract di `D:\dev\flutter`, maka path-nya: `D:\dev\flutter\bin`

7. Klik **OK** → **OK** → **OK** (tutup semua dialog)

### Verifikasi PATH:

**PENTING: Tutup SEMUA Command Prompt / Terminal yang sedang terbuka**, lalu buka **Command Prompt BARU**.

Jalankan perintah berikut:

```bash
flutter --version
```

Output yang diharapkan (contoh):
```
Flutter 3.xx.x • channel stable • https://github.com/flutter/flutter.git
Framework • revision xxxxxxx (x weeks ago) • 2026-xx-xx
Engine • revision xxxxxxx
Tools • Dart 3.x.x • DevTools 2.xx.x
```

Kemudian cek juga Dart:
```bash
dart --version
```

Output yang diharapkan:
```
Dart SDK version: 3.x.x (stable) ... on "windows_x64"
```

> [!WARNING]
> Jika perintah `flutter --version` **masih error** (not recognized):
> 1. Pastikan PATH sudah benar (cek ulang langkah di atas)
> 2. **Restart komputer** dan coba lagi
> 3. Pastikan di folder `C:\src\flutter\bin\` terdapat file `flutter.bat`

---

## 6. 🧩 Install Extension Flutter & Dart di VS Code

### Langkah-langkah:

1. **Buka VS Code**

2. Buka panel **Extensions** dengan cara:
   - Klik ikon **Extensions** di sidebar kiri (ikon kotak-kotak), **ATAU**
   - Tekan shortcut **`Ctrl + Shift + X`**

3. **Install extension berikut** (ketik di search bar, lalu klik **Install**):

   | No | Extension              | Publisher     | Keterangan                        |
   | -- | ---------------------- | ------------- | --------------------------------- |
   | 1  | **Flutter**            | Dart Code     | ⭐ WAJIB — extension utama Flutter |
   | 2  | **Dart**               | Dart Code     | ⭐ WAJIB — otomatis terinstall bersama Flutter |
   | 3  | **Flutter Widget Snippets** | Alexis Villegas | Opsional — snippet widget cepat  |
   | 4  | **Awesome Flutter Snippets** | Nash Ramdial | Opsional — snippet tambahan      |
   | 5  | **Error Lens**         | Alexander     | Opsional — tampilkan error inline |
   | 6  | **Bracket Pair Color DLW** | Built-in   | Opsional — warna bracket berpasangan |

4. Setelah install extension **Flutter**, VS Code akan otomatis mendeteksi Flutter SDK.  
   Jika diminta untuk locate SDK, arahkan ke: `C:\src\flutter`

### Verifikasi Extension:

1. Tekan **`Ctrl + Shift + P`** untuk membuka **Command Palette**
2. Ketik: **`Flutter: Run Flutter Doctor`**
3. Klik perintah tersebut — hasilnya akan muncul di panel **Output**

---

## 7. 📱 Install Android Studio (untuk Android SDK & Emulator)

> [!IMPORTANT]
> Meskipun kita akan coding di **VS Code**, kita tetap perlu **Android Studio** untuk:
> - **Android SDK** (tools untuk build aplikasi Android)
> - **Android Emulator** (simulasi HP Android di komputer)
> - **Command-line tools**

### Langkah-langkah:

1. **Download Android Studio** dari situs resmi:  
   👉 [https://developer.android.com/studio](https://developer.android.com/studio)  
   Klik **"Download Android Studio"** → Setujui Terms and Conditions

2. **Jalankan installer** (`android-studio-xxxx-windows.exe`)

3. **Ikuti wizard instalasi:**

   | Halaman Wizard             | Pilihan                                |
   | -------------------------- | -------------------------------------- |
   | Choose Components          | ✅ Centang **Android Studio** DAN **Android Virtual Device** |
   | Install Location           | Biarkan default atau pilih lokasi custom |
   | Start Menu Folder          | Biarkan default                        |

4. Klik **Install** → Tunggu selesai → Klik **Next** → **Finish**

5. **Buka Android Studio** untuk pertama kali:
   - Pilih **"Do not import settings"** → OK
   - Pilih **Standard** setup type → **Next**
   - Pilih UI theme (Darcula/Light) → **Next**
   - Android Studio akan mendownload komponen yang diperlukan:
     - ✅ Android SDK
     - ✅ Android SDK Command-line Tools
     - ✅ Android SDK Build-Tools
     - ✅ Android SDK Platform-Tools
     - ✅ Android Emulator
     - ✅ Intel HAXM (untuk akselerasi emulator) / Android Emulator Hypervisor Driver
   - Klik **Finish** dan tunggu download selesai (bisa memakan waktu **15-30 menit**)

> [!NOTE]
> Ukuran total download komponen Android Studio bisa mencapai **3-5 GB**.  
> Pastikan koneksi internet stabil dan disk space cukup.

---

## 8. ⚙️ Konfigurasi Android SDK & Accept Licenses

### 8.1 — Cek Lokasi Android SDK

Secara default, Android SDK terinstall di:
```
C:\Users\<NamaUser>\AppData\Local\Android\Sdk
```

Untuk mengecek atau mengubah lokasi:
1. Buka **Android Studio**
2. Klik **More Actions** (atau **Configure**) → **SDK Manager**
3. Di bagian atas, lihat **"Android SDK Location"**
4. Catat path-nya (misalnya: `C:\Users\MP2D3\AppData\Local\Android\Sdk`)

### 8.2 — Install SDK Components yang Diperlukan

Di **SDK Manager** (Android Studio → More Actions → SDK Manager):

**Tab: SDK Platforms**
- ✅ Centang versi Android terbaru (misalnya **Android 14.0 "UpsideDownCake"** / API 34)
- ✅ Boleh juga centang **Android 13.0 (Tiramisu)** / API 33

**Tab: SDK Tools**
Pastikan yang berikut ini tercentang dan terinstall:
- ✅ **Android SDK Build-Tools** (versi terbaru)
- ✅ **Android SDK Command-line Tools (latest)**
- ✅ **Android Emulator**
- ✅ **Android SDK Platform-Tools**

Klik **Apply** → **OK** dan tunggu download selesai.

### 8.3 — Accept Android Licenses

Buka **Command Prompt** (CMD) dan jalankan:

```bash
flutter doctor --android-licenses
```

Ketika diminta, ketik **`y`** lalu tekan **Enter** untuk setiap pertanyaan (biasanya ada 5-7 pertanyaan license).

```
Review licenses that have not been accepted (y/N)? y
...
Accept? (y/N): y
Accept? (y/N): y
Accept? (y/N): y
Accept? (y/N): y
Accept? (y/N): y
All SDK package licenses accepted.
```

> [!TIP]
> Jika muncul error **"Android sdkmanager not found"**, pastikan kamu sudah install **Android SDK Command-line Tools (latest)** di langkah 8.2.

---

## 9. 📲 Setup Emulator Android (AVD)

AVD = **Android Virtual Device** — ini adalah emulator HP Android di komputermu.

### Langkah-langkah:

1. Buka **Android Studio**
2. Klik **More Actions** → **Virtual Device Manager** (atau **Device Manager**)
3. Klik **"Create virtual device"**
4. **Pilih Device** (hardware profile):
   - Kategori: **Phone**
   - Disarankan: **Pixel 6** atau **Pixel 7** (resolusi bagus untuk testing)
   - Klik **Next**

5. **Pilih System Image**:
   - Pilih tab **Recommended**
   - Pilih versi terbaru, misalnya **UpsideDownCake (API 34)** atau yang sudah di-download
   - Jika belum terdownload, klik link **Download** di samping nama image
   - Tunggu download selesai (~1 GB)
   - Klik **Next**

6. **Konfigurasi AVD**:
   - **AVD Name**: biarkan default atau beri nama custom (misal: `Pixel_7_API_34`)
   - **Startup orientation**: Portrait
   - Klik **Show Advanced Settings** untuk atur RAM dan storage jika perlu
   - Klik **Finish**

7. **Jalankan Emulator** untuk test:
   - Di **Device Manager**, klik tombol ▶️ (**Play**) di samping emulator yang baru dibuat
   - Tunggu emulator booting (pertama kali bisa **3-5 menit**)
   - Jika emulator berhasil menampilkan home screen Android, berarti sudah siap! ✅

> [!WARNING]
> **Masalah umum dengan emulator:**
> - **HAXM / Hypervisor error**: Pastikan **Virtualization Technology (VT-x / AMD-V)** sudah **enabled** di BIOS komputer kamu.
> - **Emulator sangat lambat**: Pastikan HAXM atau **Windows Hypervisor Platform** sudah aktif.
>
> Cara aktifkan virtualisasi:
> 1. Restart komputer → masuk BIOS (tekan `Del`, `F2`, atau `F10` saat booting)
> 2. Cari pengaturan **Intel Virtualization Technology** atau **AMD-V** → **Enable**
> 3. Simpan dan restart

### Alternatif: Gunakan HP Android Fisik

Jika komputermu tidak kuat menjalankan emulator, kamu bisa menggunakan **HP Android fisik**:

1. Di HP Android, buka **Settings** → **About Phone**
2. Ketuk **Build Number** sebanyak **7 kali** sampai muncul "You are now a developer"
3. Kembali ke **Settings** → **Developer Options** (atau **System** → **Developer Options**)
4. Aktifkan:
   - ✅ **USB Debugging**
5. Sambungkan HP ke komputer via **kabel USB**
6. Di HP, ketika muncul popup **"Allow USB debugging?"** → klik **Allow** / **Izinkan**

Verifikasi:
```bash
flutter devices
```
HP kamu seharusnya muncul di daftar devices.

---

## 10. ✅ Jalankan `flutter doctor` untuk Verifikasi

Ini adalah langkah **PALING PENTING** untuk memastikan semua sudah terpasang dengan benar.

Buka **Command Prompt** dan jalankan:

```bash
flutter doctor -v
```

> Flag `-v` (verbose) akan memberikan informasi **lebih detail**.

### Output yang Diharapkan (Semua Hijau ✅):

```
Doctor summary (to see all details, run flutter doctor -v):
[✓] Flutter (Channel stable, 3.xx.x, on Microsoft Windows ...)
[✓] Windows Version (Installed version of Windows is version 10 or higher)
[✓] Android toolchain - develop for Android devices (Android SDK version 34.x.x)
[✓] Chrome - develop for the web
[✓] Visual Studio - develop Windows apps (opsional)
[✓] Android Studio (version 2024.x)
[✓] VS Code (version 1.xx.x)
[✓] Connected device (x available)
[✓] Network resources

• No issues found!
```

### Penjelasan Tiap Item:

| Item                  | Status | Arti                                     |
| --------------------- | ------ | ---------------------------------------- |
| Flutter               | ✅     | Flutter SDK terinstall dan terdeteksi     |
| Windows Version       | ✅     | Versi Windows memenuhi syarat             |
| Android toolchain     | ✅     | Android SDK & build tools siap            |
| Chrome                | ✅     | Browser Chrome terinstall (untuk web dev) |
| Visual Studio         | ❌/✅  | Opsional — hanya untuk Windows desktop app |
| Android Studio        | ✅     | Android Studio terdeteksi                 |
| VS Code               | ✅     | VS Code terdeteksi                        |
| Connected device      | ✅     | Ada device (emulator/HP) yang terhubung   |

> [!NOTE]
> **Visual Studio** (bukan VS Code!) berstatus ❌ itu **TIDAK MASALAH** jika kamu hanya membuat app Android/iOS.  
> Visual Studio (C++ build tools) hanya diperlukan untuk membuat **Windows desktop app**.

---

## 11. 🆕 Membuat Project Flutter Pertama

### Cara 1: Via Command Prompt (Terminal)

```bash
cd C:\Users\MP2D3\Documents\SEMESTER 6\app-mobile
flutter create nama_project_kamu
```

> [!CAUTION]
> Nama project harus:
> - **huruf kecil semua** (lowercase)
> - **tanpa spasi** — gunakan underscore `_`
> - **tanpa karakter khusus** — hanya huruf, angka, dan underscore
> - **tidak boleh diawali angka**
>
> ✅ Benar: `my_first_app`, `todo_app`, `calculator_app`  
> ❌ Salah: `My App`, `1st-app`, `app@home`

Contoh:
```bash
flutter create my_first_app
```

Output:
```
Creating project my_first_app...
Running "flutter pub get" in my_first_app...
...
All done!

In order to run your application, type:

  $ cd my_first_app
  $ flutter run

Your application code is in my_first_app\lib\main.dart.
```

### Cara 2: Via VS Code (Command Palette)

1. Buka **VS Code**
2. Tekan **`Ctrl + Shift + P`** untuk membuka **Command Palette**
3. Ketik: **`Flutter: New Project`**
4. Pilih **Application**
5. Pilih **folder lokasi** penyimpanan project
6. Masukkan **nama project** (huruf kecil, pakai underscore)
7. Tekan **Enter** — VS Code akan membuat project dan membukanya secara otomatis

### Struktur Project Flutter:

```
my_first_app/
├── android/          ← konfigurasi & kode native Android
├── ios/              ← konfigurasi & kode native iOS
├── lib/              ← ⭐ KODE UTAMA DART kamu di sini
│   └── main.dart     ← file utama yang dijalankan pertama
├── test/             ← unit test
├── web/              ← konfigurasi untuk web platform
├── pubspec.yaml      ← ⭐ file konfigurasi project & dependencies
├── pubspec.lock      ← lock file (jangan diedit manual)
├── README.md         ← dokumentasi project
└── analysis_options.yaml ← aturan linting Dart
```

> [!TIP]  
> File utama yang akan sering kamu edit:
> - `lib/main.dart` — kode utama aplikasi
> - `pubspec.yaml` — untuk menambah package/library

---

## 12. ▶️ Menjalankan Aplikasi Flutter

### Cara 1: Via Terminal

```bash
cd my_first_app
flutter run
```

Jika ada beberapa device yang terhubung, pilih salah satu:
```bash
flutter run -d chrome       # jalankan di Chrome (web)
flutter run -d emulator     # jalankan di emulator Android
flutter run -d <device_id>  # jalankan di device tertentu
```

Untuk melihat daftar device yang tersedia:
```bash
flutter devices
```

### Cara 2: Via VS Code (DISARANKAN)

1. Buka project Flutter di VS Code
2. Buka file `lib/main.dart`
3. **Pilih device** di pojok kanan bawah VS Code (status bar):
   - Klik nama device yang muncul
   - Pilih emulator atau device yang ingin digunakan
4. Tekan **`F5`** atau klik **Run → Start Debugging**
5. Atau tekan **`Ctrl + F5`** untuk **Run Without Debugging** (lebih cepat)

### Hot Reload & Hot Restart:

| Fitur          | Shortcut    | Fungsi                                          |
| -------------- | ----------- | ----------------------------------------------- |
| **Hot Reload** | **`Ctrl+S`** (save file) atau **`r`** di terminal | Update UI tanpa restart, state tetap terjaga |
| **Hot Restart** | **`Shift + R`** di terminal atau **`Ctrl+Shift+F5`** di VS Code | Restart app dari awal, state di-reset |
| **Stop**       | **`q`** di terminal atau **`Shift+F5`** di VS Code | Menghentikan aplikasi |

> [!TIP]
> **Hot Reload** adalah fitur paling keren Flutter! Kamu bisa langsung lihat perubahan UI **dalam hitungan detik** tanpa perlu rebuild seluruh aplikasi.

---

## 13. 🛠️ Troubleshooting & Masalah Umum

### ❌ Problem 1: `flutter` is not recognized

**Penyebab:** PATH belum di-set dengan benar.

**Solusi:**
1. Buka **Environment Variables** (lihat [Langkah 5](#5--setting-environment-variable-path))
2. Pastikan `C:\src\flutter\bin` ada di variabel **Path** (User variables)
3. **Restart Command Prompt** (tutup dan buka lagi)
4. Jika masih gagal, **restart komputer**

---

### ❌ Problem 2: `Android SDK not found` atau `Unable to locate Android SDK`

**Solusi:**
1. Pastikan Android Studio sudah diinstall dan SDK sudah di-download
2. Set Android SDK path secara manual:

```bash
flutter config --android-sdk "C:\Users\<NamaUser>\AppData\Local\Android\Sdk"
```

Ganti `<NamaUser>` dengan username Windows kamu.

---

### ❌ Problem 3: `Android license status unknown` atau `Some Android licenses not accepted`

**Solusi:**
```bash
flutter doctor --android-licenses
```
Ketik `y` untuk semua pertanyaan.

Jika masih error:
```bash
cd C:\Users\<NamaUser>\AppData\Local\Android\Sdk\cmdline-tools\latest\bin
sdkmanager --licenses
```

---

### ❌ Problem 4: `cmdline-tools component is missing`

**Solusi:**
1. Buka **Android Studio** → **SDK Manager**
2. Tab **SDK Tools**
3. Centang ✅ **Android SDK Command-line Tools (latest)**
4. Klik **Apply** → Download

---

### ❌ Problem 5: Emulator tidak bisa jalan / error HAXM

**Solusi:**
1. Pastikan **Virtualization** sudah di-enable di BIOS
2. Buka **Control Panel** → **Programs** → **Turn Windows features on or off**
3. Centang:
   - ✅ **Hyper-V** (jika tersedia)
   - ✅ **Windows Hypervisor Platform**
4. Restart komputer

Alternatif: install **HAXM** manual dari Android Studio → SDK Manager → SDK Tools → ✅ Intel x86 Emulator Accelerator (HAXM installer)

---

### ❌ Problem 6: `Waiting for another flutter command to release the startup lock`

**Solusi:**
1. Tutup semua terminal/CMD
2. Hapus file lock:
```bash
del C:\src\flutter\bin\cache\lockfile
```
3. Jalankan ulang perintah flutter

---

### ❌ Problem 7: VS Code tidak mendeteksi Flutter SDK

**Solusi:**
1. Tekan **`Ctrl + Shift + P`**
2. Ketik: **`Flutter: Change SDK`**
3. Arahkan ke folder Flutter SDK: `C:\src\flutter`

Atau tambahkan setting di VS Code:
1. Buka **Settings** (`Ctrl + ,`)
2. Cari: **`dart.flutterSdkPath`**
3. Isi dengan: `C:\src\flutter`

Atau edit file `settings.json` di VS Code:
```json
{
    "dart.flutterSdkPath": "C:\\src\\flutter",
    "dart.sdkPath": "C:\\src\\flutter\\bin\\cache\\dart-sdk"
}
```

---

### ❌ Problem 8: `Pub get failed` atau dependency error

**Solusi:**
```bash
flutter clean
flutter pub get
```

Jika masih gagal:
```bash
flutter pub cache repair
```

---

## 14. 💡 Tips & Trik Tambahan

### 🔄 Update Flutter ke Versi Terbaru
```bash
flutter upgrade
```

### 📊 Cek Channel Flutter
```bash
flutter channel
```
Untuk switch channel:
```bash
flutter channel stable    # paling stabil, DISARANKAN
flutter channel beta      # fitur baru, mungkin ada bug
flutter channel master    # bleeding edge, TIDAK disarankan untuk production
```

### 🧹 Bersihkan Cache Flutter
```bash
flutter clean
flutter pub get
```

### 📦 Menambah Package/Library
```bash
flutter pub add nama_package
```
Contoh:
```bash
flutter pub add http              # untuk HTTP request
flutter pub add provider          # untuk state management
flutter pub add shared_preferences # untuk penyimpanan lokal
```

### 🔍 Keyboard Shortcuts VS Code untuk Flutter

| Shortcut                | Fungsi                                |
| ----------------------- | ------------------------------------- |
| `Ctrl + Shift + P`      | Command Palette                       |
| `F5`                    | Start Debugging                       |
| `Ctrl + F5`             | Run Without Debugging                 |
| `Ctrl + S`              | Save (trigger Hot Reload)             |
| `Ctrl + Shift + F5`     | Hot Restart                           |
| `Shift + F5`            | Stop debugging                        |
| `Ctrl + .`              | Quick Fix / Wrap Widget               |
| `Ctrl + Space`          | Autocomplete                          |
| `F2`                    | Rename symbol                         |
| `F12`                   | Go to Definition                      |
| `Alt + Shift + F`       | Format Document                       |
| `Ctrl + Shift + R`      | Refactor                              |

### 🎯 Widget Wrapping Shortcut

Di VS Code, untuk membungkus widget dengan widget lain:
1. Letakkan cursor di nama widget
2. Tekan **`Ctrl + .`**
3. Pilih:
   - **Wrap with Center**
   - **Wrap with Container**
   - **Wrap with Column**
   - **Wrap with Row**
   - **Wrap with Padding**
   - dll.

---

---

## 15. 🖥️ Menampilkan Layar HP ke Laptop (Screen Mirroring)

Jika kamu menggunakan **HP fisik** dan ingin menampilkan layarnya di laptop agar mudah saat demo atau coding, cara terbaik adalah menggunakan **scrcpy**.

### Langkah-langkah:

1. **Download scrcpy** (Screen Copy):
   👉 [https://github.com/Genymobile/scrcpy/releases](https://github.com/Genymobile/scrcpy/releases)
   Pilih versi Windows (misal: `scrcpy-win64-vX.X.zip`)

2. **Extract file ZIP** tersebut ke folder pilihanmu (misal: `C:\scrcpy`)

3. **Pastikan USB Debugging Aktif** di HP kamu (sudah dijelaskan di [Bagian 9](#alternatif-gunakan-hp-android-fisik))

4. **Hubungkan HP ke Laptop** via USB.

5. **Jalankan scrcpy**:
   - Buka folder `C:\scrcpy`
   - Klik 2x pada file `scrcpy.exe`
   - Layar HP kamu akan muncul di laptop! 🚀

> [!TIP]
> Agar lebih mudah, kamu bisa menambahkan folder `C:\scrcpy` ke **Environment Variables (PATH)** (sama seperti cara di [Langkah 5](#5--setting-environment-variable-path)). 
> Setelah itu, kamu cukup ketik `scrcpy` di Command Prompt mana saja untuk menampilkan layar.

---

## 📝 Checklist Setup


Gunakan checklist ini untuk memastikan semua langkah sudah dilakukan:

- [ ] ✅ Windows 64-bit
- [ ] ✅ Git terinstall → `git --version` berhasil
- [ ] ✅ VS Code terinstall → `code --version` berhasil
- [ ] ✅ Flutter SDK di-extract → `C:\src\flutter\`
- [ ] ✅ PATH di-set → `flutter --version` berhasil
- [ ] ✅ Extension Flutter & Dart terinstall di VS Code
- [ ] ✅ Android Studio terinstall
- [ ] ✅ Android SDK terdownload
- [ ] ✅ Android SDK Command-line Tools terinstall
- [ ] ✅ License diterima → `flutter doctor --android-licenses`
- [ ] ✅ Emulator dibuat dan bisa jalan (atau HP fisik terhubung)
- [ ] ✅ `flutter doctor` semua hijau (✓)
- [ ] ✅ Project pertama berhasil dibuat → `flutter create`
- [ ] ✅ App pertama berhasil dirun → `flutter run`

---

## 🎉 Selamat!

Jika semua checklist di atas sudah tercentang, berarti kamu sudah **siap 100%** untuk mulai belajar dan membangun aplikasi dengan **Flutter & Dart** menggunakan **VS Code**! 🚀

### Langkah Selanjutnya:
1. 📖 Pelajari dasar-dasar **Dart** → [dart.dev/language](https://dart.dev/language)
2. 📖 Pelajari dasar-dasar **Flutter Widget** → [docs.flutter.dev/ui/widgets](https://docs.flutter.dev/ui/widgets)
3. 🎓 Ikuti **Flutter Codelabs** → [codelabs.developers.google.com](https://codelabs.developers.google.com/?cat=Flutter)
4. 📦 Cari package di → [pub.dev](https://pub.dev)
5. 💬 Gabung komunitas Flutter Indonesia!

---

> **Dibuat dengan ❤️ sebagai panduan untuk pemula Flutter.**  
> Jika ada pertanyaan atau error, jalankan `flutter doctor -v` dan bagikan outputnya.
