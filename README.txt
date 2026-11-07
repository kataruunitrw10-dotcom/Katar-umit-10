# Website Karang Taruna Gutama RW 10

## Isi
- `index.html` — website responsif (HTML, CSS, JavaScript) dalam satu file.
- Program unggulan, bagan struktur pengurus, galeri kegiatan, pengumuman.
- Panel admin: tambah/hapus kegiatan, upload foto, tambah/hapus pengumuman.
- Integrasi JSONBin.io API v3.

## Login demo awal
- Username: `admin`
- Password: `admi`

**Penting:** Login ini hanya pengunci tampilan sisi browser untuk demo. Kredensial ada di JavaScript dan bisa dilihat oleh siapa pun yang membuka source website. Jangan gunakan untuk data sensitif atau website produksi tanpa backend autentikasi.

## Menghubungkan JSONBin.io
1. Buat akun di https://jsonbin.io lalu buat satu Bin berisi JSON awal berikut:
   ```json
   {"activities":[],"announcements":[]}
   ```
2. Atur Bin menjadi **Public** jika pengunjung website perlu membaca data tanpa login. Jangan simpan data pribadi di Bin publik.
3. Buat **Access Key** khusus di JSONBin dengan izin membaca dan memperbarui Bin tersebut. Hindari memakai Master Key.
4. Buka website → Admin → login → tab **Database**.
5. Masukkan Bin ID dan Access Key, lalu klik **Simpan Konfigurasi** dan **Sinkronkan**.

Website menggunakan:
- GET `https://api.jsonbin.io/v3/b/{BIN_ID}/latest`
- PUT `https://api.jsonbin.io/v3/b/{BIN_ID}`
- Header `X-Access-Key` untuk akses yang diizinkan.

## Catatan keamanan penting
File HTML statis tidak dapat menyimpan rahasia dengan aman. Access Key yang dimasukkan di browser tersimpan di localStorage browser admin dan dapat diperiksa melalui developer tools. Untuk website publik/produksi, pindahkan proses update JSONBin ke backend/serverless function, simpan key sebagai environment secret, dan gunakan autentikasi admin di server.

## Foto
Foto diperkecil otomatis menjadi JPEG untuk membantu menekan ukuran JSON. Batas Bin gratis JSONBin yang didokumentasikan adalah 100 KB per record; karena itu unggahan foto dibatasi dan bisa cepat memenuhi kapasitas. Untuk galeri foto dalam jumlah banyak, gunakan layanan penyimpanan gambar (misalnya Cloudinary atau layanan object storage) dan simpan URL gambar di JSONBin.

## Susunan organisasi awal
Pelindung/Pembina (Ketua RW 10) → Ketua → Wakil Ketua, Sekretaris, Bendahara → Seksi Keamanan, Lingkungan, Sosial, Olahraga, Seni & Budaya.
Nama pengurus sengaja dikosongkan agar diisi setelah rapat pembentukan.
