---
title: "Perbedaan OpenWrt vs LEDE vs ImmortalWrt: Mana yang Cocok untukmu?"
tags: [Linux, OpenWrt, Networking]
style: fill
color: primary
description: "Memahami perbedaan antara OpenWrt Official, LEDE (coolsnowwolf), dan ImmortalWrt — mulai dari sejarah, fitur, kelebihan, dan kekurangannya."
---

<br>

## Pendahuluan

Jika kamu pernah berkecimpung di dunia networking atau pernah memodifikasi router, pasti kamu pernah mendengar tentang **OpenWrt**. Tapi tahukah kamu bahwa ada beberapa "varian" OpenWrt yang beredar di luar sana? Yap, ada **LEDE** dan **ImmortalWrt**. Masing-masing punya kelebihan dan kekurangan tersendiri. Mari kita bahas satu per satu.

## Sejarah Singkat

Untuk memahami mengapa ada beberapa varian OpenWrt, kita perlu menengok sebentar sejarahnya.

Pada tahun 2016, terjadi konflik internal di antara developer OpenWrt. Akibatnya, sebagian developer memisahkan diri dan membuat fork baru bernama **LEDE** (Linux Embedded Development Environment). Namun pada tahun 2018, kedua belah pihak berdamai dan merge kembali menjadi OpenWrt 18.06.

Namun jalan cerita tidak berhenti di situ. Beberapa developer tetap melanjutkan versi mereka sendiri:

- **coolsnowwolf** melanjutkan nama LEDE dengan repositori sendiri, menambahkan berbagai paket proxy/VPN yang tidak ada di OpenWrt official.
- **immortalwrt** melakukan fork dari LEDE, fokus pada dukungan perangkat khusus pasar China dan menambahkan lebih banyak paket.

## OpenWrt Official

