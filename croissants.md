|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Croissants 牛角面包 - Intrusion Detection and Prevention System

## netplan as default

Networks and computers that are opened to the public facing hacker attacks from all over the world every day.  Once we are compromised, we would be one of the cyber crime victims.  Our tasty Croissants is a high performance and ultra-low latency Intrusion Detection and Prevention System (IDPS).  Unlike well known and famous brands for large business enterprises in the market,  Croissants is available free of charge that everyone can afford.  It is ideal for home, Small Office Home Office (SOHO) and Small Medium Business (SMB).

Not a Network Security Monitoring (NSM) or Information Security (InfoSec) expert?  No problem!  Our Croissants really is the "Plug, Play and Forget" system of your dreams.  Don't be the next cyber crime victims, try Croissants now!

Croissants is designed by a hacker to defend against hackers. He knows what hackers are doing and thinking, regardless of whether they are ethical or malicious.

## FEATURES

- Blocks known malicious activities  
- Blocks known malware and virus  
- Easy and straight forward web interfaces  
- Compatible with Bittorrent and 4K video streaming  
- Ultra-low latency for demanding online games  
- Compatible with Microsoft Windows, GNU Linux, Apple macOS, Apple iOS and Google Android  
- No subscription fee  
- Automatically update and upgrade  
- Plug, Play and Forget!  

每当电脑或网络连接互联网时，我们的电脑或网络就有机会被恶意黑客的攻击。为免成为下一个网络罪行的受害者，我们美味的牛角面包可以助你免于被袭击。不像其他知名的商业品牌，她是完全免费，每个人都能够负担的入侵防御系统。

我们的牛角面包是随插即用，用户的参与性极少，适合一般大众使用。

牛角面包是由黑客设计来对付黑客的有效工具，不论其为道德黑客抑或是恶意黑客。

## 功能概览

- 有效阻挡已知的恶意行为
- 有效阻挡已知的恶意程式
- 简单直接的用户介面
- 极低的延迟性能有效地播放 4K 多媒体和玩要求速度的网络游戏
- 兼容微软视窗、苹果电脑、Linux 等系统
- 开源项目，完全免费
- 自动更新
- 随插即用，并且可以忘记之

## LICENSE

Croissants is an Open Source Project which is released under GPLv3 License and it is developed by Samiux.

Please keep in mind that Croissants is available FREE OF CHARGE.

__Croissants is designed and developed by Samiux since 2012.__

## MINIMUM REQUIREMENTS

### Hardware

- Multi-Core Intel / AMD x86 CPU (e.g. AMD Ryzen R7-4800U for home usage)   
- 16GB DDR4 RAM or more (Croissants use at least 4GB RAM)  
- 256GB hard drive or more (SSD for better performance)   
- 3 Network Interface Cards/Ports (Network Based only)  
- 1 Network Interface Card/Port (Host Based only)  
- CPU with AVX2 or better (at least SSSE3)  
- More cores and faster CPU the better performance  

### Software

- Ubuntu Server 20.04.3 LTS (64-bit) (support until April 2025)  
- __netplan__ as default  
- Support WIFI (for Monitoring Interface only) (Intel AX200 for WPA3 is not recommended as it is unstable unless the kernel is 5.11.0-36 or later)  

## MAIN COMPONENTS

- Suricata 6.0.4  
- Hyperscan 5.2.1 (Ubuntu 20.04)    
- netdata  

## DOCUMENTATION

### 1.0 Installation Guide

#### 1.1 Download and Install

##### 1.1.1 Network Based

```bash
sudo -sH

cd /root

sudo apt install git net-tools

git clone https://github.com/samiux/idps

cd idps
```

If your monitoring network interface is a WIFI device, you need to copy ```/root/idps/wifi``` directory to ```/root```.  When your monitoring network interface is a Ethernet device, you need to copy ```/root/idps/lan``` directory to ```/root```.

```bash
cp wifi/* /root

or 

cp lan/* /root
```
```bash
cd /root/idps

cp -R lua/ /root
cp -R rules/ /root
cp * /root

cd /root

nano nsm.conf

chmod +x nsm_install

sudo ./nsm_install
```

