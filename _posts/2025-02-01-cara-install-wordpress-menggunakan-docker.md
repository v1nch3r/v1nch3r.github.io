---
title: Cara Install WordPress Menggunakan Docker
tags: [Linux, WordPress]
style: fill
color: primary
description: Instalasi WordPress di Docker pada Debian menggunakan Docker Compose untuk menjalankan WordPress dan MySQL dalam container terisolasi.
---

<br>
{% capture list_items %}
Install Docker & Docker Compose
Buat Direktori untuk WordPress
Buat File docker-compose.yml
Jalankan WordPress
Akses WordPress
{% endcapture %}
{% include elements/list.html title="Page Index / Daftar Isi" type="toc" %}

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
services:

  wordpress:
    image: wordpress
    restart: always
    ports:
      - 8080:80
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: exampleuser
      WORDPRESS_DB_PASSWORD: examplepass
      WORDPRESS_DB_NAME: exampledb
    volumes:
      - wordpress:/var/www/html

  db:
    image: mysql:8.0
    restart: always
    environment:
      MYSQL_DATABASE: exampledb
      MYSQL_USER: exampleuser
      MYSQL_PASSWORD: examplepass
      MYSQL_RANDOM_ROOT_PASSWORD: '1'
    volumes:
      - db:/var/lib/mysql

volumes:
  wordpress:
  db:
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
