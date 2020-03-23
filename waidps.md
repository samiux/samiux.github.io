|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# **WAIDPS 无线攻防**

# **Wireless Auditing, Intrusion Detection and Prevention System**

```Please be informed that when Wifi6 and WPA3 are in action, this tool is no longer effective!  This project is discontinued!```

## INTRODUCTION

WAIDPS (Wireless Auditing, Intrusion Detection and Prevention System) is written in Python 3 and working well on Penetration Testing distributions, such as Parrot Security OS 4.0.1 or later.  This is a multi-purpose tool that is designed for penetration testing as well as wireless intrusion detection and prevention.

It stores all wifi information that harvests from the surrounding.  Therefore, it is very useful for penetration testing especially for MAC address filtering and SSID hidden access points.

Meanwhile, it detects (1) association / authentication flooding, (2) mass deauthentication, (3) WEP and WPA/WPA2 as well as WPS attacks, (4) evil-twins and (5) rogue access points.

## BACKGROUND

This project is original created by SY Chua of SYWorks Programming. However, it is no longer maintained by him since 2014. The GitHub version is v1.0 R.6 and it is dated Oct 10, 2014. Meanwhile, the demonstration in his tutorials and Youtube videos are displayed v1.0 R.7 dated Oct 11, 2014.  It is considered as abandoned project.

On the other hand, this software is a very good design in screen layout and good operation experience. Since v1.0 R.6 will crash especially when handshake is captured and it is not working properly on Kali Linux 2017.2,  Samiux fixed the problems and ported to Python 3.  It also support IEEE 802.11ac (2.4 and 5 GHz bands).

## LICENSE

This project is an open source project and it is released under GPLv3 by Samiux.

## OPERATING SYSTEM

It is well tested on Parrot Security OS 4.0.1. Other penetration testing Linux distributions may work too.  However, it does not compatible with Kali Nethunter.

