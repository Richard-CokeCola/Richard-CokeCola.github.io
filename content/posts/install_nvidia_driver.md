---
title: "Install Nvidia GPU driver on Ubuntu"
date: 2021-08-09T08:46:38+08:00
tags:  [  " AI " , "Tutorial"]
---

Install Nvidia driver on Ubuntu is very tricky. Sometimes it goes extremely smooth while sometime it just doesn't work. Follow these following steps, it should make it easier.

1. Download Nvidia driver to your Ubuntu machine from its website. It is a .run file.

2. Install make and gcc.

   ```bash
   sudo apt install make    
   sudo apt install gcc
   ```

3. Disable Nouveau kernel driver.

   ```bash
   # Create a file
   sudo nano /etc/modprobe.d/blacklist-nouveau.conf
   ```

   with the following contents:

   ```
   blacklist nouveau
   options nouveau modeset=0
   ```

   Regenerate the kernel initramfs:

   ```bash
   sudo update-initramfs -u
   ```

   Then reboot

   ```bash
   sudo reboot
   ```

4. Hit Ctrl+Alt+F1 and login using your credentials. Then kill your current X server session by typing sudo service lightdm stop or sudo lightdm stop. Enter runlevel 3 by typing:

   ```bash
   sudo init 3
   ```

5. Install the driver

   ```bash
   sudo ./Your_Nvidia_Driver.run
   ```

**Ref:**

https://www.cnblogs.com/zqifa/p/12910989.html

