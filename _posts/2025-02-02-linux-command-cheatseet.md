---
title: Linux Commands Cheat Sheet
tags: [Linux]
style: fill
color: info
description: This is a Basic Linux Command Cheatsheet offering a quick reference for common Linux commands. It covers tasks like file management, navigation, process management, networking, and more, making it useful for developers, system administrators, or anyone working with Linux systems.
---

<br>
{% capture list_items %}
File and Directory Navigation
File and Directory Manipulation
Viewing File Contents
Process Management
User and Permission Management
Networking
Package Management
Archiving and Compression
Miscellaneous
{% endcapture %}
{% include elements/list.html title="Page Index / Daftar Isi" type="toc" %}

# Basic Linux Command Cheatsheet

## File and Directory Navigation

| Command            | Description                                |
|--------------------|--------------------------------------------|
| `pwd`              | Display the current directory              |
| `ls`               | List the contents of a directory           |
| `ls -l`            | List detailed information of files/directories |
| `ls -a`            | List all files, including hidden ones (.) |
| `cd <directory>`   | Change to a specific directory             |
| `cd ..`            | Go back to the previous directory          |
| `cd ~`             | Change to the home directory               |
| `cd -`             | Go back to the previous directory          |

---

## File and Directory Manipulation

| Command              | Description                                        |
|----------------------|----------------------------------------------------|
| `touch <file>`       | Create a new file                                  |
| `mkdir <directory>`  | Create a new directory                             |
| `rm <file>`          | Remove a file                                      |
| `rm -r <directory>`  | Remove a directory and its contents                |
| `mv <file1> <file2>` | Move/rename a file                                 |
| `cp <file> <directory>` | Copy a file to another directory                   |
| `cp -r <dir1> <dir2>` | Copy a directory and its contents                  |

---

## Viewing File Contents

| Command            | Description                                |
|--------------------|--------------------------------------------|
| `cat <file>`       | Display the contents of a file             |
| `less <file>`      | Display the contents of a file page by page |
| `head <file>`      | Display the first 10 lines of a file       |
| `tail <file>`      | Display the last 10 lines of a file        |
| `tail -f <file>`   | Display the continuously updated contents of a file (e.g., log) |

---

## 4. File and Text Searching

| Command                     | Description                                          |
|-----------------------------|------------------------------------------------------|
| `find /path -name "file.txt"` | Search for a file by name                           |
| `grep "text" file.txt`      | Search for text within a file                       |
| `grep -r "text" /directory/` | Search for text within all files in a directory     |
| `locate <file_name>`         | Search for a file using the `updatedb` database     |
| `which <command>`            | Display the location of a command (binary)          |
| `whereis <command>`          | Display the location of the binary, source, and manual |

---

## Process Management

| Command               | Description                                       |
|-----------------------|---------------------------------------------------|
| `ps aux`              | Display a list of running processes               |
| `top`                 | Display processes in real-time                    |
| `htop`                | Interactive version of `top` (needs installation) |
| `kill <PID>`          | Terminate a process by PID                        |
| `killall <process_name>` | Terminate all processes by name                   |
| `pkill <process_name>` | Terminate processes by name                       |

---

## User and Permission Management

| Command                   | Description                                            |
|---------------------------|--------------------------------------------------------|
| `whoami`                  | Display the current logged-in user                      |
| `who`                     | Display the list of currently logged-in users          |
| `chmod 755 <file>`        | Change file permissions                                 |
| `chown user:group <file>` | Change file/directory ownership                        |

---

## Networking

| Command            | Description                                      |
|--------------------|--------------------------------------------------|
| `ip a`             | Display IP address information                   |
| `ifconfig`         | Display network information (deprecated)         |
| `ping <host>`      | Check connectivity to a host                     |
| `netstat -tulnp`   | Display open ports and listening services        |
| `curl -I <URL>`    | Check HTTP headers of a URL                      |
| `wget <URL>`       | Download a file from a URL                       |
| `iftop`             | Display bandwidth usage on an interface by host   |

---

## Package Management

| Command               | Description                                          |
|-----------------------|------------------------------------------------------|
| `apt update`          | Update the package list (Debian/Ubuntu)              |
| `apt upgrade`         | Upgrade all packages (Debian/Ubuntu)                 |
| `apt install <package>` | Install a package (Debian/Ubuntu)                   |
| `apt remove <package>`  | Remove a package (Debian/Ubuntu)                    |
| `dnf install <package>` | Install a package (Fedora)                         |
| `pacman -S <package>`   | Install a package (Arch Linux)                      |

---

## Archiving and Compression

| Command                      | Description                                          |
|------------------------------|------------------------------------------------------|
| `tar -cvf file.tar file/`     | Create a `.tar` archive                              |
| `tar -xvf file.tar`           | Extract a `.tar` archive                             |
| `tar -czvf file.tar.gz file/` | Create a compressed `.tar.gz` archive                |
| `tar -xzvf file.tar.gz`       | Extract a `.tar.gz` archive                          |
| `zip file.zip file/`          | Create a `.zip` archive                              |
| `unzip file.zip`              | Extract a `.zip` archive                             |

---

## Miscellaneous

| Command            | Description                                       |
|--------------------|---------------------------------------------------|
| `history`          | Display command history                          |
| `clear`            | Clear the terminal screen                        |
| `alias ll='ls -la'` | Create an alias for a command                    |
| `date`             | Display the current date and time                |
| `uptime`           | Display system uptime                            |
| `df -h`            | Display disk space usage                         |
| `du -sh <directory>` | Display the size of a directory                  |