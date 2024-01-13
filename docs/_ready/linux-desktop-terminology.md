## Desktop Environment

A desktop environment relies on a desktop interface and window manager, both of which work in tandem to provide a graphical experience that most of us are familiar with. Popular desktop environments include many extensions, such as how GNOME includes a login screen, panels, systrays, and tools to configure settings.

Desktop environments are optional to Linux systems, as there are many use cases that require only the standard CLI. Linux provides the ability to choose a desktop environment during log in, meaning multiple may be coexist on a system, letting the user choose one based on their needs.

For a lightweight system, one might opt for a more efficient yet less feature-rich window manager (such as *twm* / *fluxbox*) or desktop environment (such as *LXDE* / *Xfce*).

On more powerful systems, *GNOME* and *KDE* are good desktop environments options to choose from.

### Desktop Interfaces

#### X Windows System

- The X Window System (aka X) desktop interface provides a framework that allows development of desktop environments and simple window managers.
- X works similar to a backwards client/server model.
	- The X server runs on the local system providing an interface for hardware.
	- The X clients consist of graphical applications that can be launched a local system or system on a network to which the X server permits.
- X itself provides a plain gray background and a "X" shaped mouse cursor - no menus, panels, or icons on a plain X screen.
	- An X client wont have a border around it to move, minimize, or close the window. These features are handled by a [window manager](#window-managers).

#### X Implementations

- Most major Linux distributions use an X implementation from the [X.Org Foundation](http://www.x.org).
- Another up and coming X server is called [Wayland](http://wayland.freedesktop.org/), which is currently the default X server for Fedora.

### Window Managers

- Window managers, as the name indicates, provide the ability to manage windows that have been launched, i.e. the X clients.
- They also often provide menus for launching applications and working with the desktop.

