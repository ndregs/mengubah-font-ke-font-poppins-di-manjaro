# Mengubah Font Sistem ke Font Poppins di Manjaro

Tutorial ini akan memandu Anda untuk mengubah font sistem menjadi font Poppins di Manjaro Linux.

## Prasyarat

Pastikan Anda memiliki `git` dan `base-devel` terinstal di sistem Anda.

```bash
sudo pacman -S git base-devel
```
itu sebagai user root, kalau user non-root bisa pakai :
```bash
yay -S git base-devel
```
## Instalasi Font Poppins dari AUR (Arch Linux User Repository)
 1. Clone repository ttf-poppins dari AUR menggunakan `git` :

```bash
git clone https://aur.archlinux.org/ttf-poppins.git
cd ttf-poppins
```
  2. Build dan Install Paket
     
Jangan jalankan `makepkg` sebagai root, jalankan sebagai non-root

Jika Anda melihat pesan kesalahan berikut saat menjalankan `makepkg` :
```bash
==> ERROR: Running makepkg as root is not allowed as it can cause permanent,
catastrophic damage to your system.
```
Keluar dari mode root dengan menjalankan `exit` atau beralih ke pengguna non-root.
```bash
exit
cd /path/ke/ttf-poppins
````
Pastikan Anda berada di direktori yang benar dan jalankan perintah berikut:
```bash
makepkg -si
```
Jika Anda mendapat pesan kesalahan terkait izin:
```bash
==> ERROR: You do not have write permission for the directory $BUILDDIR (/home/user/dir/ttf-poppins).
```
Ubah izin direktori agar pengguna Anda memiliki akses tulis:
```bash
sudo chown -R $(whoami) /path/ke/ttf-poppins
````
Setelah itu, coba lagi perintah `makepkg -si` sebagai pengguna biasa (non-root).
```bash 
makepkg -si
```

## Verifikasi dan Penggunaan Font Poppins

Setelah instalasi selesai, Anda dapat memverifikasi apakah font Poppins telah terpasang dan mulai menggunakannya di sistem Anda.

1. **Verifikasi Font di Font Management**

   - Reboot sistem Anda untuk memastikan perubahan diterapkan dengan benar.
   - Setelah reboot, buka `Appearance & Style` -> `Text & Fonts` -> `Font Management`.
   - Gulir ke bawah dan cari font "Poppins". Jika font tersebut muncul di daftar, berarti instalasi berhasil.

2. **Mengubah Font Sistem ke Poppins**

   - Untuk mengubah font sistem menjadi Poppins, tetap berada di `Appearance & Style` -> `Text & Fonts`.
   - Pergi ke tab `Fonts`, lalu pilih `General`.
   - Ubah font ke "Poppins" untuk menerapkannya sebagai font umum di seluruh sistem.
   - Anda juga dapat memilih jenis font Poppins yang berbeda untuk penggunaan lain, seperti font monospace atau dokumen.

3. **Reboot untuk Menerapkan Perubahan**

   - Untuk memastikan perubahan font diterapkan secara penuh, ```reboot``` sistem Anda lagi. Anda dapat melakukannya melalui terminal dengan perintah:

```bash
reboot
```
