|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# **Shumai 烧卖 - Intrusion Detection and Prevention System**

When your laptop is connecting to the internet directly, it opens to the public facing hacker attacks from all over the world every day.  Once we are compromised, we would be one of the cyber crime victims.  Our tasty Shumai is a high performance and ultra-low latency Intrusion Detection and Prevention System (IDPS).  Unlike well known and famous brands for large business enterprises in the market, Shumai is available free of charge that everyone can afford.  It is ideal for home, Small Office Home Office (SOHO) and Small Medium Business (SMB).

Since laptop is a mobile device, the rules for Shumai should be as few as possible in order to reduce the loading time.  Therefore, the rules are custom made for the purpose and provides necessary protection to the laptop.

# FEATURES

- Blocks known malicious activities  
- Compatible with Bittorrent and 4K video streaming  
- Ultra-low latency for demanding online games  
- Compatible with Ubuntu Desktop 20.04 LTS  
- No subscription fee  
- Plug, Play and Forget!  

# LICENSE

Shumai is an Open Source Project which is released under GPLv3 License and it is developed by Samiux.

Please keep in mind that Shumai is available 	FREE OF CHARGE.

# MINIMUM REQUIREMENTS

## Hardware

- Multi-Core Intel / AMD x86 CPU  
- 8GB DDR4 RAM or more  
- 256GB hard drive or more  
- 1 Network Interface Card/Port   
- CPU with AVX2 or better (at least SSSE3)  

## Software

- Ubuntu Desktop 20.04 LTS (64-bit) (End of Life on April 2025)

# MAIN COMPONENTS

- Suricata 5.0.3  
- Hyperscan 5.2.1 (Ubuntu 20.04)  

# DOCUMENTATION

## 1.0 Installation Guide

### 1.1 Download and Install

```bash
sudo -i

cd /root

git clone https://github.com/samiux/shumai

cd shumai

cp * /root

cd /root

nano nsm.conf

chmod +x nsm_install

./nsm_install
```

**Make sure you edit ```nsm.conf``` before running ```nsm_install```

The definition of nsm.conf is [here](https://samiux.github.io/nsmconf-hidps).

### 1.2 ChangeLog

[Shumai ChangeLog](https://samiux.github.io/changelog)

## 2.0 Useer Guide

### 2.1 Glances

Text mode monitoring tool for the performance of Shumai.

```bash
glances
```

### 2.2 Suricata Health Check

```bash
sudo tail -f /var/log/suricata/stats.log | grep drop
```

Press ```CTRL+c``` to exit.

### 2.3 Suricata Event Log

```bash
sudo tail -f /var/log/suricata/fast.log
```

Press ```CTRL+c``` to exit.

### 2.4 Rules Management

If you want to disable some rules as they are false positive, you can edit the “disable.conf” of suricata-update.

```bash
sudo nano /etc/suricata/disable.conf
```

If you want to drop some traffic, you can edit the “drop.conf” of suricata-update.

```bash
sudo nano /etc/suricata/drop.conf
```

If you want to modify some rules, you can edit the “modify.conf” of suricata-update.

```bash
sudo nano /etc/suricata/modify.conf
```

After updated the configuration files, you should run the following command to make the changes effective.

```bash
sudo nsm_rules_update
```

### 2.5 Ubuntu Update

```bash
sudo update_ubuntu
```

### 2.6 Auto Configuration

Whenever you changed the nsm.conf file, you need to run the following command in order to make it effective.

```bash
sudo nano /etc/croissants/conf.d/nsm.conf

sudo /etc/croissants/conf.d/auto_config
```

### 2.7 Suricata Performance

To check the performance of suricata :

```bash
sudo apt install linux-tools-generic
```

Then run :

```bash
sudo perf top -p $(pidof suricata)
```

### 2.8 Logs Clean Up

To delete related log files :

```bash
sudo nsm_cleanlogs
```

The item(s) that in red colour may be in issue.

## 3.0 Troubleshooting

If you cannot access internet when you are behind the Shumai, Suricata may be down unexpectedly. You can check if it is running or not by the following command :

```bash
sudo ps aux | grep suricata
```

If it is not running, you can issue the following command to start it :

```bash
sudo systemctl restart suricata
```

You can check the suricata.log at ```/var/log/suricata/suricata.log```. Please allow about 15 minutes for Suricata fully starting.

## 4.0 To-Do-List

Nil

## 5.0 See Also

Nil

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