__Make sure you edit ```nsm.conf``` before running ```nsm_install```__

The definition of nsm.conf is [here](https://github.com/samiux/samiux.github.io/blob/master/nsmconf.md).

##### 1.1.2 Host Based

```bash
sudo -sH

cd /root

sudo apt install git net-tools

git clone https://github.com/samiux/idps-host

cd idps-host

cp * /root

cd /root

nano nsm.conf

chmod +x nsm_install

sudo ./nsm_install
```

__Make sure you edit ```nsm.conf``` before running ```nsm_install```__

The definition of nsm.conf is [here](https://github.com/samiux/samiux.github.io/blob/master/nsmconf-hidps.md).

#### 1.2 Post Installation (Optional)

You are required to update the rules.  However, you should wait until the Suricata is starting up completely.  You may wait for about 15 minutes for the start up.  Or see ```<Notice> - rule reload complete``` at the end of the following command.
 
```bash
sudo tail -f /var/log/suricata/suricata.log
```

Then run :

```bash
sudo nsm_rules_update
```
#### 1.3 ChangeLog

[Croissants ChangeLog](https://github.com/samiux/samiux.github.io/blob/master/changelog.md)

### 2.0 User Guide

__WARNING : Make sure port 19999 is not opened to the public.__

#### 2.1 Glances

Text mode monitoring tool for the performance of Croissants.

```bash
glances
```

#### 2.2 Netdata

Graphic mode monitoring tool for the performance of Croissants.

__Network based only__

```bash
sudo sed -i 's/127\.0\.0\.1/0\.0\.0\.0/' /etc/netdata/netdata.conf
sudo systemctl restart netdata
```

__Network based__

```bash
http://[monitoring_ip]:19999
```
e.g. http://192.168.20.180:19999

__Host based__

```bash
http://127.0.0.1:19999
````

__Since netdata is now on the cloud and the performance of it is dropped a lot for some countries.  If you encounter the performance problem, you may consider to disable it.__  

```
sudo systemctl disable netdata
sudo systemctl stop netdata
```

#### 2.3 Suricata Health Check

```bash
sudo tail -f /var/log/suricata/stats.log | grep drop
```

Press ```CTRL+c``` to exit.

#### 2.4 Suricata Event Log

```bash
sudo tail -f /var/log/suricata/fast.log
```

Press ```CTRL+c``` to exit.

#### 2.5 Rules Management

If you want to disable some rules as they are false positive, you can edit the "disable.conf" of suricata-update.

```bash
sudo nano /etc/suricata/disable.conf
```

If you want to drop some traffic, you can edit the "drop.conf" of suricata-update.

```bash
sudo nano /etc/suricata/drop.conf
```

If you want to modify some rules, you can edit the "modify.conf" of suricata-update.

```bash
sudo nano /etc/suricata/modify.conf
```

After updated the configuration files, you should run the following command to make the changes effective.

```bash
sudo nsm_rules_update
```

#### 2.6 Ubuntu Update

```bash
sudo update_ubuntu
```

#### 2.7 Auto Configuration

Whenever you changed the nsm.conf file, you need to run the following command in order to make it effective.

```bash
sudo nano /etc/croissants/conf.d/nsm.conf

sudo /etc/croissants/conf.d/auto_config
```

### 3.0 Hall of Fame

Nathan Paquin - Unix System Expert and InfoSec guy (IRC nick : sys)  
Omnish - Gamer with InfoSec in mind (IRC nick : omnish)  
Alpharyon - Ultra speed internet user with InfoSec in mind  

### 4.0 Troubleshooting

If you cannot access internet when you are behind the Croissants, Suricata may be down unexpectedly.  You can check if it is running or not by the following command :

```bash
sudo ps aux | grep suricata
```

If it is not running, you can issue the following command to start it :

```bash
sudo systemctl restart suricata
```

You can check the suricata.log at ```/var/log/suricata/suricata.log```.  Please allow about 15 minutes for Suricata fully starting.

### 5.0 FAQ

#### What is the function of the third network interface? (Network Based)  
One is for incoming traffic (from modem or ISP) and the other is for outgoing traffic (to router or switch).  The third one is connected to the switch for management purpose.  It is also used for updating the rules and system.

#### Which network interface is used for the installation? (Network Based)  
The monitoring network interface is good for installation.  Incoming and outgoing network interfaces may cause problem during the installation.

#### How to check what network interfaces are in my box? (Network Based)  
```bash
ls /sys/class/net
```

#### How to deploy Croissants?  
The following is the recommended connection method of Croissants.  However, you can connect it behind router too.

__Network Based__

```bash
Internet --- Modem (if any) --- Croissants --- Wifi Router --- Switch --- PCs
                                    |                             |
                                    +-----------------------------+
```
```bash
5G Modem --- Croissants --- Wifi Router --- Switch --- PCs
                 |                             |
                 +-----------------------------+
```
Do not use the wifi that comes with 5G modem as the traffic flow does not protected by Croissants.

The DNS entries at 5G Modem and Wifi Router should be identical; otherwise, the speed of internet browsing would be delayed a little bit.  

__Host Based__
```bash
Internet --- Croissants (with application on it)
```

#### When will the rules are updated?
Between 0200 and 0600 hours every day, Croissants will do the housekeeping and updating.  The defending work of Croissants may be interrupted during this perid.  Outdated logs will be deleted at 0200 hours.  All blacklists will be updated at 0300 hours.  Croissants will be updated at 0400 hours (when necessary).  All rules will be updated at 0500 hours.  Ubuntu will be updated at 0600 hours (it will auto reboot when necessary).  

### 6.0 To-Do-List

Nil

### 7.0 See Also

[Minisforum Elitemini HM80](https://store.minisforum.com/collections/all-product/products/minisforum-hm80) is a Mini PC that ideal for home based or SOHO based Intrusion Detection and Prevention System (IDPS).  An external USB Ethernet dongle is required for the management purpose.  It comes with AMD Ryzen R7-4800U (8-core with 16 threading) CPU and the memory can be up to 64GB.

When installing Linux with USB dongle, you are required to use Front Panel USB ports instead of Rear ones.  You may need to add "iommu=soft" to the Grub in order to use the Rear Panel USB ports for the later.

[![](https://img.youtube.com/vi/TdmcRxU4ziY/0.jpg)](https://www.youtube.com/watch?v=TdmcRxU4ziY "MinisForum HM80 Unboxing")

[![](https://img.youtube.com/vi/X4MOUnOsA7Q/0.jpg)](https://www.youtube.com/watch?v=X4MOUnOsA7Q "Don't let this tiny PC fool you... it's faster than you think!")

[![](https://img.youtube.com/vi/LOLWCWHSDEA/0.jpg)](https://www.youtube.com/watch?v=LOLWCWHSDEA "This Tiny PC Is A Powerhouse! HM80 Ryzen 7 4800U Mini PC")

### 8.0 Bug Fixed

Since there is a bug in the kernel for 5.13.0 (5.13.0-25-generic and 5.13.0-27-generic [maybe newer]) of Ubuntu 20.04 HWE kernel, the box of AMD R7-4800U cannot be reboot or shutdown properly.  Therefore, we need to install the latest kernel (such as 5.16.x or newer) to fix the problem.  However, AMD R5-3500U does not affected.

```
[1.277717] BUG: kernel NULL pointer dereference, address: 000000000000000c
[    1.277720] #PF: supervisor write access in kernel mode
[    1.277722] #PF: error_code(0x0002) - not-present page
```

In order to install the kernel 5.16.x, you need to do the following steps :

```
sudo add-apt-repository -y ppa:tuxinvader/lts-mainline
sudo apt install -y linux-generic-5.16
```

You may need to insert the following in ```/etc/default/grub``` at ```GRUB_CMDLINE_LINUX_DEFAULT``` :

```
iommu.strict=1 iommu.passthrough=1
```
or
```
iommu=soft
```

After that, you need to run the following command before reboot the box :

```
sudo update-grub
sudo reboot
```

### 9.0 Known Issues

- [Bastille Post (巴士的報)](https://www.bastillepost.com/hongkong/) not loading properly under AMD R7-4800U CPU for unknown reason.

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
