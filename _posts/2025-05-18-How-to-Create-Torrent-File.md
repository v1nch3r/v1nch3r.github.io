---
title: How to Create Torrent File
tags: [Linux]
style: fill
color: secondary
description: Torrent is a method of sharing files over the internet using a peer-to-peer (P2P) network. Instead of downloading a file from one server, torrent allows users to download small parts of the file from many other users who already have it. This makes the download faster and reduces the load on a single server.
---

## Transmission

Format:

```shell
transmission-create -o <output_file.torrent> -t <announce_url> <file_or_directory>
```

Example:

```shell
transmission-create -o file.torrent -t udp://tracker.opentrackr.org:1337/announce /home/file.img
```

## Mktorrent

Format:

```shell
mktorrent -a <announce_url> -o <output_file.torrent> <file_or_directory>
```

Example:
```shell
mktorrent -a udp://tracker.opentrackr.org:1337/announce -o file.torrent /home/file.img
```