OpenWrt Official adalah proyek utama yang dikelola komunitas global di [openwrt.org](https://openwrt.org).

### Kelebihan

- **Stabilitas tertinggi** — Setiap release melalui pengujian ketat
- **Release terjadwal** — Update stabil sekitar setiap 6 bulan
- **Kompatibilitas luas** — Mendukung ratusan device dari berbagai vendor
- **Dokumentasi lengkap** — Wiki resmi yang sangat detail
- **Keamanan** — Package harus lulus review komunitas sebelum masuk

### Kekurangan

- **Tidak ada proxy/VPN tools** — SSR+, Clash, Passwall tidak tersedia karena masalah lisensi
- **Package lebih sedikit** — Hanya paket yang lulus review yang masuk
- **Update lebih lambat** — Prioritas stabilitas daripada fitur baru

### Cocok untuk

- Server produksi
- Router yang butuh stabilitas tinggi
- Pengguna yang tidak butuh proxy/VPN tools
- Docker host, monitoring, automation

## LEDE (coolsnowwolf)

LEDE oleh coolsnowwolf adalah fork yang dikelola di [github.com/coolsnowwolf/lede](https://github.com/coolsnowwolf/lede). Meskipun namanya "LEDE", ini bukan LEDE asli yang merge ke OpenWrt pada 2018, melainkan kelanjutan dari komunitas China.

### Kelebihan

- **Proxy/VPN tools lengkap** — SSR+ (ShadowsocksR), OpenClash, Passwall, v2rayA sudah pre-installed
- **Rolling release** — Selalu dapat update terbaru di master branch
- **Driver lebih lengkap** — Tambahan driver untuk modem USB, WiFi, dan perangkat China
- **Custom firmware builds** — Banyak custom firmware seperti HelmiWrt yang berbasis LEDE
- **Komunitas aktif** — Forum dan grup China sangat aktif

### Kekurangan

- **Stabilitas kurang** — Master branch bersifat experimental, kadang ada bug
- **Tidak ada release resmi** — Tidak ada versi "stabil" seperti OpenWrt official
- **Dokumentasi terbatas** — Mayoritas dalam bahasa China
- **Risiko keamanan** — Paket tidak melalui review ketat seperti OpenWrt official

### Cocok untuk

- Pengguna yang butuh proxy/VPN (tunneling, bypass, dll)
- Eksperimen dengan custom firmware
- Router dengan modem USB (LTE tethering)
- Pengguna yang ingin fitur terbaru

## ImmortalWrt

ImmortalWrt adalah fork dari LEDE yang dikelola di [github.com/immortalwrt](https://github.com/immortalwrt). Fokus utamanya adalah dukungan perangkat khusus pasar China.

### Kelebihan

- **Dukungan perangkat China** — Xiaomi, Redmi, dan perangkat China lainnya lebih banyak didukung
- **Paket tambahan** — AdGuardHome, v2rayA, ModemManager, minieap, dan lainnya
- **Lebih banyak device support** — Termasuk perangkat yang tidak didukung OpenWrt official
- **Komunitas China aktif** — Banyak kontributor dari komunitas China

### Kekurangan

- **Stabilitas sama dengan LEDE** — Karena berbasis LEDE, risiko bug juga ada
- **Dokumentasi mayoritas bahasa China** — Sulit untuk pengguna non-China
- **Paket kurang teruji** — Sama seperti LEDE, tidak melalui review ketat

### Cocok untuk

- Pengguna perangkat China (Xiaomi, Redmi, dll)
- Yang butuh paket tambahan yang tidak ada di LEDE
- Yang butuh dukungan ModemManager dan tools modem

## Perbandingan Lengkap

| Aspek | OpenWrt Official | LEDE (coolsnowwolf) | ImmortalWrt |
|-------|-------------------|---------------------|-------------|
| **Stabilitas** | ✅ Tertinggi | ⚠️ Sedang | ⚠️ Sedang |
| **Proxy/VPN** | ❌ Tidak ada | ✅ SSR+, OpenClash, Passwall | ✅ Passwall, v2rayA |
| **Modem USB** | Dasar | ✅ Lengkap | ✅ Lengkap |
| **Device Support** | Universal | Universal + extra | ✅ Paling banyak (China) |
| **Update** | Terjadwal | Rolling | Rolling |
| **Dokumentasi** | ✅ Lengkap (English) | Terbatas (China) | Terbatas (China) |
| **Keamanan** | ✅ Review ketat | ⚠️ Santai | ⚠️ Santai |
| **Custom Firmware** | Sedikit | ✅ Banyak (HelmiWrt, dll) | Beberapa |

## Mana yang Cocok untukmu?

### Pilih OpenWrt Official jika:
- Kamu butuh router yang stabil 24/7
- Kamu menjalankan Docker, server, atau automation
- Kamu tidak butuh proxy/VPN tools
- Kamu ingin dukungan komunitas global

### Pilih LEDE jika:
- Kamu butuh proxy/VPN (SSR+, Clash, Passwall)
- Kamu ingin fitur terbaru meskipun berisiko
- Kamu menggunakan modem USB untuk internet
- Kamu ingin membangun custom firmware sendiri

### Pilih ImmortalWrt jika:
- Kamu punya perangkat China (Xiaomi router, dll)
- Kamu butuh paket yang tidak ada di LEDE
- Kamu butuh ModemManager atau tools modem spesifik

## Kesimpulan

Tidak ada yang "terbaik" secara absolut — semuanya kembali ke kebutuhanmu. OpenWrt Official unggul di stabilitas, LEDE unggul di fitur proxy/VPN, dan ImmortalWrt unggul di dukungan perangkat China.

Jika kamu masih bingung, mulailah dengan **OpenWrt Official**. Kalau ternyata kamu butuh proxy/VPN tools, baru pertimbangkan LEDE atau ImmortalWrt.

> **Tip:** Kamu bisa memulai dengan OpenWrt official, lalu menginstal paket tambahan dari repositori LEDE secara manual menggunakan `opkg` tanpa harus mengganti seluruh firmware.