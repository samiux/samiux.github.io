|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Taro 芋头 - Intrusion Detection and Prevention System  防御入侵系统 (Server)

Networks and computers that are opened to the public facing hacker attacks from all over the world every day.  Once we are compromised, we would be one of the cyber crime victims.  Our tasty Taro is a high performance and ultra-low latency Intrusion Detection and Prevention System (IDPS).  Unlike well known and famous brands for large business enterprises in the market,  Taro is available free of charge that everyone can afford.  It is ideal for home, Small Office Home Office (SOHO) and Small Medium Business (SMB).

Not a Network Security Monitoring (NSM) or Information Security (InfoSec) expert?  No problem!  Our Taro really is the "Plug, Play and Forget" system of your dreams.  Don't be the next cyber crime victims, try Taro now!

Taro is designed by a hacker to defend against hackers. He knows what hackers are doing and thinking, regardless of whether they are ethical or malicious.

## FEATURES

- Blocks known malicious activities  
- Blocks known malware  
- Easy and straight forward interfaces  
- Compatible with Bittorrent and 4K video streaming  
- Ultra-low latency for demanding online games  
- Compatible with Ubuntu Linux Server  
- No subscription fee  
- Automatically update and upgrade  
- Plug, Play and Forget!  

每当电脑或网络连接互联网时，我们的电脑或网络就有机会被恶意黑客的攻击。为免成为下一个网络罪行的受害者，我们美味的芋头可以助你免于被袭击。不像其他知名的商业品牌，她是完全免费，每个人都能够负担的入侵防御系统。

我们的芋头是随插即用，用户的参与性极少，适合一般大众使用。

芋头是由黑客设计来对付黑客的有效工具，不论其为道德黑客抑或是恶意黑客。

## 功能概览

- 有效阻挡已知的恶意行为
- 有效阻挡已知的恶意程序
- 简单直接的用户介面
- 极低的延迟性能有效地播放 4K 多媒体和玩要求速度的网络游戏
- 兼容 Ubuntu Linux 服务器 
- 开源项目，完全免费
- 自动更新
- 随插即用，并且可以忘记之

## LICENSE

Taro is an Open Source Project which is released under GPLv3 License and it is developed by Samiux.

Please keep in mind that Taro is available FREE OF CHARGE.

__Taro is designed and developed by Samiux based on Croissants (Croissants since 2012).__

## MINIMUM REQUIREMENTS

### Hardware

- Multi-Core Intel / AMD x86-64 CPU    
- 8GB DDR4 RAM or more (Taro use at least 2GB RAM)  
- 256GB hard drive or more (SSD for better performance)   
- 1 Network Interface Card/Port   
- CPU with AVX2 or AVX512 (at least SSSE3 or SSE4.2)  
- More cores and faster CPU the better performance  

### Software

- Ubuntu Server / Desktop 22.04 LTS (64-bit) (support until April 2027)  

## MAIN COMPONENTS

- Suricata 6.0.13  
- Hyperscan 5.4.0 (Ubuntu 22.04)    

## DOCUMENTATION

### 1.0 Installation Guide

#### 1.1 Download and Install

```bash
sudo -sH

cd /root

sudo apt install git net-tools

git clone https://github.com/samiux/taro

```

```bash
cd /root/taro

cp -R rules/ /root
cp * /root

cd /root

nano nsm.conf

chmod +x nsm_install

sudo ./nsm_install
```

__Make sure you edit ```nsm.conf``` before running ```nsm_install```__

#### 1.2 ChangeLog

[Taro ChangeLog](https://github.com/samiux/samiux.github.io/blob/master/taro_changelog.md)  

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

### 5.0 FAQ

#### (1) When will the rules be updated?

##### 24/7
Between 0200 and 0600 hours every day, Taro will do the housekeeping and updating.  The defending work of Taro may be interrupted during this period.  Outdated logs will be deleted at 0200 hours.  All blacklists will be updated at 0300 hours.  Taro will be updated at 0400 hours (when necessary).  All rules will be updated at 0500 hours.  Ubuntu will be updated at 0600 hours (it will auto reboot when necessary).  

##### non 24/7
Taro can be turned off and it is not required to operate 24/7.  The update will be carried out within half an hour when the Taro is booting up.  The Taro may be reboot itself when necessary.  It is advised not to turn off the Taro between 0300 and 0600 hours as it will do the update automatically.  If you do so, you may break the Taro.  Meanwhile, if you turn off the Taro within half an hour of the booting up, you may also break the system too.    
    
#### (2) How many detecting / blocking rules in Taro?  
There are more than 40,000 rules in Taro and they are all free of charge.  The number of rules are increasing.    

#### (3) Can Taro decrypt the SSL/TLS traffic?
Taro cannot decrypt the SSL/TLS traffic well.  However, it can handle a limited SSL/TLS traffic flow.  Therefore, it is not ideal for using it as Web Application Firewall (WAF).  For example, Taro can detect and drop self signed SSL/TLS certificate traffic and etc.   

#### (4) How about Taro is turned off for a week or longer?
It is recommended to run the install script once again to keep the Taro up-to-date.  

### 6.0 To-Do-List

#### 6.1 Upgrade to Ubuntu Server / Desktop 24.04 LTS 

N/A

### 7.0 See Also

Besides, your server or desktop is required to be hardening on SSH, Web application and other applications, etc when necessary.  It is because that Taro is not a silver bullet.  

### 8.0 Bug Fixed

N/A

### 9.0 Known Issues

N/A  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

