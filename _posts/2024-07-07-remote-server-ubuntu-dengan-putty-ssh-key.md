---
layout: post
---


Untuk login menggunakan SSH key dari Windows (dengan menggunakan Putty) ke server Ubuntu 20.04, berikut langkah-langkahnya:

## Generate SSH Key Pair di Windows:

Jika belum memiliki pasangan kunci SSH di Windows, Anda dapat menggunakan utilitas seperti PuTTYgen untuk menghasilkan kunci SSH.
Buka PuTTYgen, pilih tipe kunci RSA, lalu klik tombol "Generate". Ikuti instruksi untuk menggerakkan mouse untuk mengumpulkan entropi yang diperlukan.
Setelah selesai, simpan kunci privat (private key) dan kunci publik (public key).
Menambahkan Kunci Publik ke Server Ubuntu:

## Login ke server Ubuntu menggunakan password.
Pastikan direktori .ssh pada home directory Anda (jika belum ada, buat dengan mkdir ~/.ssh).
Salin isi dari kunci publik yang dihasilkan (biasanya dengan ekstensi .pub) ke file ~/.ssh/authorized_keys di server Ubuntu. Anda dapat melakukan ini dengan perintah:

echo "isi_kunci_publik_anda" >> ~/.ssh/authorized_keys
Pastikan untuk mengganti "isi_kunci_publik_anda" dengan konten kunci publik yang sebenarnya.
Konfigurasi SSH di Putty:

## Buka Putty dan masukkan alamat IP atau nama host dari server Ubuntu di bagian "Host Name".
Di sebelah kiri, navigasikan ke "Connection" -> "SSH" -> "Auth".
Klik tombol "Browse" di bagian "Private key file for authentication" dan pilih file kunci privat (private key) yang dihasilkan oleh PuTTYgen.
Kembali ke bagian "Session", beri nama sesi dan klik "Save" untuk menyimpan konfigurasi ini jika diperlukan.
Klik "Open" untuk memulai sesi SSH.
Masuk ke Server Menggunakan Kunci SSH:

Setelah koneksi berhasil didirikan, Anda akan diminta untuk autentikasi menggunakan kunci SSH. Tidak ada kata sandi yang diperlukan karena kunci SSH digunakan untuk otentikasi.
Dengan langkah-langkah di atas, Anda seharusnya dapat login ke server Ubuntu menggunakan kunci SSH dari Windows menggunakan Putty dengan lancar. Pastikan kunci publik telah disalin dengan benar ke authorized_keys di server Ubuntu dan kunci privat sudah dikonfigurasi di Putty.
