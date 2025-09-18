# Making a chroot ARM64 Environment on AMD64

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

 Using ```trixie``` (testing, debian 13.1) as ARM64 development environment on Ubuntu 24.04.3 LTS.
 
 ## On the host
 
 ```
 sudo apt-get install qemu-utils qemu-efi-aarch64 qemu-system-arm chrootuid \
      qemu-user-static binfmt-support debootstrap debian-archive-keyring
 ```
 
 ```
 sudo -sH
 ```
 
 Download the ARM64 image.
 
 ```
 qemu-debootstrap --arch=arm64 --keyring /usr/share/keyrings/debian-archive-keyring.gpg \
--variant=buildd --exclude=debfoster trixie debian-arm64 http://ftp.debian.org/debian
 ```
 
 ```
 chroot debian-arm64/
 ```
 
 ## On the guest
 
 ```
 apt install build-essential cmake dh-make locales nano dialog
 ```
 
 Fix locales.
 
 ```
 nano /etc/locale.gen
locale-gen
dpkg-reconfigure locales
```

Should choose ```C.UTF-8``` as default.

Samiux        
September 19, 2025, Hong Kong, China        

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
