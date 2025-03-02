---
title: Linux Commands Cheat Sheet
tags: [Linux]
style: fill
color: info
description: This is a Basic Linux Command Cheatsheet offering a quick reference for common Linux commands. It covers tasks like file management, navigation, process management, networking, and more, making it useful for developers, system administrators, or anyone working with Linux systems.
---

# Linux Command Cheatsheet Dasar

## 1. Navigasi File dan Direktori

| Perintah         | Deskripsi                                |
|------------------|------------------------------------------|
| `pwd`            | Menampilkan direktori saat ini           |
| `ls`             | Menampilkan isi direktori                |
| `ls -l`          | Menampilkan detail file/direktori        |
| `ls -a`          | Menampilkan semua file termasuk hidden (.) |
| `cd <direktori>` | Pindah ke direktori tertentu             |
| `cd ..`          | Kembali ke direktori sebelumnya         |
| `cd ~`           | Pindah ke home directory                 |
| `cd -`           | Kembali ke direktori sebelumnya          |

---

## 2. Manipulasi File dan Direktori

| Perintah              | Deskripsi                                        |
|-----------------------|--------------------------------------------------|
| `touch <file>`        | Membuat file baru                                |
| `mkdir <direktori>`   | Membuat direktori baru                           |
| `rm <file>`           | Menghapus file                                   |
| `rm -r <direktori>`   | Menghapus direktori beserta isinya              |
| `mv <file1> <file2>`  | Memindahkan/mengubah nama file                   |
| `cp <file> <direktori>` | Menyalin file ke direktori lain                  |
| `cp -r <dir1> <dir2>` | Menyalin direktori beserta isinya               |

---

## 3. Menampilkan Isi File

| Perintah            | Deskripsi                                |
|---------------------|------------------------------------------|
| `cat <file>`        | Menampilkan isi file                     |
| `less <file>`       | Menampilkan isi file per halaman         |
| `head <file>`       | Menampilkan 10 baris pertama file        |
| `tail <file>`       | Menampilkan 10 baris terakhir file       |
| `tail -f <file>`    | Menampilkan isi file yang terus diperbarui (log) |

---

## 4. Pencarian File dan Teks

| Perintah                   | Deskripsi                                        |
|----------------------------|--------------------------------------------------|
| `find /path -name "file.txt"` | Mencari file berdasarkan nama                    |
| `grep "teks" file.txt`     | Mencari teks dalam file                           |
| `grep -r "teks" /direktori/` | Mencari teks dalam semua file di direktori       |
| `locate <nama_file>`       | Mencari file dengan database `updatedb`          |
| `which <perintah>`         | Menampilkan lokasi perintah (biner)              |
| `whereis <perintah>`       | Menampilkan lokasi biner, source, dan manual     |

---

## 5. Manajemen Proses

| Perintah               | Deskripsi                                       |
|------------------------|-------------------------------------------------|
| `ps aux`               | Menampilkan daftar proses berjalan              |
| `top`                  | Menampilkan proses secara real-time             |
| `htop`                 | Versi lebih interaktif dari `top` (butuh install)|
| `kill <PID>`           | Menghentikan proses berdasarkan PID              |
| `killall <nama_proses>`| Menghentikan semua proses dengan nama tertentu  |
| `pkill <nama_proses>`  | Menghentikan proses berdasarkan nama            |

---

## 6. Manajemen Pengguna dan Hak Akses

| Perintah                 | Deskripsi                                          |
|--------------------------|----------------------------------------------------|
| `whoami`                 | Menampilkan user yang sedang login                 |
| `who`                    | Menampilkan daftar user yang sedang login          |
| `chmod 755 <file>`       | Mengubah permission file                           |
| `chown user:group <file>`| Mengubah kepemilikan file/direktori                |

---

## 7. Jaringan

| Perintah             | Deskripsi                                      |
|----------------------|------------------------------------------------|
| `ip a`               | Menampilkan informasi IP Address               |
| `ifconfig`           | Menampilkan informasi jaringan (deprecated)    |
| `ping <host>`        | Mengecek konektivitas ke host                   |
| `netstat -tulnp`     | Menampilkan port yang sedang digunakan         |
| `curl -I <URL>`      | Mengecek header HTTP suatu URL                  |
| `wget <URL>`         | Mengunduh file dari URL                         |

---

## 8. Manajemen Paket

| Perintah                  | Deskripsi                                       |
|---------------------------|-------------------------------------------------|
| `apt update`              | Memperbarui daftar paket (Debian/Ubuntu)        |
| `apt upgrade`             | Memperbarui semua paket (Debian/Ubuntu)         |
| `apt install <package>`   | Menginstal paket (Debian/Ubuntu)                |
| `apt remove <package>`    | Menghapus paket (Debian/Ubuntu)                 |
| `dnf install <package>`   | Menginstal paket (Fedora)                       |
| `pacman -S <package>`     | Menginstal paket (Arch Linux)                   |

---

## 9. Arsip dan Kompresi

| Perintah                    | Deskripsi                                          |
|-----------------------------|----------------------------------------------------|
| `tar -cvf file.tar file/`   | Membuat arsip `.tar`                               |
| `tar -xvf file.tar`         | Mengekstrak arsip `.tar`                           |
| `tar -czvf file.tar.gz file/` | Membuat arsip `.tar.gz` (terkompresi)             |
| `tar -xzvf file.tar.gz`     | Mengekstrak arsip `.tar.gz`                        |
| `zip file.zip file/`        | Membuat arsip `.zip`                               |
| `unzip file.zip`            | Mengekstrak arsip `.zip`                           |

---

## 10. Lain-lain

| Perintah           | Deskripsi                                       |
|--------------------|-------------------------------------------------|
| `history`          | Menampilkan riwayat perintah                    |
| `clear`            | Membersihkan layar terminal                     |
| `alias ll='ls -la'` | Membuat alias perintah                         |
| `date`             | Menampilkan tanggal dan waktu saat ini          |
| `uptime`           | Menampilkan waktu sistem berjalan               |
| `df -h`            | Menampilkan penggunaan disk                     |
| `du -sh <direktori>`| Menampilkan ukuran direktori                    |