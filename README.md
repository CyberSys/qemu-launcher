QEMU Launcher
=============

QEMU Launcher is an application designed for simple QEMU virtual machine management.  It is licensed under the GPLv3.  It not available under a prior or future version of the GPL.

Operation
---------

Terminal (GUI Only)

> Allows the user to specify if they would like to use a terminal and, if so, which one.  Use of this option is highly recommended as it gives access to the QEMU console.  A terminal must be used if the user would like to chroot into a disk image that holds a GNU/Linux OS.

Disk Images (-p -s -b -d -a)

> The user can specify up to five disk images of a pre-determined type.  Primary devices will boot while secondary devices will not.  If both Primary HDD and ROM are specified, QEMU Launcher will boot from the ROM media.

Cores (-c, CLI Only for now)

> The user can specify how many cores to give to the VM.  Default is [cores+1]/2

Chroot (-r)

> For GNU/Linux virtual machine, QEMU Launcher can set up a chroot for diagnosis and repair.  In the GUI, this will necessitate a terminal be used.

USB Mouse (-u)

> Some operating systems (FreeBSD, early Windows) will not work with the Tablet Device that QEMU Launcher sets up by default.  While tracking might not be synchronized, some mouse is better than no mouse.

IDE Mode (-i)

> Some operating systems (early Windows) have no VirtIO drivers available to them.  Some operating systems (Windows 2000, XP) have drivers but don't have an easy way to install them during setup.

Force Secondary VirtIO (-v)

> For operating systems that have VirtIO drivers that can be installed post-setup, this allows the virtual machine to keep IDE Mode on the Primary HDD (so the OS can boot) while presenting a VirtIO HDD (so the drivers can be installed).

Use QXL/SPICE (-q)

> Through my personal testing, I found VNC to be a better solution that the combination of QXL and SPICE thanks to the recent addition of bochs_drm to the Linux kernel.  Others may have had better luck or have a larger collection of VMs that might be a hassle to move, so the option to use QXL and SPICE has stayed.

Memory Allocation (-m)

> Self-explanatory.

X11 Listening Port (-x)

> When using VNC, this will be the port specified in the vncviewer command.  When using QXL, this number is added to 6000 to get the SPICE listening port number.


Files
-----

qcl - QEMU Command Launcher

> This is the shell script that forms the basis of QEMU Launcher's simple virtual machine management.

qgl - QEMU Graphical Launcher

> This script contains the logic code behind the GUI implementation of QEMU Launcher.

qglgui.py -- QEMU Graphical Launcher Graphical User Interface

> This script contains the GUI elements.  It is built with wxFormBuilder and should not be edited directly.

ql.fbp -- QEMU Launcher Form Builder Project

> This is the project file generated by wxFormBuilder.  This is used to generate qglgui.py

