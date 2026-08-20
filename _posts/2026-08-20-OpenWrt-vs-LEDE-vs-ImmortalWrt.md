---
title: "Perbedaan OpenWrt vs LEDE vs ImmortalWrt: Mana yang Cocok untukmu?"
tags: [Linux, OpenWrt, Networking]
style: fill
color: primary
description: "Memahami perbedaan antara OpenWrt Official, LEDE (coolsnowwolf), dan ImmortalWrt — mulai dari sejarah, fitur, kelebihan, dan kekurangannya."
---

<br>

<!-- Language Selector -->
<div class="text-center" markdown="0">
  <a href="#id" class="btn btn-outline-primary btn-sm">🇮🇩 Indonesia</a>
  <a href="#en" class="btn btn-outline-primary btn-sm">🇬🇧 English</a>
  <a href="#zh" class="btn btn-outline-primary btn-sm">🇨🇳 中文</a>
  <a href="#ja" class="btn btn-outline-primary btn-sm">🇯🇵 日本語</a>
</div>

---

<!-- ==================== INDONESIA ==================== -->
<a name="id"></a>

## 🇮🇩 Pendahuluan

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

---

<!-- ==================== ENGLISH ==================== -->
<a name="en"></a>

## 🇬🇧 Introduction

If you've ever dabbled in networking or modified a router, you've probably heard of **OpenWrt**. But did you know there are several "variants" of OpenWrt out there? Yep, there's **LEDE** and **ImmortalWrt**. Each has its own strengths and weaknesses. Let's break them down one by one.

## Brief History

To understand why there are multiple OpenWrt variants, we need to briefly look at the history.

In 2016, an internal conflict occurred among OpenWrt developers. As a result, some developers split off and created a new fork called **LEDE** (Linux Embedded Development Environment). However, in 2018, both sides reconciled and merged back into OpenWrt 18.06.

But the story didn't end there. Some developers continued their own versions:

- **coolsnowwolf** continued the LEDE name with their own repository, adding various proxy/VPN packages not available in OpenWrt official.
- **immortalwrt** forked from LEDE, focusing on support for China-specific devices and adding more packages.

## OpenWrt Official

