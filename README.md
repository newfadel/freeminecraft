# mineCRACK

## Deskripsi
MineCRACK adalah aplikasi konsol yang ditulis dalam VB.NET untuk mengganti file sistem tertentu (`Windows.ApplicationModel.Store.dll`) di direktori `System32` dan `SysWOW64` pada sistem operasi Windows. Aplikasi ini dapat mengunduh file pengganti dari GitHub, membuat cadangan file sistem asli, dan memungkinkan pengguna untuk memulihkan file dari cadangan jika diperlukan. Aplikasi ini menggunakan hak akses administratif untuk mengelola file sistem yang terkunci dan mengatur kepemilikan file.

**Peringatan**: Mengganti file sistem dapat menyebabkan ketidakstabilan sistem atau masalah keamanan. Gunakan dengan hati-hati dan pastikan Anda memahami risikonya.

## Fitur
- Mengunduh file pengganti dari URL GitHub.
- Membuat cadangan file sistem asli sebelum penggantian.
- Mengganti file sistem di `System32` dan `SysWOW64`.
- Memungkinkan pemulihan file dari cadangan.
- Menampilkan antarmuka konsol dengan ASCII art dan log berwarna.
- Mengelola file yang terkunci menggunakan API tingkat rendah.

## Teknologi
- **Bahasa Pemrograman**: VB.NET
- **Framework**: .NET Framework
- **P/Invoke**: Untuk memanggil fungsi Windows API (kernel32.dll, user32.dll, advapi32.dll) guna mengelola file sistem dan hak akses.
- **HTTP Client**: Untuk mengunduh file dari GitHub.
- **Sistem Operasi**: Windows (diuji pada Windows 10/11).

## Persyaratan
Untuk menjalankan aplikasi ini, Anda memerlukan:
1. **Sistem Operasi**: Windows (64-bit direkomendasikan).
2. **.NET Framework**: Versi 4.5 atau lebih tinggi.
3. **Hak Akses Administrator**: Aplikasi harus dijalankan dengan hak administratif untuk mengakses dan mengganti file sistem.
4. **Koneksi Internet**: Diperlukan untuk mengunduh file pengganti dari GitHub jika file tidak tersedia secara lokal.
5. **Visual Studio** atau kompiler VB.NET lain untuk membangun proyek.

## Cara Menggunakan
1. **Kompilasi Kode**:
   - Buka proyek di Visual Studio atau lingkungan pengembangan VB.NET lainnya.
   - Bangun solusi untuk menghasilkan file executable.

2. **Jalankan Aplikasi**:
   - Klik kanan pada file executable dan pilih "Run as Administrator".
   - Pastikan koneksi internet tersedia jika file pengganti perlu diunduh.

3. **Ikuti Petunjuk di Konsol**:
   - Jika cadangan ditemukan, Anda akan diminta untuk memilih apakah ingin memulihkan file (Y/N).
   - Jika tidak ada cadangan, Anda akan diminta untuk mengganti file sistem (Y/N).
   - Aplikasi akan mencadangkan file asli sebelum penggantian dan mencatat status operasi.

4. **Periksa Log**:
   - Log ditampilkan di konsol dengan warna berbeda untuk informasi, keberhasilan, peringatan, atau kesalahan.

## Struktur Direktori
Setelah menjalankan aplikasi, direktori berikut akan dibuat (jika belum ada):
```
MineCRACK/
├── System32/
│   └── Windows.ApplicationModel.Store.dll  (file pengganti untuk System32)
├── SysWOW64/
│   └── Windows.ApplicationModel.Store.dll  (file pengganti untuk SysWOW64)
├── backup/
│   ├── System32/
│   │   └── Windows.ApplicationModel.Store.dll  (cadangan file asli System32)
│   └── SysWOW64/
│       └── Windows.ApplicationModel.Store.dll  (cadangan file asli SysWOW64)
```

## Catatan Penting
- **Cadangan Otomatis**: Aplikasi secara otomatis membuat cadangan file sistem asli sebelum penggantian.
- **Keamanan**: Pastikan file pengganti dari sumber terpercaya, karena mengganti file sistem dengan file yang tidak sah dapat membahayakan sistem.
- **Hak Akses**: Aplikasi menggunakan hak `SeTakeOwnershipPrivilege` dan `SeRestorePrivilege` untuk mengelola file sistem.
- **Kegagalan Operasi**: Jika terjadi kegagalan (misalnya, file terkunci atau izin ditolak), aplikasi akan mencatat kesalahan dan membatalkan operasi.

## Kontribusi
Jika Anda ingin berkontribusi:
1. Fork repositori ini.
2. Buat branch baru untuk fitur atau perbaikan bug.
3. Kirim pull request dengan deskripsi perubahan.

## Lisensi
Proyek ini dilisensikan di bawah [MIT License](LICENSE).

## Peringatan
Pengguna bertanggung jawab penuh atas penggunaan aplikasi ini. Pengembang tidak bertanggung jawab atas kerusakan sistem atau kehilangan data yang disebabkan oleh penggunaan aplikasi ini.
