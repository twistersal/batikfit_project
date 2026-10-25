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

## Workout cards

Carousel workout dapat di-swipe horizontal. Pengguna dapat menambah kartu workout custom berisi nama, deskripsi, dan beberapa latihan; kartu tersimpan di `localStorage` dan dapat dihapus atau di-undo.

## Aksi tracker

Demo mendukung edit jadwal, tambah hari, tambah makanan, input kalori/protein/carbs/fats/air/langkah/catatan, hapus makanan, hapus tracker hari ini, dan **Undo terakhir**. Perubahan disimpan lokal di browser melalui `localStorage`.

Jadwal otomatis menyorot hari aktual berdasarkan tanggal perangkat, jadi ketika hari ini Kamis baris Kamis akan menjadi highlight.

Card pertama Ringkasan mengikuti hari aktual, shift, rutinitas, dan jam workout dari jadwal yang tersimpan.

Timeline dapat ditambah melalui tombol plus, diurutkan berdasarkan waktu, dan dapat di-hold untuk memilih Edit atau Hapus. Kebiasaan custom juga dapat ditambah melalui tombol plus.

Card header Jadwal dan Target Nutrisi menggunakan alignment inline; highlight hari diperlebar agar isi tidak tertekan.

Pada layar smartphone, mode calm mengurangi motif batik, border, shadow, nested card, dan padding agar konten tidak terasa bertumpuk.

Semua input numerik mendukung bilangan bulat dan desimal dengan `step="any"`, termasuk input nutrisi dan makanan.

Setelah setiap input, ringkasan langsung diperbarui dan aplikasi mengarahkan pengguna ke progress atau jadwal yang relevan.

Target Nutrisi dapat diklik untuk mengubah kalori, protein, karbohidrat, lemak, dan gula; progress menampilkan status to accomplish, Target accomplished, atau Warning, Overtarget detected.

Shift tersedia: P (09:00–17:00), LK2 (09:00–19:00), 11 (11:00–19:00), 12 (12:00–20:00), 12L (12:00–22:00), dan S (14:00–22:00). Pergantian tanggal mengarsipkan hari sebelumnya dan me-reset tracker harian.
