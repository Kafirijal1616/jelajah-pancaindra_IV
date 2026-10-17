# Jelajah Pancaindra — Paket GitHub Pages

## Isi paket
- `index.html` — website utama.
- `backsound.mp3` — musik latar utama yang dipanggil melalui jalur relatif.

## Cara publikasi
1. Buat repositori GitHub baru bernama `jelajah-pancaindra` dan pilih **Public** jika menggunakan GitHub Free.
2. Unggah `index.html` dan `backsound.mp3` langsung ke root repositori (bukan di dalam folder tambahan).
3. Buka **Settings → Pages**.
4. Di **Build and deployment**, pilih **Deploy from a branch**.
5. Pilih branch `main` dan folder `/(root)`, kemudian tekan **Save**.
6. Tunggu proses deployment selesai. Tautan biasanya berbentuk `https://NAMA-GITHUB.github.io/jelajah-pancaindra/`.

## Periksa koneksi Google Sheets
- `index.html` saat ini berisi konfigurasi `window.JP_CONFIG.APPS_SCRIPT_URL`.
- Pastikan URL itu adalah URL Web App Apps Script terbaru yang aktif dan berakhiran `/exec`.
- Jika URL berubah setelah deployment, edit `index.html`, ganti hanya nilai `APPS_SCRIPT_URL`, simpan, lalu unggah ulang.
- Jalankan `setupSheets()` pada Apps Script terlebih dahulu dan pastikan eksekusinya berhasil.
- Setelah deployment, uji pendaftaran siswa. Pastikan data benar-benar muncul di spreadsheet. Jangan menganggap sukses jika hanya layar website yang lanjut.

## Jalur backsound
`index.html` mencari `backsound.mp3` di folder yang sama terlebih dahulu, lalu mencoba `assets/backsound.mp3`. Karena itu, letakkan `backsound.mp3` di root repositori sesuai paket.

## Catatan privasi
GitHub Pages akan membuat website tersedia secara publik. Jangan unggah data siswa asli, file spreadsheet berisi informasi pribadi, atau kredensial. Papan peringkat publik sebaiknya hanya menampilkan nama panggilan/inisial dan skor. URL Web App yang digunakan di frontend bukan password; amankan Apps Script dengan validasi input dan jangan menaruh rahasia pada HTML.

## Jika tidak berfungsi
- Jika halaman 404: pastikan nama file tepat `index.html` dan sudah berada di root repositori.
- Jika musik tidak muncul: pastikan file tepat bernama `backsound.mp3`, huruf besar/kecil sesuai, dan berada di root.
- Jika data tidak masuk ke Sheets: pastikan URL `/exec` dan deployment Apps Script terbaru benar, `setupSheets()` berhasil, serta akses spreadsheet diberikan ke akun yang menjalankan script.
- Sesudah mengganti file, tunggu deployment selesai lalu muat ulang paksa dengan `Ctrl + Shift + R`.
