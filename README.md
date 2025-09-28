# 🚀 Scraping Status Tiket Gunung Bromo & Semeru

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📋 Daftar Isi
- [Deskripsi](#deskripsi)
- [Fitur Utama](#fitur-utama)
- [Prasyarat](#prasyarat)
- [Instalasi](#instalasi)
- [Cara Penggunaan](#cara-penggunaan)
- [Cara Kerja](#cara-kerja)
- [Output](#output)
- [Catatan](#catatan)
- [Lisensi](#lisensi)

## 📖 Deskripsi
Proyek ini adalah notebook Jupyter yang digunakan untuk melakukan scraping data status kapasitas tiket masuk ke Gunung Bromo dan Semeru dari situs web resmi [bromotenggersemeru.id](https://bromotenggersemeru.id/). Script ini mengambil data kuota tiket untuk berbagai periode bulan dan tahun, kemudian menampilkannya dalam bentuk tabel menggunakan pandas.

## ✨ Fitur Utama
- 🌐 Mengambil opsi bulan/tahun yang tersedia dari halaman utama.
- 🔄 Melakukan iterasi melalui setiap periode untuk mengambil data kapasitas tiket via AJAX POST request.
- 📊 Scraping data tabel yang berisi tanggal dan status kuota (misalnya "Kuota Penuh" atau status lainnya).
- 📈 Mengumpulkan semua data ke dalam DataFrame pandas untuk analisis atau penyimpanan lebih lanjut.

## 🛠️ Prasyarat
- 🐍 Python 3.x
- 📓 Jupyter Notebook
- 📚 Library yang diperlukan:
  - `beautifulsoup4`
  - `requests`
  - `pandas`

## 📦 Instalasi
1. Pastikan Python dan Jupyter Notebook terinstal di sistem Anda.
2. Instal dependensi yang diperlukan dengan menjalankan perintah berikut di terminal atau dalam notebook:

   ```bash
   %pip install beautifulsoup4 requests pandas
   ```

## 🚀 Cara Penggunaan
1. Buka notebook `scraping_status_tiket_gunung_bromo&semeru.ipynb` di Jupyter Notebook.
2. Jalankan sel-sel secara berurutan:
   - **Sel pertama:** Instal dependensi.
   - **Sel kedua:** Mengatur URL target, headers, dan mengambil opsi bulan/tahun dari halaman awal.
   - **Sel ketiga:** Iterasi melalui setiap bulan, membuat POST request ke endpoint AJAX, dan scraping data tabel.
   - **Sel keempat:** Memproses dan menampilkan data yang dikumpulkan dalam DataFrame.
3. Data akan ditampilkan di output notebook. Anda dapat menyimpannya ke file CSV atau melakukan analisis lebih lanjut jika diperlukan.

## 🔧 Cara Kerja
- **Langkah 1:** Mengambil HTML halaman awal untuk menemukan opsi `year_month` dari dropdown form.
- **Langkah 2:** Ekstrak nilai-nilai opsi bulan/tahun.
- **Langkah 3-4:** Untuk setiap bulan, kirim POST request ke endpoint AJAX dengan payload yang sesuai, lalu parse HTML respons untuk mengambil data tabel (tanggal dan status).
- **Langkah 5:** Gabungkan semua data ke dalam DataFrame pandas dan tampilkan.
- Jika tidak ada data atau terjadi error, script akan memberikan pesan peringatan dan melanjutkan ke bulan berikutnya.

## 📊 Output
- Data ditampilkan dalam tabel dengan kolom: `Tanggal`, `Status`, `Periode`.
- Contoh status: "Kuota Penuh" (quota full), dll.
- Opsional: Analisis tambahan seperti jumlah hari kuota penuh per periode dapat ditambahkan.

## ⚠️ Catatan
- Script ini menggunakan headers untuk meniru permintaan browser. Jika situs web berubah, Anda mungkin perlu menyesuaikan headers atau payload.
- Pastikan untuk menghormati terms of service situs web dan tidak melakukan scraping berlebihan yang dapat membebani server.
- Untuk debugging, uncomment bagian print respons mentah jika diperlukan.

## 📄 Lisensi
Proyek ini dilisensikan di bawah [MIT License](LICENSE). Lihat file `LICENSE` untuk detail lebih lanjut.
