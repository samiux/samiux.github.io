|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Rosemary 迷迭香 - Intrusion Detection and Prevention System  防御入侵系统

As technology advances, so do cybersecurity threats, which can leave individuals and small businesses vulnerable to cybercrime. Public-facing networks and computers are highly susceptible to daily hacker attacks from around the world. In response to this need, the Rosemary Intrusion Detection and Prevention System (IDPS) was developed as a highly efficient and ultra-low latency security solution.

One of the most significant benefits of Rosemary is its user-friendly design, making it accessible to everyone, regardless of their technical expertise in Network Security Monitoring (NSM) or Information Security (InfoSec). This "Plug, Play and Forget" system efficiently eliminates the need for any complex configurations or maintenance. Also, Rosemary is making it an affordable and ideal solution for home and small office/home office (SOHO) setups.

Rosemary's creator is an experienced white hat hacker, so the cybersecurity solution's design effectively detects and prevents sophisticated cyber threats. The Rosemary Intrusion Detection and Prevention System utilizes the malicious hacker's inside knowledge of current and potential malicious hacker tactics. And it provides complete transparency and is hassle-free for users.

Protecting digital assets should be a priority, and Rosemary Intrusion Detection and Prevention System meets this need. With this reliable and easy-to-use cybersecurity solution, individuals and small office/home office businesses can feel secure knowing that their digital assets are protected, and their data is secured against cyberattacks.

In summary, Rosemary Intrusion Detection and Prevention System is an effective, user-friendly, and accessible cybersecurity solution that can cater to the varying security needs of individuals and small office/home office businesses.

当技术不断进步时，网络安全威胁也会不断增加，这可能使个人和小型企业容易受到网络犯罪的侵害。公共网络和电脑面临来自世界各地黑客的日常攻击，而「迷迭香」入侵防御系统（IDPS）则为应对此类威胁提供了高效、超低延迟的解决方案。

「迷迭香」的主要优势之一是其用户友好设计，它可供任何人使用，无论其在网络安全监控（NSM）或信息安全（InfoSec）方面的技术水平如何。此外，「迷迭香」以「随插即用，并且可以忘记之」的方式运行，无需进行复杂的配置或维护。同时，「迷迭香」使其成为适合家庭和小型办公室/家庭办公室（SOHO）设置的负担得起的解决方案。

「迷迭香」的设计者是一位经验丰富的「白帽黑客」，因此这个网络安全方案的设计可以有效地检测和防范复杂的网络威胁。「迷迭香」入侵防御系统利用恶意黑客对当前和潜在的恶意黑客策略的深入了解，为用户提供完全透明、无麻烦的网络安全解决方案。

保护数字资产应该是一个优先考虑的问题，「迷迭香」入侵防御系统可以满足这一需求。有了这个可靠且易于使用的网络安全方案，个人和小型办公室/家庭办公室可以放心，他们的数字资产得到了保护，他们的数据得到了安全的保护，不会受到网络攻击的侵害。

总之，「迷迭香」入侵防御系统是一个有效、用户友好且易于获取的网络安全解决方案，可以满足个人和小型办公室/家庭办公室不同的安全需求。

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

- 有效阻挡已知的恶意行为，例如网络攻击等  
- 极低的延迟性能有效地播放 4K 多媒体和玩要求速度的网络游戏
- 兼容微软视窗、苹果电脑、Linux 及 Apple iOS、Google Android、Huawei HarmonyOS 等各大移动系统
- 自动更新
- 随插即用，并且可以忘记之
- 完全透明
- 无需设定

## HARDWARE

### FriendlyElec NanoPi R6S

- 8 cores ARM CPU (Quad-core ARM Cortex™-A76 & Quad-core ARM Cortex™-A55)  
- 8GB RAM  
- 32GB eMMC  
- 3 network interfaces (2 x 2.5Gbps, 1 x 1Gbps)   
- Max. power consumption 5W, fanless, no noise  
- Max. WAN traffic flow up to 2.5Gbps  
- 1 HDMI 2.0  
- 1 USB 3.0 Type-A, 1 USB 2.0 Type-A  
- 1 micro SD Card Slot  
- Slightly larger than a credit card  
- 96.5mm (L) x 68mm (W) x 30mm (H)   

## DEPLOYMENT  

The following is the recommended connection method of Rosemary.  However, you can connect it behind router too.

建议将防御入侵系统放置于路由器之前，但亦可以放置在路由器之后。

