|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# TP-Link Archer TX20U Nano on Ubuntu 22.04 LTS

This article is credit to __morrownr__ who build the WIFI adapter Linux driver for rtl8852bu chipset.

Device Name : TP-Link Archer TX20U Nano (US) Version 1.0  
Device ID : 35bc:0108  
Device Chipset : rtl8852bu  

## Pre-Installation

```
sudo apt install make gcc linux-headers-$(uname -r) build-essential git dkms
git clone https://github.com/morrownr/rtl8852bu
```

## Installation

```
sudo dkms add rtl8852bu
sudo dkms build -m rtl8852bu -v 1.19.3
sudo dkms install -m rtl8852bu -v 1.19.3
```

## Post-Installation

```
sudo cp rtl8852bu/8852bu.conf /etc/modprobe.d/
echo '8852bu' | sudo tee -a /etc/modules
```

Then insert the device and reboot the system.  If it does not work, please confirm the previous wireless device driver is in the blacklist.conf at /etc/modprobe.d/blacklist.conf.

You can also check the status of dkms by issuing the following command :

```
dkms status
```

## Update or Re-installation

```
cd rtl8852bu
git pull

sudo dkms remove -m rtl8852bu -v 1.19.3
sudo dkms build -m rtl8852bu -v 1.19.3
sudo dkms install -m rtl8852bu -v 1.19.3
```

# Reference 

- [TP-Link Archer TX20U Nano](https://www.tp-link.com/hk/home-networking/adapter/archer-tx20u-nano/)  
- [TP-Link Archer TX20U Nano Linux Driver](https://github.com/morrownr/rtl8852bu)

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