OpenWrt Official is the main project maintained by the global community at [openwrt.org](https://openwrt.org).

### Pros

- **Highest stability** — Every release goes through rigorous testing
- **Scheduled releases** — Stable updates approximately every 6 months
- **Broad compatibility** — Supports hundreds of devices from various vendors
- **Comprehensive documentation** — Detailed official wiki
- **Security** — Packages must pass community review before inclusion

### Cons

- **No proxy/VPN tools** — SSR+, Clash, Passwall not available due to licensing issues
- **Fewer packages** — Only packages that pass review are included
- **Slower updates** — Stability prioritized over new features

### Best for

- Production servers
- Routers requiring high stability
- Users who don't need proxy/VPN tools
- Docker host, monitoring, automation

## LEDE (coolsnowwolf)

LEDE by coolsnowwolf is a fork maintained at [github.com/coolsnowwolf/lede](https://github.com/coolsnowwolf/lede). Although named "LEDE", this is not the original LEDE that merged into OpenWrt in 2018, but a continuation from the Chinese community.

### Pros

- **Comprehensive proxy/VPN tools** — SSR+ (ShadowsocksR), OpenClash, Passwall, v2rayA pre-installed
- **Rolling release** — Always gets the latest updates on master branch
- **More drivers** — Additional drivers for USB modems, WiFi, and Chinese devices
- **Custom firmware builds** — Many custom firmware like HelmiWrt based on LEDE
- **Active community** — Chinese forums and groups very active

### Cons

- **Less stable** — Master branch is experimental, sometimes has bugs
- **No official releases** — No "stable" version like OpenWrt official
- **Limited documentation** — Mostly in Chinese
- **Security risk** — Packages don't go through strict review like OpenWrt official

### Best for

- Users who need proxy/VPN (tunneling, bypass, etc.)
- Custom firmware experimentation
- Routers with USB modems (LTE tethering)
- Users who want the latest features

## ImmortalWrt

ImmortalWrt is a fork from LEDE maintained at [github.com/immortalwrt](https://github.com/immortalwrt). Its main focus is support for China-specific devices.

### Pros

- **Chinese device support** — Xiaomi, Redmi, and other Chinese devices better supported
- **Additional packages** — AdGuardHome, v2rayA, ModemManager, minieap, and more
- **More device support** — Including devices not supported by OpenWrt official
- **Active Chinese community** — Many contributors from the Chinese community

### Cons

- **Same stability as LEDE** — Since it's based on LEDE, same bug risk
- **Documentation mostly in Chinese** — Difficult for non-Chinese users
- **Less tested packages** — Same as LEDE, no strict review process

### Best for

- Users with Chinese devices (Xiaomi router, etc.)
- Those needing packages not available in LEDE
- Those needing ModemManager or specific modem tools

## Full Comparison

| Aspect | OpenWrt Official | LEDE (coolsnowwolf) | ImmortalWrt |
|--------|-------------------|---------------------|-------------|
| **Stability** | ✅ Highest | ⚠️ Medium | ⚠️ Medium |
| **Proxy/VPN** | ❌ None | ✅ SSR+, OpenClash, Passwall | ✅ Passwall, v2rayA |
| **USB Modem** | Basic | ✅ Comprehensive | ✅ Comprehensive |
| **Device Support** | Universal | Universal + extra | ✅ Most (China) |
| **Updates** | Scheduled | Rolling | Rolling |
| **Documentation** | ✅ Complete (English) | Limited (Chinese) | Limited (Chinese) |
| **Security** | ✅ Strict review | ⚠️ Relaxed | ⚠️ Relaxed |
| **Custom Firmware** | Few | ✅ Many (HelmiWrt, etc.) | Some |

## Which One is Right for You?

### Choose OpenWrt Official if:
- You need a stable 24/7 router
- You run Docker, servers, or automation
- You don't need proxy/VPN tools
- You want global community support

### Choose LEDE if:
- You need proxy/VPN (SSR+, Clash, Passwall)
- You want the latest features even if risky
- You use USB modems for internet
- You want to build your own custom firmware

### Choose ImmortalWrt if:
- You have Chinese devices (Xiaomi router, etc.)
- You need packages not in LEDE
- You need ModemManager or specific modem tools

## Conclusion

There is no absolute "best" — it all comes down to your needs. OpenWrt Official excels in stability, LEDE excels in proxy/VPN features, and ImmortalWrt excels in Chinese device support.

If you're still unsure, start with **OpenWrt Official**. If you find you need proxy/VPN tools, then consider LEDE or ImmortalWrt.

> **Tip:** You can start with OpenWrt official, then install additional packages from LEDE repositories manually using `opkg` without replacing the entire firmware.

---

<!-- ==================== CHINESE ==================== -->
<a name="zh"></a>

## 🇨🇳 引言

如果你曾经涉足网络领域或修改过路由器，你一定听说过 **OpenWrt**。但你知道市面上有几种 OpenWrt 的"变体"吗？没错，有 **LEDE** 和 **ImmortalWrt**。每种都有各自的优缺点。让我们逐一分析。

## 简史

要理解为什么会有多个 OpenWrt 变体，我们需要简要回顾一下历史。

2016年，OpenWrt 开发者之间发生了内部冲突。因此，部分开发者分离出来，创建了一个名为 **LEDE**（Linux Embedded Development Environment）的新分支。然而在2018年，双方和解并合并回 OpenWrt 18.06。

但故事并没有就此结束。一些开发者继续维护自己的版本：

- **coolsnowwolf** 以自己的仓库延续了 LEDE 的名称，添加了 OpenWrt 官方没有的各种代理/VPN 包。
- **immortalwrt** 从 LEDE 分叉，专注于支持中国特定设备并添加更多包。

## OpenWrt Official

OpenWrt Official 是由全球社区维护的主要项目，网址为 [openwrt.org](https://openwrt.org)。

### 优点

- **最高稳定性** — 每个版本都经过严格测试
- **定期发布** — 大约每6个月一次稳定更新
- **广泛兼容性** — 支持来自各厂商的数百种设备
- **完善文档** — 详细的官方 Wiki
- **安全性** — 包必须通过社区审核才能加入

### 缺点

- **无代理/VPN 工具** — 由于许可问题，SSR+、Clash、Passwall 不可用
- **包较少** — 只有通过审核的包才会被加入
- **更新较慢** — 优先考虑稳定性而非新功能

### 适合

- 生产服务器
- 需要高稳定性的路由器
- 不需要代理/VPN 工具的用户
- Docker 主机、监控、自动化

## LEDE（coolsnowwolf）

coolsnowwolf 的 LEDE 是一个分支，维护在 [github.com/coolsnowwolf/lede](https://github.com/coolsnowwolf/lede)。虽然名为"LEDE"，但这不是2018年合并回 OpenWrt 的原始 LEDE，而是来自中国社区的延续。

### 优点

- **全面的代理/VPN 工具** — SSR+（ShadowsocksR）、OpenClash、Passwall、v2rayA 已预装
- **滚动发布** — master 分支始终获得最新更新
- **更多驱动** — 为 USB 调制解调器、WiFi 和中国设备添加了额外驱动
- **自定义固件构建** — 许多自定义固件如 HelmiWrt 基于 LEDE
- **活跃的社区** — 中国论坛和群组非常活跃

### 缺点

- **稳定性较差** — master 分支具有实验性质，有时会有 bug
- **无正式发布** — 没有 OpenWrt 官方那样的"稳定"版本
- **文档有限** — 大部分为中文
- **安全风险** — 包不像 OpenWrt 官方那样经过严格审核

### 适合

- 需要代理/VPN（隧道、绕过等）的用户
- 自定义固件实验
- 带 USB 调制解调器的路由器（LTE 网络共享）
- 想要最新功能的用户

## ImmortalWrt

ImmortalWrt 是从 LEDE 分叉的，维护在 [github.com/immortalwrt](https://github.com/immortalwrt)。其主要关注点是中国特定设备的支持。

### 优点

- **中国设备支持** — 小米、红米和其他中国设备更好地被支持
- **额外包** — AdGuardHome、v2rayA、ModemManager、minieap 等
- **更多设备支持** — 包括 OpenWrt 官方不支持的设备
- **活跃的中国社区** — 许多来自中国社区的贡献者

### 缺点

- **稳定性与 LEDE 相同** — 因为基于 LEDE，同样的 bug 风险
- **文档大部分为中文** — 对非中文用户较困难
- **包测试较少** — 与 LEDE 一样，没有严格审核

### 适合

- 拥有中国设备的用户（小米路由器等）
- 需要 LEDE 中没有的包
- 需要 ModemManager 或特定调制解调器工具

## 完整对比

| 方面 | OpenWrt Official | LEDE（coolsnowwolf）| ImmortalWrt |
|------|-------------------|---------------------|-------------|
| **稳定性** | ✅ 最高 | ⚠️ 中等 | ⚠️ 中等 |
| **代理/VPN** | ❌ 无 | ✅ SSR+、OpenClash、Passwall | ✅ Passwall、v2rayA |
| **USB 调制解调器** | 基本 | ✅ 全面 | ✅ 全面 |
| **设备支持** | 通用 | 通用 + 额外 | ✅ 最多（中国）|
| **更新** | 定期 | 滚动 | 滚动 |
| **文档** | ✅ 完整（英文）| 有限（中文）| 有限（中文）|
| **安全性** | ✅ 严格审核 | ⚠️ 宽松 | ⚠️ 宽松 |
| **自定义固件** | 少 | ✅ 多（HelmiWrt 等）| 一些 |

## 哪个适合你？

### 选择 OpenWrt Official 如果：
- 你需要稳定的 24/7 路由器
- 你运行 Docker、服务器或自动化
- 你不需要代理/VPN 工具
- 你想要全球社区支持

### 选择 LEDE 如果：
- 你需要代理/VPN（SSR+、Clash、Passwall）
- 你想要最新功能即使有风险
- 你使用 USB 调制解调器上网
- 你想构建自己的自定义固件

### 选择 ImmortalWrt 如果：
- 你有中国设备（小米路由器等）
- 你需要 LEDE 中没有的包
- 你需要 ModemManager 或特定调制解调器工具

## 结论

没有绝对的"最好"——一切都取决于你的需求。OpenWrt Official 在稳定性方面出色，LEDE 在代理/VPN 功能方面出色，ImmortalWrt 在中国设备支持方面优胜。

如果你仍然不确定，请从 **OpenWrt Official** 开始。如果你发现需要代理/VPN 工具，再考虑 LEDE 或 ImmortalWrt。

> **提示：** 你可以从 OpenWrt 官方版开始，然后使用 `opkg` 手动从 LEDE 仓库安装额外的包，而无需更换整个固件。

---

<!-- ==================== JAPANESE ==================== -->
<a name="ja"></a>

## 🇯🇵 はじめに

ネットワークの世界にかかわったり、ルーターを改造したことがあるなら、**OpenWrt** という名前を聞いたことがあるでしょう。でも、OpenWrtにはいくつかの「バリアント」があるのを知っていましたか？そう、**LEDE** と **ImmortalWrt** です。それぞれに独自の長所と短所があります。一つずつ解説していきましょう。

## 簡単な歴史

なぜ複数のOpenWrtバリアントが存在するのかを理解するには、少し歴史を振り返る必要があります。

2016年、OpenWrtの開発者の間で内部対立が発生しました。その結果、一部の開発者が分離し、**LEDE**（Linux Embedded Development Environment）という新しいフォークを作成しました。しかし2018年、両者は和解し、OpenWrt 18.06として再統合されました。

しかし、物語はそこで終わりませんでした。一部の開発者は独自のバージョンを継続しました：

- **coolsnowwolf** は独自のリポジトリでLEDEの名前を継続し、OpenWrt公式にはない様々なプロキシ/VPNパッケージを追加しました。
- **immortalwrt** はLEDEからフォークし、中国市場向けデバイスのサポートに焦点を当て、より多くのパッケージを追加しました。

## OpenWrt Official

OpenWrt Officialは、[openwrt.org](https://openwrt.org) でグローバルコミュニティによって管理されているメインプロジェクトです。

### 長所

- **最高の安定性** — 毎回のリリースが厳格なテストを経ている
- **定期的なリリース** — 約6ヶ月ごとの安定アップデート
- **幅広い互換性** — 様々なベンダーの数百のデバイスをサポート
- **包括的なドキュメント** — 詳細な公式Wiki
- **セキュリティ** — パッケージはコミュニティレビューに通過する必要がある

### 短所

- **プロキシ/VPNツールなし** — ライセンス問題によりSSR+、Clash、Passwallは利用不可
- **パッケージが少ない** — レビューに通過したパッケージのみ収録
- **アップデートが遅い** — 新機能より安定性を優先

### 適している用途

- 本番サーバー
- 高い安定性が必要なルーター
- プロキシ/VPNツールが不要なユーザー
- Dockerホスト、監視、自動化

## LEDE（coolsnowwolf）

coolsnowwolfによるLEDEは、[github.com/coolsnowwolf/lede](https://github.com/coolsnowwolf/lede) で管理されているフォークです。「LEDE」という名前ですが、これは2018年にOpenWrtに統合された元のLEDEではなく、中国コミュニティからの継続版です。

### 長所

- **包括的なプロキシ/VPNツール** — SSR+（ShadowsocksR）、OpenClash、Passwall、v2rayAがプリインストール
- **ローリングリリース** — masterブランチで常に最新アップデートを取得
- **より多くのドライバー** — USBモデム、WiFi、中国製デバイス用の追加ドライバー
- **カスタムファームウェアビルド** — HelmiWrtなど多くのカスタムファームウェアがLEDEベース
- **活発なコミュニティ** — 中国のフォーラムやグループが非常に活発

### 短所

- **安定性が低い** — masterブランチは実験的で、時々バグがある
- **公式リリースがない** — OpenWrt公式のような「安定版」がない
- **ドキュメントが限定的** — 主に中国語
- **セキュリティリスク** — OpenWrt公式のような厳格なレビューがない

### 適している用途

- プロキシ/VPN（トンネリング、バイパスなど）が必要なユーザー
- カスタムファームウェアの実験
- USBモデムを使用するルーター（LTEテザリング）
- 最新機能を求めるユーザー

## ImmortalWrt

ImmortalWrtはLEDEからフォークしたもので、[github.com/immortalwrt](https://github.com/immortalwrt) で管理されています。主な焦点は中国市場向けデバイスのサポートです。

### 長所

- **中国製デバイスのサポート** — Xiaomi、Redmiなど中国製デバイスのサポートが充実
- **追加パッケージ** — AdGuardHome、v2rayA、ModemManager、minieapなど
- **より多くのデバイスサポート** — OpenWrt公式がサポートしないデバイスを含む
- **活発な中国コミュニティ** — 中国コミュニティから多くの貢献者

### 短所

- **LEDEと同等の安定性** — LEDEベースのため同じバグリスク
- **ドキュメントの大部分が中国語** — 非中国語ユーザーには困難
- **パッケージのテストが不十分** — LEDEと同様に厳格なレビューがない

### 適している用途

- 中国製デバイスを使用するユーザー（Xiaomiルーターなど）
- LEDEにないパッケージが必要な場合
- ModemManagerや特定のモデムツールが必要な場合

## 完全比較

| 項目 | OpenWrt Official | LEDE（coolsnowwolf）| ImmortalWrt |
|------|-------------------|---------------------|-------------|
| **安定性** | ✅ 最高 | ⚠️ 中程度 | ⚠️ 中程度 |
| **プロキシ/VPN** | ❌ なし | ✅ SSR+、OpenClash、Passwall | ✅ Passwall、v2rayA |
| **USBモデム** | 基本 | ✅ 包括的 | ✅ 包括的 |
| **デバイスサポート** | 汎用 | 汎用 + 追加 | ✅ 最多（中国）|
| **アップデート** | 定期的 | ローリング | ローリング |
| **ドキュメント** | ✅ 完全（英語）| 限定的（中国語）| 限定的（中国語）|
| **セキュリティ** | ✅ 厳格なレビュー | ⚠️ 緩い | ⚠️ 緩い |
| **カスタムファームウェア** | 少ない | ✅ 多い（HelmiWrtなど）| 少数 |

## どれがあなたに適しているか？

### OpenWrt Officialを選ぶ場合：
- 安定した24時間稼働のルーターが必要
- Docker、サーバー、自動化を実行している
- プロキシ/VPNツールが不要
- グローバルなコミュニティサポートが必要

### LEDEを選ぶ場合：
- プロキシ/VPN（SSR+、Clash、Passwall）が必要
- リスクがあっても最新機能を求める
- USBモデムでインターネットに接続している
- 自分のカスタムファームウェアを構築したい

### ImmortalWrtを選ぶ場合：
- 中国製デバイスを使用している（Xiaomiルーターなど）
- LEDEにないパッケージが必要
- ModemManagerや特定のモデムツールが必要

## 結論

絶対的な「最良」はありません — すべてはあなたのニーズ次第です。OpenWrt Officialは安定性に優れ、LEDEはプロキシ/VPN機能に優れ、ImmortalWrtは中国製デバイスのサポートに優れています。

まだ迷っている場合は、**OpenWrt Official** から始めましょう。プロキシ/VPNツールが必要になったら、LEDEまたはImmortalWrtを検討してください。

> **ヒント：** OpenWrt公式版から始めて、`opkg` を使ってLEDEリポジトリから追加パッケージを手動でインストールすることもできます。ファームウェア全体を交換する必要はありません。