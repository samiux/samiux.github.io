|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Kale 羽衣甘蓝 - Intrusion Detection System  侦测入侵系统 (Port Mirroring)

## Main Components

- Suricata 6.0.10  
- Hyperscan 5.4.0   
- Ubuntu Server 22.04 LTS  

## Hardware Requirement

- Management switch with port mirroring function  

## Features

- No UI, No overhead
- Log marked with "wDrop" is susposed to be blocked by rule  
- Auto update  
 
## License
 
Kale is released under GPLv3 and is developed by Samiux.

## Change Log

### Version 6.0.10.0 (Latest, Stable)  
Released on Feb 18, 2023 (GMT +8)  
- First released  

## Install

```bash
sudo -sH
cd /root
git clone https://github.com/samiux/kale
```

```bash
cd /root/kale
nano nsm.conf
chmod +x nsm_install
sudo ./nsm_install
sudo reboot
```

## Usage

```bash
sudo tail -f /var/log/suricata/fast.log | grep wDrop

sudo tail -f /var/log/suricata/fast.log
```
```
sudo cat /var/log/suricata/fast.log | grep wDrop

sudo cat /var/log/suricata/fast.log
```

## Deploy

```bash
                                                                            +------- WIFI AP
                                                                            |        (if any)
         (Incoming)             (Outgoing, WAN)           (LAN)             |
   Modem ----------- Croissants ---------------- Router -------- Switch ----+------- PCs
                          |                      (WIFI)             |       |
                          |                                         |       |
                          +-----------------------------------------+       +------- Kale (Port Mirroring)
                                         (Monitoring)

```

```bash
                                                                    +------- WIFI AP
                                                                    |
         (Incoming)            (Outgoing, Port #1)                  |
5G Modem ----------- Croissants ---------------- Switch ------------+------- PCs
WIFI Router (unused)      |                        |                |
                          |                        |                |
                          +------------------------+                +------- Kale (Port Mirroring)
                                 (Monitoring)

```
- where Croissants is an Intrusion Detection and Prevention System that developed by Samiux  
 
|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
