|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Garland 茼蒿 - Intrusion Detection and Prevention System  防御入侵系统

Networks and computers that are opened to the public facing hacker attacks from all over the world every day.  Once we are compromised, we would be one of the cyber crime victims.  Our Garland is a high performance and ultra-low latency Intrusion Detection and Prevention System (IDPS).  Unlike well known and famous brands for large business enterprises in the market,  Garland is available free of charge that everyone can afford.  It is ideal for home and Small Office Home Office (SOHO). 

Not a Network Security Monitoring (NSM) or Information Security (InfoSec) expert?  No problem!  Our Garland really is the "Plug, Play and Forget" system of your dreams, it is totally transparent.  Don't be the next cyber crime victims, try Garland now!

Garland is designed by a hacker to defend against hackers. He knows what hackers are doing and thinking, regardless of whether they are ethical or malicious.

## FEATURES

- Blocks known malicious activities  
- Compatible with Bittorrent and 4K video streaming  
- Ultra-low latency for demanding online games  
- Compatible with Microsoft Windows, GNU Linux, Apple macOS, Apple iOS, Google Android and Huawei HarmonyOS  
- No subscription fee  
- Automatically update  
- Plug, Play and Forget!  
- Totally transparent  
- Setup is not required   

## HARDWARE

### NanoPI R6S

- 4 cores ARM CPU (Quad-core ARM Cortex™-A55)  
- 4GB RAM  
- 16GB storge  
- 3 network interfaces (2 x 2.5Gbps, 1 x 1Gbps)   
- Max. power consumption 5W, fanless, no noise  
- Max. WAN traffic flow up to 2.5Gbps  
- 1 HDMI 2.0  
- 2 USB 3.0 Type-A  
- 1 SD Card Slot  
- Slightly larger than a credit card  
- 94.5mm (L) x 68mm (W) x 30mm (H)   

## IDPS ENGINE

- Suricata 6.0.10  

## INSTALLATION

A 16GB micro SD Card (at least Class 10) is required for the installation.  

Download the [SD Card image (564.6MB)](<https://drive.google.com/file/d/1jaNzXoQWMmv-Zflq06MMymNNIJHl6JFn/view?usp=sharing>) at Google Drive and extract it.

Download [Balena Etcher](https://www.balena.io/etcher) at its official site and burn the image to the SD Card.  Then boot the NanoPi R6S with the SD Card.  Therefore, faster the SD Card is better the performance.  

### Checksum

sha256 fe20c8782dfc953e7610e4b968d00b2385ba1ca317ec78b1a213a2251d17e19a  rk3568-r5s-sd-garland-6.0.10-5.10-arm64-20230307.zip  
sha256 22cb018b29579263c9f6fdfc732d9790abefdffbfca3ce50749d0d7939fb28bf  rk3568-r5s-sd-garland-6.0.10-5.10-arm64-20230307.img  

## LICENSE

Garland is developed by Samiux based on Croissants project which is since 2012 and it is released under GPLv3 and FREE OF CHARGE.  

## DEPLOYMENT  

The following is the recommended connection method of Garland.  However, you can connect it behind router too.

```bash
            (LAN1)             (LAN2 to Router's WAN)          (Router's LAN)          
   Modem ----------- Garland ----------------------- Router ----------------- PCs & Laptops
                          |                           (WIFI)                      
                          |                             | (Router's LAN)                   
                          +-----------------------------+
                              (WAN to Router's LAN)
```
```bash
                                                                                +------- Laptops
                                                                                |
            (LAN1)           (LAN2 to Router's WAN)     (Switch's LAN)           |
   Modem ----------- Garland ------------------ Router -------- Switch --------+
                          |                      (WIFI)             |           |
                          |                                         |           |
                          +-----------------------------------------+           +------- PCs
                                   (WAN to Switch's LAN)

```
```bash
                                                                    +------- WIFI AP
                                                                    |
            (LAN1)          (LAN2 to Switch Port #1)                 |
5G Modem ----------- Garland ------------------ Switch ------------+
WIFI Router (unused)      |                        |                |
                          |                        |                |
                          +------------------------+                +------- PCs & Laptops
                                    (WAN)

```

Do NOT use the wifi that comes with 5G modem as the traffic flow will NOT be protected by Garland.

## FAQ  

### When will the rules are updated?

#### 24/7
Between 0600 and 0630 hours every day, Garland will do the housekeeping and updating.  The defending work of Garland may be interrupted during this period.  

#### non 24/7
Garland can be turned off and it is not required to operate 24/7.  The update will be carried out within half an hour when the Garland is booting up.  It is advised NOT to turn off the Garland between 0600 and 0630 hours as it will do the update automatically.  If you do so, you may break the Garland.  Meanwhile, if you turn off the Garland within half an hour of the booting up, you may also break the system too.    

### How many detecting / blocking rules in Garland?  
There are over 46,000 rules in Garland and they are all free of charge.  The number of rules are increasing.    

### Do you recommend to access Garland via SSH in internet?
For security purpose, it is NOT recommended to connect Garland via SSH in internet.  However, you may connect Garland via SSH in intranet.  The username and password are "garland".  The IP address of the garland is 192.168.x.200, e.g. 192.168.0.200.  

### Can Garland decrypt the SSL/TLS traffic?
Garland cannot decrypt the SSL/TLS traffic well.  However, it can handle a limited SSL/TLS traffic flow.  Therefore, it is not ideal for using it as Web Application Firewall (WAF).  For example, Garland can detect and drop self signed SSL/TLS certificate traffic and etc.  

### Do I also need anti-virus on my computer or laptop?
Yes, anti-virus is required.  You are also advised to install the following add-ons or extensions for your browser such as Firefox or Chrome in order to increase the security for surfing the internet.

- uBlock Origin  
- Ghostery  
- Malwarebytes Browser Guard  
- Avast Online Security & Privacy  
- MalwareAI Browser Security  
- VT4Browsers  

## REFERENCE

- [FriendlyElec NanoPi R5S Offical Site](https://www.friendlyelec.com/index.php?route=product/product&product_id=287)  
- [NanoPi R5S评测-全面超越R2S 配置全面 接口丰富 小白用户首选](https://www.youtube.com/watch?v=AMLvqHbQwMI)  

## SUPPORT

Discord @samiux#3445  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
