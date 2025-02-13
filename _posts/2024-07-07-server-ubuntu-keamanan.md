---
layout: post
---


Mengamankan pengguna root di Ubuntu 20.04 adalah langkah penting untuk meningkatkan keamanan sistem. Berikut adalah beberapa langkah yang dapat Anda lakukan:

## 1. Nonaktifkan Login Root
Nonaktifkan akses login langsung ke akun root untuk mencegah pengguna lain mencoba login sebagai root. Biasanya, ini sudah dilakukan secara default pada instalasi Ubuntu, tetapi Anda dapat memeriksanya dengan cara berikut:

Edit file konfigurasi SSH:
sudo nano /etc/ssh/sshd_config

Cari baris berikut dan pastikan diatur seperti ini:

'''PermitRootLogin no'''
Simpan perubahan dan restart layanan SSH:
sudo systemctl restart sshd

## 2. Gunakan Sudo untuk Tugas Administratif
Gunakan perintah sudo untuk menjalankan tugas administratif. Tambahkan pengguna Anda ke grup sudo jika belum ada.

Tambahkan pengguna ke grup sudo:
sudo usermod -aG sudo username


Verifikasi akses sudo:
sudo whoami

Ini seharusnya mengembalikan "root" jika pengguna memiliki akses sudo.

## 3. Gunakan Kunci SSH untuk Otentikasi
Gunakan kunci SSH daripada kata sandi untuk otentikasi yang lebih aman.

Buat pasangan kunci SSH:

ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

Tambahkan kunci publik ke server:
ssh-copy-id username@server_ip

Nonaktifkan otentikasi kata sandi di SSH:
sudo nano /etc/ssh/sshd_config

Cari dan ubah baris berikut:

PasswordAuthentication no
Restart layanan SSH:

sudo systemctl restart sshd

## 4. Aktifkan Firewall (UFW)
Gunakan Uncomplicated Firewall (UFW) untuk mengelola akses jaringan.

Aktifkan UFW dan izinkan SSH:

sudo ufw allow OpenSSH
sudo ufw allow portsshbaru
sudo ufw enable
Periksa status UFW:


sudo ufw status
sudo netstat -tuln

## 5. Tetapkan Kata Sandi yang Kuat
Pastikan kata sandi root dan pengguna lain yang memiliki akses sudo sangat kuat.

Ganti kata sandi root:

sudo passwd root

Ganti kata sandi pengguna:
sudo passwd username

## 6. Terapkan Pembaruan Keamanan Secara Rutin
Selalu jaga agar sistem Anda tetap diperbarui dengan menginstal pembaruan keamanan terbaru.

Perbarui daftar paket dan instal pembaruan:

sudo apt update
sudo apt upgrade

Setel pembaruan otomatis:
Instal unattended-upgrades jika belum terpasang:

sudo apt install unattended-upgrades
Konfigurasi agar pembaruan otomatis:

sudo dpkg-reconfigure --priority=low unattended-upgrades

Dengan mengikuti langkah-langkah di atas, Anda dapat mengamankan akun root dan meningkatkan keamanan sistem Ubuntu 20.04 Anda.
