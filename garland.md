|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Garland 茼蒿 - Intrusion Detection and Prevention System  防御入侵系统

Networks and computers that are opened to the public facing hacker attacks from all over the world every day.  Once we are compromised, we would be one of the cyber crime victims.  Our Garland is a high performance and ultra-low latency Intrusion Detection and Prevention System (IDPS).  Unlike well known and famous brands for large business enterprises in the market,  Garland is available free of charge that everyone can afford.  It is ideal for home and Small Office Home Office (SOHO). 

Not a Network Security Monitoring (NSM) or Information Security (InfoSec) expert?  No problem!  Our Garland really is the "Plug, Play and Forget" system of your dreams, it is totally transparent.  Don't be the next cyber crime victims, try Garland now!

Garland is designed by a hacker to defend against hackers. He knows what hackers are doing and thinking, regardless of whether they are ethical or malicious.

每当电脑或网络连接互联网时，我们的电脑或网络就有机会被恶意黑客的攻击。为免成为下一个网络罪行的受害者，我们的「茼蒿」可以助你免于被袭击。不像其他知名的商业品牌，她是完全免费，每个人都能够负担的入侵防御系统。

我们的「茼蒿」是随插即用，用户的参与性极少，适合一般大众使用。

「茼蒿」是由黑客设计来对付黑客的有效工具，不论其为道德黑客抑或是恶意黑客。

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

## 功能概览

- 有效阻挡已知的恶意行为
- 简单直接的用户介面
- 极低的延迟性能有效地播放 4K 多媒体和玩要求速度的网络游戏
- 兼容微软视窗、苹果电脑、Linux 及 Apple iOS、Google Android、Huawei HarmonyOS 等各大移动系统
- 开源项目，完全免费
- 自动更新
- 随插即用，并且可以忘记之
- 完全透明
- 无需设定

## HARDWARE

### NanoPI R5S

- 4 cores ARM CPU (Quad-core ARM Cortex™-A55)  
- 4GB RAM  
- 16GB eMMC  
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

Download [Balena Etcher](https://www.balena.io/etcher) at its official site and burn the image to the SD Card.  Then boot the NanoPi R5S with the SD Card.  Therefore, faster the SD Card is better the performance.  

## 安装

你需要一张至少 16GB (规格 10) 的 SD 卡。

从[谷歌云盘](<https://drive.google.com/file/d/1jaNzXoQWMmv-Zflq06MMymNNIJHl6JFn/view?usp=sharing>)下载镜像文件，然后解压文件。

从 [Balena Etcher](https://www.balena.io/etcher) 官网下载，并将镜像文件烧录到 SD 卡中，再将 SD 卡启动 NanoPi。所以速度快的 SD 卡在效能上较为占优。

### Checksum

sha256 fe20c8782dfc953e7610e4b968d00b2385ba1ca317ec78b1a213a2251d17e19a  rk3568-r5s-sd-garland-6.0.10-5.10-arm64-20230307.zip  
sha256 22cb018b29579263c9f6fdfc732d9790abefdffbfca3ce50749d0d7939fb28bf  rk3568-r5s-sd-garland-6.0.10-5.10-arm64-20230307.img  

## LICENSE

Garland is developed by Samiux based on Croissants project which is since 2012 and it is released under GPLv3 and FREE OF CHARGE.  

## 版权

「茼蒿」是由 Samiux 基于他另一个开源项目「牛角面包」开发，该项目始于 2012 年。「茼蒿」亦是一项基于 GPLv3 的开源项目。

## DEPLOYMENT  

The following is the recommended connection method of Garland.  However, you can connect it behind router too.

建议将防御入侵系统放置于路由器之前，但亦可以放置在路由器之后。
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
            (LAN1)           (LAN2 to Router's WAN)     (Switch's LAN)          |
   Modem ----------- Garland ------------------ Router -------- Switch ---------+
                          |                      (WIFI)             |           |
                          |                                         |           |
                          +-----------------------------------------+           +------- PCs
                                   (WAN to Switch's LAN)

```
```bash
                                                                    +------- WIFI AP
                                                                    |
            (LAN1)          (LAN2 to Switch Port #1)                |
5G Modem ----------- Garland ------------------ Switch -------------+
WIFI Router (unused)      |                        |                |
                          |                        |                |
                          +------------------------+                +------- PCs & Laptops
                            (WAN to Switch's LAN)

```

Do NOT use the wifi that comes with 5G modem as the traffic flow will NOT be protected by Garland.

不要使用 5G 调解器的无线网络，因为其无线网络不受「茼蒿」的保护。

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

## 常问问题

### 何时会更新防御入侵系统的规则？

#### 全日运作

每日的凌晨 0600 至 0630 时更新和维护，其间有可能对防御入侵系统的运作有些少影响。

#### 非全日运作

每当启动后的半小时内其会自行更新维护，所以不要在其间或在 0600 至 0630 时其间内关闭防御入侵系统，因为有可能会损坏防御入侵系统。

### 防御入侵系统内有多少条规则？

所有规则都是免费的，已经超过 4 万 6 千多条，而且亦每日在增加中。

### 是否建议在互联网中利用 SSH 接驳防御入侵系统？

不建议，但可以在内网连接。其用户名称和密码都是 "garland"。至于网址是 192.168.x.200，例如 192.168.0.200。

### 防御入侵系统是否能够解密所有加密的连接？

不能。但她能够识别及阻挡自签 SSL/TLS 证书的流量。

### 我仍是否需要在电脑上安装防毒软件？

需要。除此之外，我更建议在「火狐」或 Chrome 浏览器安装以下附加组件，使得上网时更安全。

- uBlock Origin  
- Ghostery  
- Malwarebytes Browser Guard  
- Avast Online Security & Privacy  
- MalwareAI Browser Security  
- VT4Browsers  

## KNOWN ISSUES

Since there is no Real-Time-Clock battery in the device, you are required to reboot the device (__the FIRST boot of the burning SD Card__) after half an hour in order to get the current local time.  

## 已知问题

因为防御入侵系统没有时钟电池，所以在烧录后第一次开机时，应在半小时后重启一次就可以更正时钟了。

## REFERENCE

- [FriendlyElec NanoPi R5S Offical Site](https://www.friendlyelec.com/index.php?route=product/product&product_id=287)  
- [NanoPi R5S评测-全面超越R2S 配置全面 接口丰富 小白用户首选](https://www.youtube.com/watch?v=AMLvqHbQwMI)  

## SUPPORT

Discord @samiux#3445  

## SEE ALSO

- [Garland IDPS and 4K video playback]( https://youtu.be/3D4knrZNr8U)  
- [Rosemary 迷迭香 - Intrusion Detection and Prevention System (NanoPi R6S)](/rosemary.md)  
- [平价适合家用的防御入侵系统](/nanopi.md)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
