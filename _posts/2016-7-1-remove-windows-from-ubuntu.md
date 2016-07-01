---
layout: post
title: Remove Windows & keep Ubuntu
---
Yesterday I removed Windows 10 from my Lenovo laptop while keeping Ubuntu 14.04 LTS installed. 

As suggested by the two tutorials I found online:

[tutorial 1](http://lifehacker.com/how-to-uninstall-windows-or-linux-after-dual-booting-508710422)

[tutorial 2](https://www.pcsteps.com/330-delete-windows-linux-mint-ubuntu-dual-boot/)

I inserted a Ubuntu Live CD (burnt on an usb stick) and used Gparted for deleting the Windows partition and resizing the Ubuntu partition.

However, there was still a grub entry of Windows when I rebooted. Following [this article](https://linuxnorth.wordpress.com/2011/03/09/grub2-revisited/), I disabled the script 30_os-prober in /etc/grub.d by removing its checkmark from the execute bit. Finally run the command: **sudo update-grub**, this will update GRUB.

Reboot again, there's no entry for Windows anymore! Enjoy the Window-free system.
