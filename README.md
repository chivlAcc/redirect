# Proyek QR Code Dinamis Sederhana

Proyek ini menyediakan cara mudah dan gratis untuk membuat QR code dinamis menggunakan GitHub Pages. QR code yang dihasilkan akan mengarah ke URL statis, tetapi URL tujuan akhirnya bisa diubah kapan saja tanpa perlu membuat QR code baru.

## 🚀 Fitur Utama

  * **Gratis Sepenuhnya**: Tidak ada biaya tersembunyi atau biaya langganan.
  * **Dinamis**: Ubah URL tujuan kapan pun Anda mau hanya dengan mengedit satu file.
  * **Sederhana**: Menggunakan GitHub Pages dan JavaScript sederhana, tanpa perlu *backend* yang rumit.

## ⚙️ Cara Menggunakan

### 1\. Persiapan

1.  **Buat Repositori GitHub Baru**: Buat repositori baru untuk proyek ini.
2.  **Aktifkan GitHub Pages**:
      * Buka menu **`Settings`** di repositori Anda.
      * Pilih **`Pages`** di sidebar kiri.
      * Di bagian **`Source`**, pilih *branch* utama Anda (`main` atau `master`) dan klik **`Save`**.
      * GitHub Pages akan memberikan Anda URL publik, misalnya: `https://[nama-pengguna].github.io/[nama-repositori]`. Catat URL ini.

### 2\. Membuat Halaman Pengalihan

1.  Buat file baru di repositori Anda dengan nama **`index.html`** (atau nama lain yang Anda inginkan, misalnya `redirect.html`).

2.  Tambahkan kode berikut ke dalam file tersebut, lalu ganti `URL_TUJUAN_ANDA` dengan URL yang Anda inginkan (misalnya, `https://www.google.com`).

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>Redirecting...</title>
        <meta http-equiv="refresh" content="0; url=URL_TUJUAN_ANDA">
        <script>
            // Fallback JavaScript
            window.onload = function() {
                setTimeout(function() {
                    window.location.href = "URL_TUJUAN_ANDA";
                }, 1000);
            };
        </script>
    </head>
    <body>
        <p>Jika tidak dialihkan secara otomatis, silakan klik <a href="URL_TUJUAN_ANDA">tautan ini</a>.</p>
    </body>
    </html>
    ```

3.  *Commit* perubahan ini ke repositori Anda.

### 3\. Membuat QR Code

1.  Gunakan *library* Python `qrcode` (atau generator QR code online apa pun) untuk membuat QR code.
2.  Masukkan **URL GitHub Pages** yang sudah Anda dapatkan di langkah 1 sebagai data untuk QR code. Contohnya: `https://[nama-pengguna].github.io/[nama-repositori]/index.html`.
3.  Simpan QR code yang dihasilkan sebagai file gambar (`.png`, `.svg`, dll.). QR code ini **permanen**.

## 🔄 Cara Mengubah URL Tujuan

Untuk mengubah URL tujuan dari QR code yang sudah ada:

1.  Buka file `index.html` di repositori GitHub Anda.
2.  Edit URL di dalam tag `<meta>` dan `<script>` menjadi URL baru yang Anda inginkan.
3.  *Commit* perubahan.

Secara instan, setiap kali QR code Anda dipindai, pengguna akan diarahkan ke URL yang baru Anda tetapkan.

## ⚠️ Keterbatasan

  * Proyek ini **tidak memiliki fitur analitik atau pelacakan** (tracking) seperti jumlah pemindaian, lokasi, atau jenis perangkat.
  * Proses pengubahan URL membutuhkan *commit* ke repositori, yang kurang efisien dibandingkan dengan *dashboard* yang disediakan oleh layanan berbayar.