```
            (WAN)             (LAN1 to Router's WAN)          (Router's LAN)          
   Modem ----------- Rosemary ----------------------- Router ----------------- PCs & Laptops
                          |                           (WIFI)                      
                          |                             | (Router's LAN)                   
                          +-----------------------------+
                              (LAN2 to Router's LAN)
```
```
                                                                                +------- Laptops
                                                                                |
            (WAN)           (LAN1 to Router's WAN)     (Switch's LAN)           |
   Modem ----------- Rosemary ------------------ Router -------- Switch --------+
                          |                      (WIFI)             |           |
                          |                                         |           |
                          +-----------------------------------------+           +------- PCs
                                   (LAN2 to Switch's LAN)

```
```
                                                                   
                                                                    
            (WAN)          (LAN1 to WIFI AP's WAN)                  
Modem with ----------- Rosemary --------------- WIFI AP -------------------- PCs & Laptops
WIFI Router (unused)      |                        |               
                          |                        |               
                          +------------------------+              
                            (LAN2 to WIFI AP's LAN)

```
```
                                                                    +------- WIFI AP
                                                                    |
            (WAN)          (LAN1 to Switch's Port #1)               |
Modem with ----------- Rosemary ---------------- Switch ------------+
WIFI Router (unused)      |                        |                |
                          |                        |                |
                          +------------------------+                +------- PCs & Laptops
                            (LAN2 to Switch's LAN)

```
```
                                                                    +------- WIFI AP
                                                                    |
            (WAN)          (LAN1 to Switch's Port #1)               |
5G Modem ----------- Rosemary ------------------ Switch ------------+
WIFI Router (unused)      |                        |                |
                          |                        |                |
                          +------------------------+                +------- PCs & Laptops
                            (LAN2 to Switch's LAN)
```

Do NOT use the wifi that comes with 5G modem or modem with WIFI router as the traffic flow will NOT be protected by Rosemary.

不要使用 5G 调解器或调解器有无线网络功能的无线网络，因为其无线网络不受「迷迭香」的保护。

## FAQ  

### When will the rules are updated?

#### 24/7
Between 0600 and 0630 hours every day, Rosemary will do the housekeeping and updating.  The defending work of Rosemary may be interrupted during this period.  

#### non 24/7
Rosemary can be turned off and it is not required to operate 24/7.  The update will be carried out within half an hour when the Rosemary is booting up.  It is advised NOT to turn off the Rosemary between 0600 and 0630 hours as it will do the update automatically.  If you do so, you may break the Rosemary.  Meanwhile, if you turn off the Rosemary within half an hour of the booting up, you may also break the system too.    

### How many detecting / blocking rules in Rosemary?  
There are over 32,000 rules in Rosemary and they are all free of charge.  The number of rules are increasing.    

### Can Rosemary decrypt the SSL/TLS traffic?
Rosemary cannot decrypt the SSL/TLS traffic well.  However, it can handle a limited SSL/TLS traffic flow.  Therefore, it is not ideal for using it as Web Application Firewall (WAF).  For example, Rosemary can detect and drop self signed SSL/TLS certificate traffic, detect and drop malicious JA3 Fingerprint and etc.  

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

所有规则都是免费的，已经超过 3 万 2 千多条，而且亦每日在增加中。

### 防御入侵系统是否能够解密所有加密的连接？

不能。但她能够识别及阻挡自签 SSL/TLS 证书的流量及能够识别及阻挡恶意 JA3 指纹等。

### 我仍是否需要安在电脑上装防毒软件？

需要。除此之外，我更建议在「火狐」或 Chrome 浏览器安装以下附加组件，使得上网时更安全。

- uBlock Origin  
- Ghostery  
- Malwarebytes Browser Guard  
- Avast Online Security & Privacy  
- MalwareAI Browser Security  
- VT4Browsers  

## KNOWN ISSUES

Public Secure DNS will encrypt the DNS query that will affect the ability of blocking of IDPS, those secure DNS cannot be used, such as 

- Cloudflare
- Google Public DNS
- Quad9
- NextDNS
- OpenDNS
- DNSWatch

## 已知问题

公共网域名称系统会将网域查询加宻而影响防御入侵系统的防御能力，所以不能使用此等设定，例如：

- Cloudflare
- Google Public DNS
- Quad9
- NextDNS
- OpenDNS
- DNSWatch

## PRICE

System price : Contact Samiux  (NOT including postage)

Copyright (c) 2023 Samiux  

## 售价

系统售价 ：联络 Samiux  (不包括邮费)

版欋 (c) 2023 Samiux  

## SUPPORT AND ENQUIRY

Discord samiux @samiux   (#3445)  

## 支援及查询

Discord samiux @samiux   (#3445)  

## REFERENCE

- [FriendlyElec NanoPi R6S Official Site](https://www.friendlyelec.com/index.php?route=product/product&product_id=289)  
- [The New Nanopi R6s Sbc: A Powerful Arm Board With A Huge Performance Edge Over The Pi4!](https://www.youtube.com/watch?v=CfaWB9q4xOI)  
- [NanoPi R6S - Unboxing and Quick Overview](https://www.youtube.com/watch?v=-rlJ_80d01U)  
- [NanoPi R6S Linux Review - Rockchip RK3588S with dual 2.5GbE + 1GbE](https://www.youtube.com/watch?v=gCBNWGhp8gM)  
- [NanoPi R6S - Wireguard & OpenVPN Throughput Test](https://www.youtube.com/watch?v=YC16CsEYN6g)  
- [NanoPi R6S - 2.35Gbps Throughput with only 5W of Power Consumption](https://www.youtube.com/watch?v=UMbTibi3n2k)  
- [NanoPi R6S Bootup - Firmware Update (eMMC) - PPPoE Speedtest](https://www.youtube.com/watch?v=WylvVwlDrFg)  

## SEE ALSO

- [Rosemary IDPS and 4K Video playback](https://youtu.be/w4cVVp3t23o)  
- [平价适合家用的防御入侵系统](/nanopi.md)  
- [使用 Rosemary IPS 和 Nano Pi R6S 轻松保护您的家庭网络安全](/rosemary_ips.md)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
