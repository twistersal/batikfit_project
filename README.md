# BatikFit — Personal Rhythm

BatikFit adalah fitness dan nutrition tracker personal dengan tampilan batik minimalis dark mode. Aplikasi ini berjalan sebagai **single-page static app** tanpa backend.

## File utama

`index.html` adalah entry point utama aplikasi. Cukup buka file tersebut di browser untuk menjalankan demo.

## Install sebagai aplikasi

Buka aplikasi melalui HTTPS (misalnya GitHub Pages), lalu pilih **Install app** atau **Tambahkan ke layar utama** dari menu browser. Service worker akan menyimpan shell aplikasi agar dapat dibuka kembali saat offline.

## Penyimpanan data

Semua input disimpan di `localStorage` browser:

- Checklist kebiasaan harian
- Langkah
- Kalori
- Protein
- Air
- Catatan harian

Tidak ada database, server, API key, atau dependensi eksternal. Data berada di browser/perangkat yang digunakan. Jika cache/site data browser dihapus, data lokal ikut terhapus.

## Jalankan lokal

Bisa langsung double-click `index.html`, atau gunakan server lokal:

```bash
python3 -m http.server 4173
```

Kemudian buka `http://localhost:4173`.

## Upload ke GitHub

1. Buat repository GitHub baru.
2. Upload `index.html` dan `README.md` ke root repository.
3. Untuk membuatnya menjadi website, aktifkan **Settings → Pages → Deploy from branch → main → /root**.
4. Untuk mengunduh aplikasinya, pilih **Code → Download ZIP** pada repository tersebut.

Karena aplikasi hanya terdiri dari file statis, hasil ZIP dapat dibuka dan dijalankan offline dengan membuka `index.html`.

## Catatan

Aplikasi ini adalah demo mandiri. Proyek BatikFit WebDev utama tetap terpisah dari folder ini.
