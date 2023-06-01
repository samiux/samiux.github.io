|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Garlic 大蒜 - Intrusion Detection and Prevention System  防御入侵系统 (Personal Computer)

Networks and computers that are opened to the public facing hacker attacks from all over the world every day.  Once we are compromised, we would be one of the cyber crime victims.  Our tasty Garlic is a high performance and ultra-low latency Intrusion Detection and Prevention System (IDPS).  Unlike well known and famous brands for large business enterprises in the market,  Garlic is available free of charge that everyone can afford.  It is ideal for home, Small Office Home Office (SOHO) and Small Medium Business (SMB).

Not a Network Security Monitoring (NSM) or Information Security (InfoSec) expert?  No problem!  Our Garlic really is the "Plug, Play and Forget" system of your dreams.  Don't be the next cyber crime victims, try Garlic now!

Garlic is designed by a hacker to defend against hackers. He knows what hackers are doing and thinking, regardless of whether they are ethical or malicious.

## FEATURES

- Blocks known malicious activities  
- Blocks known malware  
- Easy and straight forward interfaces  
- Compatible with Bittorrent and 4K video streaming  
- Ultra-low latency for demanding online games  
- Compatible with Ubuntu Linux Desktop 
- No subscription fee  
- Automatically update and upgrade  
- Plug, Play and Forget!  

每当电脑或网络连接互联网时，我们的电脑或网络就有机会被恶意黑客的攻击。为免成为下一个网络罪行的受害者，我们美味的大蒜可以助你免于被袭击。不像其他知名的商业品牌，她是完全免费，每个人都能够负担的入侵防御系统。

我们的大蒜是随插即用，用户的参与性极少，适合一般大众使用。

大蒜是由黑客设计来对付黑客的有效工具，不论其为道德黑客抑或是恶意黑客。

## 功能概览

- 有效阻挡已知的恶意行为
- 有效阻挡已知的恶意程序
- 简单直接的用户介面
- 极低的延迟性能有效地播放 4K 多媒体和玩要求速度的网络游戏
- 兼容 Ubuntu Linux 桌面电脑
- 开源项目，完全免费
- 自动更新
- 随插即用，并且可以忘记之

## LICENSE

Garlic is an Open Source Project which is released under GPLv3 License and it is developed by Samiux.

Please keep in mind that Garlic is available FREE OF CHARGE.

__Garlic is designed and developed by Samiux based on Croissants (Croissants since 2012).__

## MINIMUM REQUIREMENTS

### Hardware

- Multi-Core Intel / AMD x86-64 CPU    
- 8GB DDR4 RAM or more (Garlic use at least 2GB RAM)  
- 256GB hard drive or more (SSD for better performance)   
- 1 Network Interface Card/Port   
- CPU with AVX2 or AVX512 (at least SSSE3 or SSE4.2)  
- More cores and faster CPU the better performance  

### Software

- Ubuntu Desktop 22.04 LTS (64-bit) (support until April 2027)  

## MAIN COMPONENTS

- Suricata 6.0.12  
- Hyperscan 5.4.0 (Ubuntu 22.04)    

## DOCUMENTATION

### 1.0 Installation Guide

#### 1.1 Download and Install

```bash
sudo -sH

cd /root

sudo apt install git net-tools

git clone https://github.com/samiux/garlic

```

```bash
cd /root/garlic

cp -R rules/ /root
cp * /root

cd /root

nano nsm.conf

chmod +x nsm_install

sudo ./nsm_install
```

__Make sure you edit ```nsm.conf``` before running ```nsm_install```__

#### 1.2 ChangeLog

[Garlic ChangeLog](https://github.com/samiux/samiux.github.io/blob/master/garlic_changelog.md)   

### 2.0 User Guide

#### 2.1 Glances

Text mode monitoring tool for the performance of Taro.

```bash
glances
```

#### 2.2 Suricata Health Check

```bash
sudo tail -f /var/log/suricata/stats.log | grep drop
```

Press ```CTRL+c``` to exit.

#### 2.3 Suricata Event Log

```bash
sudo tail -f /var/log/suricata/fast.log
```

Press ```CTRL+c``` to exit.

#### 2.4 Rules Management

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

#### 2.5 Ubuntu Update

```bash
sudo update_ubuntu
```

#### 2.6 Auto Configuration

Whenever you changed the nsm.conf file, you need to run the following command in order to make it effective.

```bash
sudo nano /etc/croissants/conf.d/nsm.conf

sudo /etc/croissants/conf.d/auto_config
```

### 3.0 Hall of Fame

N/A

### 4.0 Troubleshooting

If you cannot access internet when you are behind the Taro, Suricata may be down unexpectedly.  You can check if it is running or not by the following command :

```bash
sudo ps aux | grep suricata
```

If it is not running, you can issue the following command to start it :

```bash
sudo systemctl restart suricata
```

You can check the suricata.log at ```/var/log/suricata/suricata.log```.  Please allow about 5 minutes for Suricata fully starting.

### 5.0 Uninstall

```
sudo -sH
cd /root
chmod +x garlic_uninstaller
sudo ./garlic_uninstaller
```
Then reboot your personal computer.

### 6.0 FAQ

#### (1) When will the rules be updated?

The update will be carried out within 15 minutes when the Garlic is booting up.  If you turn off the Garlic within 15 minutes of the booting up, you may also break the system too.    
    
#### (2) How many detecting / blocking rules in Garlic?  
There are more than 40,000 rules in Garlic and they are all free of charge.  The number of rules are increasing.    

#### (3) Can Garlic decrypt the SSL/TLS traffic?
Garlic cannot decrypt the SSL/TLS traffic well.  However, it can handle a limited SSL/TLS traffic flow.  Therefore, it is not ideal for using it as Web Application Firewall (WAF).  For example, Garlic can detect and drop self signed SSL/TLS certificate traffic and etc.   

#### (4) How about Garlic is turned off for a week or longer?
It is recommended to run the install script once again to keep the Garlic up-to-date.  

### 7.0 To-Do-List

#### 7.1 Upgrade to Ubuntu Desktop 24.04 LTS 

N/A

### 8.0 See Also

Besides, your desktop is required to be hardening on SSH and other applications, etc when necessary.  It is because that Garlic is not a silver bullet.  Garlic is running behind router or Wifi router as well as Wifi hotpot.

### 9.0 Bug Fixed

N/A

### 10.0 Known Issues

N/A  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
