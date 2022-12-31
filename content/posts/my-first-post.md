---
title: "My First Post"
date: 2022-12-27T20:54:16-05:00
draft: true
---

## Introduction

TIL...

```sh
diskutil list
diskutil eraseDisk FAT32 UNTITLED MBRFormat /dev/disk4
diskutil unmountDisk /dev/disk4
sudo dd if=ubuntu-22.04.1-live-server-amd64.dmg of=/dev/rdisk4 bs=1m
hdiutil detach /dev/disk4
```
