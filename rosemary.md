|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Rosemary 迷迭香 - Intrusion Detection and Prevention System  防御入侵系统

Networks and computers that are opened to the public facing hacker attacks from all over the world every day.  Once we are compromised, we would be one of the cyber crime victims.  Our Rosemary is a high performance and ultra-low latency Intrusion Detection and Prevention System (IDPS).  Unlike well known and famous brands for large business enterprises in the market,  Rosemary is available free of charge that everyone can afford.  It is ideal for home and Small Office Home Office (SOHO). 

Not a Network Security Monitoring (NSM) or Information Security (InfoSec) expert?  No problem!  Our Rosemary really is the "Plug, Play and Forget" system of your dreams, it is totally transparent.  Don't be the next cyber crime victims, try Rosemary now!

Rosemary is designed by a hacker to defend against hackers. He knows what hackers are doing and thinking, regardless of whether they are ethical or malicious.

每当电脑或网络连接互联网时，我们的电脑或网络就有机会被恶意黑客的攻击。为免成为下一个网络罪行的受害者，我们的「迷迭香」可以助你免于被袭击。不像其他知名的商业品牌，她是完全免费，每个人都能够负担的入侵防御系统。

我们的「迷迭香」是随插即用，用户的参与性极少，适合一般大众使用。

「迷迭香」是由黑客设计来对付黑客的有效工具，不论其为道德黑客抑或是恶意黑客。

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
- 极低的延迟性能有效地播放 4K 多媒体和玩要求速度的网络游戏
- 兼容微软视窗、苹果电脑、Linux 及 Apple iOS、Google Android、Huawei HarmonyOS 等各大移动系统
- 开源项目，完全免费
- 自动更新
- 随插即用，并且可以忘记之
- 完全透明
- 无需设定

## HARDWARE

### NanoPI R6S

- 8 cores ARM CPU (Quad-core ARM Cortex™-A76 & Quad-core ARM Cortex™-A55)  
- 8GB RAM  
- 32GB eMMC  
- 3 network interfaces (2 x 2.5Gbps, 1 x 1Gbps)   
- Max. power consumption 5W, fanless, no noise  
- Max. WAN traffic flow up to 2.5Gbps  
- 1 HDMI 2.0  
- 1 USB 3.0 Type-A, 1 USB 2.0 Type-A  
- 1 SD Card Slot  
- Slightly larger than a credit card  
- 96.5mm (L) x 68mm (W) x 30mm (H)   

## IDPS ENGINE

- Suricata 6.0.10  

## INSTALLATION

A 16GB micro SD Card (at least Class 10) is required for the installation.  

