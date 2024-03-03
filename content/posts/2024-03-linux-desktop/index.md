---
title: "Linux Overview: Linux Desktop"
summary: "High level summary of the linux desktop."
date: 2024-03-03
draft: false
categories: ["Linux"]
tags: ["Linux Desktop"]
series: ["Linux-Overview"]
series_order: 2
---

## The Linux Desktop

The Linux kernel relies on a software stack in order to provide a desktop experience. 
That software stack includes driver support, display server, system libraries, system daemons, desktop shells, and UI toolkits.
Sounds complicated right? There actually is a lot of software behind the scenes - for any operating system - that allows even the most basic usage of graphic interfaces, mouse, and keyboard. 
The good news that most Linux desktop users do not have to worry about managing all that stuff. This is thanks to developers and maintainers of Linux distributions. 

## Linux Distributions

A Linux distributions (aka Linux distro), is a select stack of software that is built on top of the Linux kernel. 
The differences between distros really boils down to a couple things: package manager (i.e. the way you install and maintain software) and update cadence. 
This is where the fun begins. Each distro is built with specific philosophies, for example Ubuntu tries to provide a preconfigured, easy to use, and complete desktop experience from the get go. On the other hand, Arch Linux provides a wiki and a disc image of their installer, giving you full authority (and responsibility) to manage every bit of your desktop (other than the complete essentials).

In most cases, you can strip down the even the most preconfigured distro and make it look and function like another one. 
As a first time Linux user, a distro that requires the least bit of initial tinkering is recommended.
Before jumping into a Linux distribution, it is important to check whether it will support your hardware out of the box, if it requires manual intervention, or there is no solution at the moment.
The next topic to cover is that of a desktop environment.


## Desktop Environment

Desktop environments are optional to Linux systems, as there are many use cases that require only the standard CLI. 
Linux provides the ability to choose a desktop environment during log in, meaning multiple may be coexist on a system, letting the user choose one based on their needs.
Popular desktop environments include many extensions, such as how GNOME includes a login screen, panels, systrays, and tools to configure settings.
For a lightweight system, one might opt for a more efficient yet less feature-rich window manager (such as *twm* / *fluxbox*) or desktop environment (such as *LXDE* / *Xfce*).
On more powerful systems, *GNOME* and *KDE* are good desktop environments options to choose from.

A desktop environment relies on a desktop interface and window manager, both of which work in tandem to provide a graphical experience that most of us are familiar with.

## Desktop Interfaces

### X Windows System

- The X Window System (aka X) desktop interface provides a framework that allows development of desktop environments and simple window managers.
- X works similar to a backwards client/server model.
	- The X server runs on the local system providing an interface for hardware.
	- The X clients consist of graphical applications that can be launched a local system or system on a network to which the X server permits.
- X itself provides a plain gray background and a "X" shaped mouse cursor - no menus, panels, or icons on a plain X screen.
	- An X client wont have a border around it to move, minimize, or close the window. These features are handled by a [window manager](#window-managers).

### X Implementations

- Most major Linux distributions use an X implementation from the [X.Org Foundation](http://www.x.org).
- Another up and coming X server is called [Wayland](http://wayland.freedesktop.org/), which is currently the default X server for Fedora.

## Window Managers

- Window managers, as the name indicates, provide the ability to manage windows that have been launched, i.e. the X clients.
- They also often provide menus for launching applications and working with the desktop.

