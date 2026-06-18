# 💸 Cash Opname Solver

Sebuah aplikasi web kalkulator minimalis berdesain **Neo-Brutalist** yang dirancang khusus untuk membantu kasir atau operator menyeimbangkan pencatatan kasbon (Dana Virtual vs Uang Fisik) tanpa pusing memikirkan rumus akuntansi.

![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)

## 📌 Latar Belakang Masalah

Ketika seorang karyawan meminjam kasbon baru sambil mengembalikan sisa kasbon lama, sering terjadi kebingungan saat mencatat di sistem (POS/ERP), terutama terkait fitur pop-up **Cash Opname**.

**Use Case:**

- Pengembalian kasbon lama: **Rp 20.000.000** (Uang masih dipegang peminjam, fisik tidak ada di laci).
- Peminjam melaporkan pengeluaran rill: **Rp 8.460.000**.
- Peminjam meminta kasbon baru: **Rp 100.000.000**.

Secara logika nyata, operator hanya perlu menyerahkan uang fisik sebesar **Rp 88.460.000** dari laci. Namun, sistem meminta pencatatan terpisah di 3 pop-up berbeda. Jika salah input, saldo fisik di laci dan sistem akan selisih.

## 🚀 Solusi

Aplikasi ini secara otomatis memecah nominal transaksi ke dalam porsi **Dana Virtual (Transit)** dan **Uang Fisik**, sehingga:

1. Uang fisik di laci dipastikan akurat dan cocok.
2. Saldo Dana Virtual pada akhirnya akan kembali menjadi **Nol (0)** (saling menghapus).
3. Operator cukup menyalin angka (copy-paste / ketik ulang) sesuai panduan warna di layar ke dalam sistem utama.

## ✨ Fitur Unggulan

- **Auto-Formatting:** Otomatis menambahkan titik ribuan (misal `100.000.000`) saat mengetik secara _real-time_.
- **Live Calculation:** Hasil langsung muncul tanpa perlu menekan tombol "Hitung".
- **Compact UI:** Didesain padat (_anti-scroll_) agar muat di layar monitor kasir / admin berukuran kecil.
- **Neo-Brutalism Design:** Tampilan mencolok, kontras tinggi, dan instruksi to-the-point sehingga meminimalisir _human-error_.
- **100% Client Side:** Hanya membutuhkan satu file HTML tanpa backend. Sangat ringan dan cepat.

## 📖 Cara Penggunaan untuk Operator

1. Buka aplikasi/link web.
2. Masukkan nilai **Kasbon Lama** pada kolom 1.
3. Masukkan nilai **Pengeluaran Rill** pada kolom 2.
4. Masukkan nilai **Kasbon Baru** pada kolom 3.
5. Ambil uang dari laci sebesar nilai yang tertera di kotak biru muda (**UANG FISIK KELUAR**).
6. Saat pop-up sistem kasir muncul, cukup masukkan angka sesuai dengan instruksi yang tertera di layar (Pop-up 1, Pop-up 2, dan Pop-up 3).

## 🛠️ Deployment (GitHub Pages)

Repositori ini sudah dilengkapi dengan **GitHub Actions**. Setiap kali ada perubahan (_push_) pada branch `main`, aplikasi akan otomatis di-_deploy_ secara _live_ ke GitHub Pages.

**Struktur File:**

```text
/
├── index.html                  # Core application (UI & Logic)
├── README.md                   # Dokumentasi
└── .github/workflows/
    └── deploy.yml              # Skrip CI/CD GitHub Actions
```
