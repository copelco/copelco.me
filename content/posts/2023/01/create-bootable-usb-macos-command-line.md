---
title: "Create a bootable Ubuntu USB stick on macOS from the command line"
date: 2023-01-02T11:19:16-05:00
tags: ["til"]
draft: false
---

Ubuntu's official guide [Create a bootable USB stick on macOS](https://ubuntu.com/tutorials/create-a-usb-stick-on-macos) works, but it currently requires [Etcher](https://www.balena.io/etcher/), runs on x86 through Rosetta, and assumes you want to run on a Mac too. TIL how to use the command line to create a bootable Ubuntu Server `amd64` USB flash drive.

Plug in your USB flash drive and look it up using `diskutil`:

```sh
diskutil list external
```

Erase and reformat using a Master Boot Record (MBR), then unmount it:

```sh
diskutil eraseDisk FAT32 UBUNTU MBRFormat /dev/disk4
diskutil unmountDisk /dev/disk4
```

Download an Ubuntu ISO:

```sh
wget https://releases.ubuntu.com/jammy/ubuntu-22.04.1-live-server-amd64.iso
```

Copy image to the USB drive (note the **r** before the device name):

```
sudo dd if=ubuntu-22.04.1-live-server-amd64.iso of=/dev/rdisk4 bs=1m
```

Eject the USB drive:

```sh
hdiutil detach /dev/disk4
```
