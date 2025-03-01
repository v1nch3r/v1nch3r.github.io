---
title: Cara Install WordPress Menggunakan Docker
tags: [Linux, WordPress]
style: fill
color: primary
description: Instalasi WordPress di Docker pada Debian menggunakan Docker Compose untuk menjalankan WordPress dan MySQL dalam container terisolasi.
---

## Install Docker & Docker Compose
Jalankan perintah berikut untuk menginstal Docker dan Docker Compose:

```shell
curl -fsSL https://get.docker.com | sh
```

## Buat Direktori untuk WordPress
Buat folder untuk menyimpan konfigurasi WordPress:

```shell
mkdir -p /opt/wordpress/
cd /opt/wordpress/
```

## Buat File docker-compose.yml
Buat file docker-compose.yml dengan isi berikut:

```yml
version: '3.8'

services:
  db:
    image: mysql:5.7
    container_name: wordpress_db
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: rootpassword
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wordpressuser
      MYSQL_PASSWORD: wordpresspassword
    volumes:
      - db_data:/var/lib/mysql

  wordpress:
    image: wordpress:latest
    container_name: wordpress_app
    restart: always
    depends_on:
      - db
    ports:
      - "8080:80"
    environment:
      WORDPRESS_DB_HOST: db:3306
      WORDPRESS_DB_NAME: wordpress
      WORDPRESS_DB_USER: wordpressuser
      WORDPRESS_DB_PASSWORD: wordpresspassword
    volumes:
      - wp_data:/var/www/html

volumes:
  db_data:
  wp_data:
```

## Jalankan WordPress
Jalankan perintah berikut untuk memulai layanan:

```shell
docker-compose up -d
```
### Akses WordPress
Buka browser dan akses:

```
http://server-ip:8080
```

Gantilah server-ip dengan alamat IP server Debian Anda.
