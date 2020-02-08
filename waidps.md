# **WAIDPS 无线攻防**

# **Wireless Auditing, Intrusion Detection and Prevention System**


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
