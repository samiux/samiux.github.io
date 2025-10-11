# Most Secure and Clean Internet Connection

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

## Intrusion Detection and Prevention System (IDPS) for Mobile Devices

If you have an IDPS at office or home, you may consider to have an IDPS on your smartphone or tablet as well as your laptop.  The easiest and fastest way is to setup an OpenVPN Access Server on your x86 hardware.  Then connection via it with OpenVPN Connect 3 and it is available for Windows, macOS, iOS, Android and ChromeOS.

However, OpenVPN Access Server is not free when you need more than 2 connections at the same time.

To set it up just follows the instruction on this [tutorial](https://samiux.github.io/openvpn_as.html) and set the Access Server to be connected without encryption.

```
VPN Server --> Security / Encryption 

TLS control channel security -- Disabled (not recommended)
```

Set the OpenVPN Access Server for High Proiority in QoS at your router that may boost your VPN speed a lot.

## Pi-Hole for Cleaner Internet Connection

To remove ads and malicious domains besides IDPS, you need to have a Pi-Hole setup on your network.  It is very easy to do so.  Just follows the instruction on this [tutorial](https://samiux.github.io/casaos_pi-hole_unbound.html) or this [tutorial](https://samiux.github.io/pi-hole_unbound.html).

Set the Pi-Hole for High Priority in QoS at your router and allows ```dns.weixin.qq.com.cn``` when you need to surf Weixin or websites in China at Pi-Hole that may boost your internet speed a lot.

## Headless Anti Malware with Wazuh and VirusTotal

Monitoring any new file in the directories/folders and inspecting any malicious file as well as removing it automatically in your network.

To set it up just follows this [tutorial](https://samiux.github.io/wazuh_virustotal.html)  

## Diagram of the Home Network Configuration

```
                                    Internet
                                       |
                                       |
                                     Modem
                                       | 
                                       |
                          +---------- IDPS (Suricata)  
                          |            |
                          |            | (WAN)
                          |            |
                          |        Wifi Router --- Phones/Tablets/IoTs
                          |            |  
                    (LAN) |            | (LAN)
                          |            |
                          |            |             (SPAN)
                          |      Mirroring Switch ----------- IDS (Suricata)
                          |            |             
                          |            |
                          +--------- Switch
                                       |
                                       |
                   +----------+--------+--------+----------+
                   |          |                 |          |
                   |          |                 |          |
                 Wazuh     OpenVPN           Pi-Hole   Computers/Servers
                         Access Server         DNS

```

## Conclusion

When your network is equipped with IDPS, Pi-Hole and Wazuh, you have a more secure and cleaner internet connection for your devices, including mobile devices.

For IDPS, I recommended to setup with Suricata.  It is an open source project and it can run on x86 and Arm devices.

For OpenVPN Access Server, you are required to use x86 hardware and Linux with the latest kernel.  It is available to Windows, Linux, macOS, iOS and Android.

For Pi-Hole, it is an open source project and it is compatible to x86 and Arm devices.

For Wazuh, it is open source project and it is very easy to set up.  It is compatiable to x86 and Arm hardwares.  However, it is available to Windows, Linux and macOS only.

Happy surfing internet in a more secure and cleaner way!

## Reference

- [Suricata - Intrusion Detection and Prevention System](https://suricata.io/)    
- [OpenVPN Access Server](https://openvpn.net/access-server/)    
- [Pi-Hole - Network-wide Ad Blocking](https://pi-hole.net/)    
- [Wazuh - The Open Source Security Platform](https://wazuh.com/)    
- [VirusTotal](https://www.virustotal.com/gui/home/upload)    
- [Deployment of OpenVPN Access Server with 2 Connections Free](https://samiux.github.io/openvpn_as.html)    
- [Setting up Pi-Hole & Unbound with CasaOS on Ubuntu 24.04.3 LTS](https://samiux.github.io/casaos_pi-hole_unbound.html)    
- [Pi-Hole & Unbound on Debian 12 (Bookworm)](https://samiux.github.io/pi-hole_unbound.html)    
- [Headless Anti Malware with Wazuh and VirusTotal](https://samiux.github.io/wazuh_virustotal.html)     

Samiux    
OSCE  OSCP  OSWP     
October 04, 2025, Hong Kong, China    

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
