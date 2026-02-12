# ANALISA DAN PERENCANAAN ALGORITMA
## IMPLEMENTASI ALGORITMA RUN LENGTH ENCODING PADA KOMPRESI DATA TABEL MAHASISAWA
## CARA KERJA
# Aplikasi Absensi Siswa dengan GUI (Tkinter)

Aplikasi ini adalah sistem untuk mencatat dan mengompres data absensi siswa menggunakan algoritma **Run-Length Encoding (RLE)**. Aplikasi ini dibangun dengan antarmuka grafis (GUI) menggunakan Tkinter, pustaka standar Python.

Sistem ini sekarang menggunakan 14 slot pertemuan tetap (P1 hingga P14) sebagai ganti tanggal dinamis. Data absensi disimpan secara persisten dalam file `data/attendance.json`, sehingga tidak akan hilang saat program ditutup.

## Fitur Utama

-   **Antarmuka Grafis (GUI): Aplikasi yang mudah digunakan dengan jendela, tabel, dan tombol.
-   **Manajemen Siswa**:
    -   Tambah Siswa: Menambah siswa baru dengan NIM dan Nama. Absensinya akan otomatis diinisialisasi 'h' (hadir) untuk ke-14 pertemuan.
    -   Hapus Siswa: Menghapus siswa yang dipilih dari tabel.
-   **Manajemen Absensi 14 Pertemuan:
    -   **Input Absensi Langsung di Tabel: Mengubah data absensi pada slot pertemuan tertentu dengan mengklik langsung (single-click) pada sel tabel yang ingin diedit.
-   Penyimpanan Persisten: Data disimpan dalam format JSON.
-   Migrasi Data Otomatis: Jika terdeteksi format data lama (berbasis tanggal), aplikasi akan mencoba migrasi. Perhatian: Data absensi lama akan direset ke 'h' untuk semua 14 pertemuan baru.
-   Tampilan Tabel Dinamis: Menampilkan rekap absensi dalam tabel yang bisa di-scroll, dengan kolom untuk setiap pertemuan (P1 - P14).
-   Analisis Kompresi RLE Interaktif: Memungkinkan pemilihan siswa untuk melihat analisis detail proses kompresi RLE data absensinya.

## Struktur Direktori

```
project/
│
├── src/
│   ├── main.py                 # Kode utama aplikasi GUI Tkinter
│   ├── algorithm.py            # Implementasi algoritma RLE
│   └── utils.py                # Fungsi untuk menyimpan dan memuat data
│
├── data/
│   └── attendance.json         # (Dibuat otomatis) File database absensi
│
├── tests/
│   └── test_algorithm.py       # Unit testing untuk algoritma RLE
│
├── README.md                   # Dokumentasi ini
└── requirements.txt            # (Kosong) Tidak ada dependensi eksternal
```

## Cara Menjalankan Aplikasi

Karena aplikasi ini menggunakan `tkinter` yang merupakan bagian dari Python, Anda tidak perlu menginstal dependensi apa pun.

Cukup jalankan file `main.py` menggunakan interpreter Python Anda:

```bash
python src/main.py
```

## Panduan Penggunaan Fitur

-   Tambah Siswa: Gunakan tombol "Tambah Siswa Baru" untuk menambahkan siswa dengan NIM dan Nama. Absensi akan otomatis 'h' untuk semua 14 pertemuan.
-   **Menghapus Siswa**:
    1.  Klik pada salah satu baris siswa di tabel untuk memilihnya.
    2.  Klik tombol "Hapus Siswa".
    3.  Konfirmasi penghapusan pada dialog yang muncul.
-   Mengedit Absensi Langsung di Tabel:
    1.  Cari sel absensi (misalnya, di kolom P1, P2, dst.) yang ingin Anda ubah di dalam tabel.
    2.  **Klik langsung (single-click) pada sel tersebut.
    3.  Sebuah kotak input akan muncul di atas sel. Masukkan status absensi yang baru (`h`, `s`, `i`, atau `a`).
    4.  Tekan `Enter` atau klik di luar kotak input, dan tabel akan otomatis diperbarui.
-   Lihat Data Kompresi: Klik tombol "Lihat Data Kompresi", lalu pilih siswa dari daftar untuk melihat detail analisis RLE.

## Kode Absensi

-   `h`: Hadir
-   `s`: Sakit
-   `i`: Izin
-   `a`: Alfa (Tanpa Keterangan)
