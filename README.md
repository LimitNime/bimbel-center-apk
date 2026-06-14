# Bimbel Center - Android App (WebView)

Project sederhana yang membungkus website https://bimbel-center.vercel.app/
menjadi aplikasi Android (.apk). Build APK dilakukan otomatis oleh GitHub
Actions, jadi tidak perlu install Android Studio.

## Cara pakai (semua lewat HP/browser, tanpa install apa-apa)

1. Buat akun GitHub kalau belum punya: https://github.com/signup
2. Buat repository baru:
   - Klik tombol "+" di pojok kanan atas -> "New repository"
   - Beri nama, misal: `bimbel-center-app`
   - Pilih "Public"
   - Klik "Create repository"
3. Upload semua file & folder di project ini ke repo tersebut:
   - Di halaman repo, klik "Add file" -> "Upload files"
   - Drag & drop SEMUA isi folder project ini (termasuk folder
     `.github`, `app`, dan file `build.gradle`, `settings.gradle`,
     `gradle.properties`) - pastikan struktur foldernya tetap terjaga
   - Klik "Commit changes"
4. Tunggu proses build otomatis:
   - Buka tab "Actions" di repo
   - Akan ada workflow "Build APK" yang sedang berjalan (ikon kuning
     berputar). Tunggu sampai jadi centang hijau (kira-kira 3-5 menit)
5. Download APK:
   - Klik workflow run yang sudah selesai (centang hijau)
   - Scroll ke bawah ke bagian "Artifacts"
   - Klik "bimbel-center-app" untuk download (berupa file .zip)
   - Extract file zip itu, di dalamnya ada `app-debug.apk`
6. Install ke HP:
   - Pindahkan app-debug.apk ke HP Android
   - Aktifkan "Install from unknown sources" / "Izinkan dari sumber ini"
     saat diminta
   - Install seperti biasa

## Mengganti URL website

Kalau alamat website berubah, edit file:
`app/src/main/java/com/bimbelcenter/app/MainActivity.kt`

Ganti baris:
```kotlin
private val siteUrl = "https://bimbel-center.vercel.app/"
```

Bisa diedit langsung di GitHub (klik file -> ikon pensil -> edit ->
commit). Setelah commit, GitHub Actions otomatis build ulang APK.

## Mengganti nama app

Edit file `app/src/main/res/values/strings.xml`, ganti nilai `app_name`.

## Kalau build gagal

Buka tab "Actions" -> klik run yang gagal (tanda silang merah) -> lihat
log error. Screenshot error tersebut dan tanyakan, nanti dibantu
perbaiki file yang bermasalah.
