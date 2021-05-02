|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Linux Kernel Runtime Guard (LKRG) Install Script

Linux Kernel Runtime Guard (LKRG) is developed by Openwall team.  LKRG can prevent and/or detect the Linux kernelspace exploit.  However, the Userspace exploit cannot be detected or prevented, such as DirtyC0W exploit even it uses the kernel for the exploit.

Be keep in mind that LKRG may be/can be bypassed like other programs.

These scripts can install/uninstall LKRG on Ubuntu Linux (or debain based) with ease.  It uses DKMS that it will be recompiled automatically when new Linux kernel is installed.

These scripts are released under GPLv3 License by Samiux and it is free of charge.

The current scripts are for LKRG version 0.9.1.

## Download LKRG

```bash
sudo apt install git
git clone https://github.com/samiux/lkrg
cd lkrg
```

## Install LKRG

```bash
sudo chmod +x lkrg-0.9.1-install
sudo ./lkrg-0.9.1-install
```

## Uninstall LKRG

```bash
sudo chmod +x lkrg-0.9.1-uninstall
sudo ./lkrg-0.9.1-uninstall
```

## Stop LKRG

```bash
sudo systemctl stop lkrg
```

## Start or Restart LKRG

```bash
sudo systemctl start lkrg

sudo systemctl restart lkrg
```

## Status of LKRG

```bash
sudo sysctl -a | grep lkrg

dmesg | grep lkrg
```

## Known Issues

- If Virtualbox is installed after the installation of LKRG, it is required to uninstall and reinstall LKRG; otherwises, Virtualbox will not working properly.  

## Reference 

- [LKRG - Linux Kernel Runtime Guard -- Openwall (Developer)](https://www.openwall.com/lkrg/)  
- [LKRG - Linux Kernel Runtime Guard -- GitHub](https://github.com/openwall/lkrg)  
- [Linux Kernel Runtime Guard -- LinuxReviews](https://linuxreviews.org/Linux_Kernel_Runtime_Guard)  
- [Linux Kernel Runtime Guard 0.9.1 Is Released -- LinuxReviews](https://linuxreviews.org/Linux_Kernel_Runtime_Guard_0.9.1_Is_Released)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