Download the [SD Card image (567.2MB)](<https://drive.google.com/file/d/1kYIPGmBi6KkwG1onPSI50WxiLOda9Zm6/view?usp=sharing>) at Google Drive and extract it.

Download [Balena Etcher](https://www.balena.io/etcher) at its official site and burn the image to the SD Card.  Then boot the NanoPi R6S with the SD Card.  Therefore, faster the SD Card is better the performance.  

## 安装

你需要一张至少 16GB (规格 10) 的 SD 卡。

从[谷歌云盘](<https://drive.google.com/file/d/1kYIPGmBi6KkwG1onPSI50WxiLOda9Zm6/view?usp=sharing>)下载镜像文件，然后解压文件。

从 [Balena Etcher](https://www.balena.io/etcher) 官网下载，并将镜像文件烧录到 SD 卡中，再将 SD 卡启动 NanoPi。所以速度快的 SD 卡在效能上较为占优。

### Checksum

sha256 f1b8593d0e189f26bc59d8cd8830099c8e4562ba8d4e1156326b99cdf3fed429  rk3588-r6s-sd-rosemary-6.0.10-5.10-arm64-20230307.zip  
sha256 e9ee789e9f298859499b14afdfa1738597d311f323c88f6d54834785304798ad  rk3588-r6s-sd-rosemary-6.0.10-5.10-arm64-20230307.img  

## LICENSE

Rosemary is developed by Samiux based on Croissants project which is since 2012 and it is released under GPLv3 and FREE OF CHARGE.  

## 版权

「迷迭香」是由 Samiux 基于他另一个开源项目「牛角面包」开发，该项目始于 2012 年。「迷迭香」亦是一项基于 GPLv3 的开源项目。

## DEPLOYMENT  

The following is the recommended connection method of Rosemary.  However, you can connect it behind router too.

建议将防御入侵系统放置于路由器之前，但亦可以放置在路由器之后。

```bash
            (WAN)             (LAN1 to Router's WAN)          (Router's LAN)          
   Modem ----------- Rosemary ----------------------- Router ----------------- PCs & Laptops
                          |                           (WIFI)                      
                          |                             | (Router's LAN)                   
                          +-----------------------------+
                              (LAN2 to Router's LAN)
```
```bash
                                                                                +------- Laptops
                                                                                |
            (WAN)           (LAN1 to Router's WAN)     (Switch's LAN)           |
   Modem ----------- Rosemary ------------------ Router -------- Switch --------+
                          |                      (WIFI)             |           |
                          |                                         |           |
                          +-----------------------------------------+           +------- PCs
                                   (LAN2 to Switch's LAN)

```
```bash
                                                                    +------- WIFI AP
                                                                    |
            (WAN)          (LAN1 to Switch Port #1)                 |
5G Modem ----------- Rosemary ------------------ Switch ------------+
WIFI Router (unused)      |                        |                |
                          |                        |                |
                          +------------------------+                +------- PCs & Laptops
                            (LAN2 to Switch's LAN)

```

Do NOT use the wifi that comes with 5G modem as the traffic flow will NOT be protected by Rosemary.

不要使用 5G 调解器的无线网络，因为其无线网络不受「迷迭香」的保护。

## FAQ  

### When will the rules are updated?

#### 24/7
Between 0600 and 0630 hours every day, Rosemary will do the housekeeping and updating.  The defending work of Rosemary may be interrupted during this period.  

#### non 24/7
Rosemary can be turned off and it is not required to operate 24/7.  The update will be carried out within half an hour when the Rosemary is booting up.  It is advised NOT to turn off the Rosemary between 0600 and 0630 hours as it will do the update automatically.  If you do so, you may break the Rosemary.  Meanwhile, if you turn off the Rosemary within half an hour of the booting up, you may also break the system too.    

### How many detecting / blocking rules in Rosemary?  
There are over 46,000 rules in Rosemary and they are all free of charge.  The number of rules are increasing.    

### Do you recommend to access Rosemary via SSH in internet?
For security purpose, it is NOT recommended to connect Rosemary via SSH in internet.  However, you may connect Rosemary via SSH in intranet.  The username and password are "rosemary".  The IP address of the Rosemary is 192.168.x.200, e.g. 192.168.0.200.  

### Can Rosemary decrypt the SSL/TLS traffic?
Rosemary cannot decrypt the SSL/TLS traffic well.  However, it can handle a limited SSL/TLS traffic flow.  Therefore, it is not ideal for using it as Web Application Firewall (WAF).  For example, Rosemary can detect and drop self signed SSL/TLS certificate traffic and etc.  

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

不建议，但可以在内网连接。其用户名称和密码都是 "rosemary"。至于网址是 192.168.x.200，例如 192.168.0.200。

### 防御入侵系统是否能够解密所有加密的连接？

不能。但她能够识别及阻挡自签 SSL/TLS 证书的流量。

### 我仍是否需要安在电脑上装防毒软件？

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

- [FriendlyElec NanoPi R6S Official Site](https://www.friendlyelec.com/index.php?route=product/product&product_id=289)  
- [The New Nanopi R6s Sbc: A Powerful Arm Board With A Huge Performance Edge Over The Pi4!](https://www.youtube.com/watch?v=CfaWB9q4xOI)  
- [NanoPi R6S - Unboxing and Quick Overview](https://www.youtube.com/watch?v=-rlJ_80d01U)  
- [NanoPi R6S Linux Review - Rockchip RK3588S with dual 2.5GbE + 1GbE](https://www.youtube.com/watch?v=gCBNWGhp8gM)  
- [NanoPi R6S - Wireguard & OpenVPN Throughput Test](https://www.youtube.com/watch?v=YC16CsEYN6g)  
- [NanoPi R6S - 2.35Gbps Throughput with only 5W of Power Consumption](https://www.youtube.com/watch?v=UMbTibi3n2k)  
- [NanoPi R6S Bootup - Firmware Update (eMMC) - PPPoE Speedtest](https://www.youtube.com/watch?v=WylvVwlDrFg)  

## SUPPORT

Discord @samiux#3445  

## SEE ALSO

- [Rosemary IDPS and 4K Video playback](https://youtu.be/w4cVVp3t23o)  
- [Garland 茼蒿 - Intrusion Detection and Prevention System (NanoPi R5S)](/garland.md)  
- [平价适合家用的防御入侵系统](/nanopi.md)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
