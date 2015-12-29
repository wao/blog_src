---
layout: post
title:  "Install Ubuntu 15.10 in MSI GE62-2QD"
date:   2015-12-11 10:36:29
tags: Ubuntu
---

Recently, I bought a new MSI GE62 2QD Notebook which has an Intel i7-5700HQ and an Nvdia GTX960M. At first day I got it, I had trouble to install Ubuntu 15.10 on it. I even can't boot up from LiveCD and enter installer GUI. I googled it and found some blogs about old model or old ubuntu version. I tried their advice and has no effective. After some reseach, I realized that the problem is caused by new Nvidia GTX960M. It is obvious that linux default driver for nvdia card, nouveau has big problem with it. Luckly, all the Intel platform notebook has an embed Intel Display card which Ubuntu support quite perfect. All I need to to is disable nouveau before LiveCD bootup. 

Following the advice of [this article](http://forums.debian.net/viewtopic.php?t=79797), I can launcher intaller and install Ubuntu 15.10. The following same procdure at my Ubuntu first boot phase and successfully boot system.

After that, modify file `/etc/default/grub`, change line 

        GRUB_CMDLINE_LINUX="" 

to 

        GRUB_CMDLINE_LINUX="nouveau.modeset=0" 
        
and run command 

        sudo update-grub

After that, I can enjoy my new notebook.

FYI, the method to disable nouveau is following steps:

1. At the grub screen, press the up or down arrow keys to select the grub stanza/entry in question.  
2. Press the "E" key. 
3. An editor will open up that will allow you to temporarily change the grub options for the next boot.
4. Press the down arrow key and move the cursor to the line after the line with the kernel options. The line with the kernel options might look something like:

        linux   /boot/vmlinuz-3.2.0-2-486 root=UUID=1cfa3078-b27d-471a-a476-e948f947f058 ro  quiet

5. Press the left/right arrow keys to position the cursor at the end of kernel options line.
6. Type in `nouveau.modeset=0`
7. Press either the F10 key or Ctrl+X to start the boot process.

