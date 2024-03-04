---
title: "Configure and Manage Linux Hardware"
date: 2024-03-04
categories: ["Linux"]
tags: ["Linux Hardware", "System Administration", "Linux Bible"]
series: ["Linux-Basic-System-Administration"]
series_order: 6
---

## Introduction

Nowadays, the Linux kernel and many popular distributions provide out of the box support for common devices, however there are still cases that require manual intervention to get a system fully up and running.
This article summarizes the section about managing and configuring hardware from [The Linux Bible](https://amzn.to/3P5Bc96).

## Checking Hardware

When a Linux system boots, it detects hardware and loads the appropriate drivers for them.
- Any user can run the `dmesg` command to see what hardware was detected and which drivers were loaded.
- `journalctl` outputs information pertaining to a particular boot instance.
- `lspci` command lists the PCI buses on your system and the hardware connected to them.
- `lsusb` lists all usb ports, and (if available) the peripherals connected via usb port, such as keyboard, mouse, and removable media.
- `lscpue` gives basic information about your processor.

### Example Output

```
$ dmesg | less
[ 0.000000] Linux version 5.0.9-301.fc30.x86_64
(mockbuild@bkernel04.phx2.fedoraproject.org) (gcc version 9.0.1 20190312
Chapter 8: Learning System Administration
[
(Red Hat 9.0.1-0.10) (GCC)) #1 SMP Tue Apr 23 23:57:35 UTC 2019 0.000000] Command line:
BOOT_IMAGE=(hd0,msdos1)/vmlinuz-5.0.9-301.fc30.x86_64 root=/dev/mapper/fedora_localhost--live-root ro resume=/dev/mapper/fedora_localhost--live-swap rd.lvm.lv=fedora_localhost-live/root rd.lvm.lv=fedora_localhost-live/swap rhgb quiet
```
This output shows the kernel version (v5.0.9) followed by kernel command-line options.
```
...

[79.177466] sd 9:0:0:0: Attached scsi generic sg2 type 0
S31B1102 USB DISK 1100 PQ: 0 ANSI: 0 CCS
[79.177854] sd 9:0:0:0: [sdb]
8343552 512-byte logical blocks: (4.27 GB/3.97 GiB)
[79.178593] sd 9:0:0:0: [sdb] Write Protect is off
```
This output depicts a removable media being mounted.
```
$ lspci
00:00.0 Host bridge: Intel Corporation
5000X Chipset Memory ControllerHub
00:02.0 PCI bridge: Intel Corporation 5000 Series Chipset
PCI Express x4 Port 2
00:1b.0 Audio device: Intel Corporation 631xESB/632xESB
High Definition Audio Controller (rev 09)
00:1d.0 USB controller: Intel Corporation 631xESB/632xESB/3100
Chipset UHCI USBController#1 (rev 09)
07:00.0 VGA compatible controller: nVidia Corporation NV44 0c:02.0 Ethernet controller: Intel Corporation 82541PI
Gigabit Ethernet Controller (rev 05)
```
If there is any hardware that is not working as intended, this is a good starting point to get the required information needed to start your research.

## Managing Removable Hardware

Most desktop environments provide a graphical interface for managing removable hardware. 
They may differ in the functions they provide, but are typically built as an interface to the same underlying mechanism, Udev.
The Udev daemon, `udevd` creates and removes devices (`/dev` directory) as they are added and removed from the computer.

If you are using a desktop environment such as GNOME or KDE, search the many ways you can configure how to handle removable media using their provided interfaces.
USB flash drives are typically created as `/dev/sda`, `/dev/sdb`, etc. and they are automatically mounted on `/run/media/your_user_name`

## Loading Modules For Missing Hardware Drivers

Kernel modules are installed in /lib/modules/ subdirectories.
The name of each sub- directory is based on the release number of the kernel.
For example, if the kernel were `5.3.8-200.fc30.x86_64`, the `/lib/modules/5.3.8-200.fc30.x86_64` directory would contain drivers for that kernel. 
Modules in those directories can then be loaded and unloaded as they are needed.
- `lsmod` lists which modules are loaded into the running kerner.
- `modinfo` provided with a module name will return information on the module.

The root user may use the command `modprobe` to temporarily load a module that wasn't automatically loaded by the kernel.
The module will not automatically load in unless included as part of a startup script.


