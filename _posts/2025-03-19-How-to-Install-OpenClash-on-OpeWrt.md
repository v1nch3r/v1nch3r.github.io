---
title: How to Install OpenClash on OpenWrt
tags: [Linux, OpenWrt]
style: fill
color: success
description: OpenClash is a Clash or Mihomo implementation for OpenWRT, used to set up a proxy with various rules.
---

<br>
{% capture list_items %}
Install Dependencies
Download and Install OpenClash
Enable OpenClash
{% endcapture %}
{% include elements/list.html title="Page Index / Daftar Isi" type="toc" %}

# Installation Guide

## Install Dependencies
`iptables`

```shell
opkg update
opkg install bash iptables dnsmasq-full curl ca-bundle ipset ip-full iptables-mod-tproxy iptables-mod-extra ruby ruby-yaml kmod-tun kmod-inet-diag unzip luci-compat luci luci-base
```

`nftables`

```shell
opkg update
opkg install bash dnsmasq-full curl ca-bundle ip-full ruby ruby-yaml kmod-tun kmod-inet-diag unzip kmod-nft-tproxy luci-compat luci luci-base
```

## Download and Install OpenClash

```shell
wget https://github.com/vernesong/OpenClash/releases/download/v0.46.079/luci-app-openclash_0.46.079_all.ipk
opkg install luci-app-openclash_0.46.079_all.ipk
```

> Note: The version may change. Check the latest version on [OpenClash GitHub.](https://github.com/vernesong/OpenClash)

## Enable OpenClash

1. Open **Services > OpenClash** in LuCI.
2. Select the configuration you want to use.
3. Click **Enable OpenClash** and **Start**.