[![](https://img.youtube.com/vi/woM5X_xkExk/0.jpg)](https://www.youtube.com/watch?v=woM5X_xkExk)

## CHANGELOG

### Version 1.0 R.6a (2017-10-19)  
[+] Fork from GitHub SYWorks v1.0 R.6  
[+] Fix for Kali Linux 2017.2  
[+] Fix for Realtek 8812au wireless USB dongle and older  
[+] Fix for scanning IEEE 802.11ac/n/b/g devices  
[+] Some minor bug fixes  

### Version 1.0 R.6b (2017-10-20)  
[+] Fix for crashes when handshake is captured  
[+] Some minor bug fixes  

### Version 1.0 R.6c (2017-12-03)  
[+] Kill processes at the beginning  

### Version 1.0 R.6d (2017-12-05)  
[+] Fix for Github and newer version (aireplay-ng display) (waidps2.py)  
  
### Version 1.0 R.6e (2017-12-14)  
[+] Fix handshake subroutine on Python 3 script  
[+] Add Python 3 support for different script (waidps3.py)  

### Version 1.0 R.6f (2017-12-16)  
[+] Fix handshake subroutine on Python 3 script  
[+] Minor improvement  

### Version 1.0 R.6g (2017-12-17)  
[+] Code clean up  
[+] Minor improvement  

### Version 1.0 R.6h (2017-12-19)  
[+] Fix undetectable unicode crash on Python 3 script  
[+] Minor fix on Python 3 script  

### Version 1.0 R.6i (2017-12-23)  
[+] Fix unicode SSID crash on handshake is captured on Python 3 script  

### Version 1.0 R.6j (2018-05-28)  
[+] Fix for Aircrack-NG 1.2  

### Version 1.0 R.6k (2020-03-23) [Stable]  
[+] Fix channel for 5GHz  

## FILE DESCRIPTION

waidps_2.4GHz.py - Python 3 script for Aircrack-NG 1.2 (2.4GHz only)  
waidps_5GHz.py - Python 3 script for Aircrack-NG 1.2 (5GHz only)  

## INSTALLATION

```bash
sudo apt install python-crypto git
```

```bash
git clone https://github.com/samiux/waidps

cd waidps

sudo python3 waidps_2.4GHz.py

(sudo ./2.4)
```

or

```bash
sudo python3 waidps_5GHz.py

(sudo ./5)
```

Follow the instruction on screen to install the required files.  It will then run the program directly.

Please leave it scanning for several minutes (warm up) before continue the operation.

You can run it at ```~/waidps/``` as ```root``` and all the captured files are at ```/root/.SYWorks/Saved/``` directory.

On every update, please copy the new script(s) to ```/root/.SYWorks/WAIDPS/``` to make sure the script is working properly.

```bash
sudo cp ~/waidps/*.py /root/.SYWorks/WAIDPS/
```

## BASIC REQUIREMENTS

- Kernel module mac80211 should be patched for Packet Injection  
- Wireless card or dongle can be in Monitor mode  
- Wireless card or dongle driver can Packet Injection  
- Wireless card or dongle driver should be supported by Linux  
- Targets wireless signal better not below than 20% ( or -80 dbm)  
- Attacker and target should be in the same mode  
- At least one client is associated  

## TESTED HARDWARE

### Fully Compatible  
[+] TP-Link TL-WN321G (G mode) [Fully compatible]  
[+] PCi GW-US54Mini (G mode) [Fully compatible]  

[+] Intel  Centrino Ultimate-N 6300 (N mode) [Fully compatible]  
[+] Intel PRO/Wireless 5100 AGN (N mode) [Fully compatible]  
[+] TP-Link TL-WN821N (N mode) [Fully compatible]  

[+] TP-Link Archer T4UHP AC1300 (AC mode) [Fully compatible]  

### Partially Compatible  
[!] TP-Link TL-WN822N (N mode) [Partially compatible]  
[!] TP-Link Archer T9UH AC1900 (AC mode) [Partially compatible]  

### Not Tested  
[?] ALFA AWUS1900 (AC mode) (Not tested)  
[?] Intel Wireless 3160 (AC mode) (Not tested but reported not working)  
[?] ALFA AWUS036ACH (AC mode) (Not tested but reported working)  

### Not Compatible  
[-] D-Link DWA-131 (G mode) [Not compatible]  
[-] ALFA AWUS036NHR (N mode) [Not compatible]  

## FAQ

Q : Why does deauthentication not working?

A : There can be several reasons and one or more can affect you :

- You are physically too far away from the access points and/or client(s). You need enough transmit power for the packets to reach and be heard by the access points and clients. If you do a full packet capture, each packet sent to the client should result in an “ack” packet back. This means the client heard the packet. If there is no “ack” then likely it did not receive the packet.

- Wireless cards work in particular modes such a, b, g, n and ac. If your card is in a different mode than the client card, there is good chance that the client will not be able to correctly receive your transmission. See the previous item for confirming the client received the packet.

- Some clients ignore broadcast deauthentications. If this is the case, you will need to send a deauthentication directly to the particular client.

- Clients may reconnect too fast for you to see that they had been disconnected. If you do a full packet capture, you will be able to look for the reassociation packets in the capture to confirm deauthentication worked.

- When IEEE802.11w (Protected Management Frames) is enabled, access points and clients will ignore the deauthentication and deassociation packets.

- When client is switching channel on a dual band router for better connection speed, you may not catch the client at the right channel.

- When client is busy in transferring data, it may not response to the deauthentication packets.
<br>
- When client is too idle, it may not response to the deauthentication packets.

## TO-DO-LIST

[+] Test WPS attack  
[+] Test WEP attack  

## REFERENCE

[1] This project is forked from [SYWorks](https://github.com/SYWorks/waidps)  
[2] [Official tutorial - Part 1](http://syworks.blogspot.hk/2014/04/waidps-wireless-auditing-intrusion.html)  
[3] [Official tutorial - Part 2](http://syworks.blogspot.hk/2014/04/waidps-wireless-auditing-intrusion_24.html)  
[4] [Official tutorial - Part 3](http://syworks.blogspot.hk/2014/04/waidps-wireless-auditing-intrusion_25.html)  
[5] [Official tutorial - Part 4](http://syworks.blogspot.hk/2014/06/waidps-wireless-auditing-intrusion.html)  
[6] [Official Youtube Playlist](https://www.youtube.com/watch?v=aGTQAWoeujA&index=1&list=PLrekpjW7JwW-T0CeXP8GwudtJmTJ6KZ8O)  
[7] [RealTek 8812AU Driver Installation](https://samiux.blogspot.com/2017/10/howto-install-realtek-8812au-driver.html)  
[8] [TP-Link Archer T4UHP (Realtek 8812AU chipset)](http://www.tp-link.com/us/products/details/cat-5520_Archer-T4UHP.html)  
[9] [ALFA AWUS036ACH (Realtek 8812AU chipset)](https://www.alfa.com.tw/service_1_detail/13.htm)  
[10] [ALFA AWUS1900 (Realtek 8814AU chipset)](https://www.alfa.com.tw/service_1_detail/15.htm)  
[11] [TP-Link Archer T9UH (Realtek 8814au chipset)](http://www.tp-link.com/us/products/details/cat-5520_Archer-T9UH.html)  
[12] [HOWTO : Install HashCat on Ubuntu 16.04.3](https://samiux.blogspot.com/2017/12/howto-install-hashcat-on-ubuntu-16043.html)  
[13] [HOWTO : Wifi Penetration Testing Without Tear](https://samiux.blogspot.com/2017/12/howto-wifi-penetration-testing-without.html)  
[14] [HOWTO : Wifi Intrusion Detection Without Tears](https://samiux.blogspot.com/2017/12/howto-wifi-intrusion-detection-without.html)  
[15] [[RESEARCH] How Secure Of Your Wifi Netowrk](https://samiux.blogspot.com/2018/05/research-how-secure-of-your-wifi-netowrk.html)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
