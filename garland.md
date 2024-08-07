|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Garland 茼蒿 - Intrusion Detection and Prevention System  防御入侵系统

As technology advances, so do cybersecurity threats, which can leave individuals and small businesses vulnerable to cybercrime. Public-facing networks and computers are highly susceptible to daily hacker attacks from around the world. In response to this need, the Garland Intrusion Detection and Prevention System (IDPS) was developed as a highly efficient and ultra-low latency security solution.

One of the most significant benefits of Garland is its user-friendly design, making it accessible to everyone, regardless of their technical expertise in Network Security Monitoring (NSM) or Information Security (InfoSec). This "Plug, Play and Forget" system efficiently eliminates the need for any complex configurations or maintenance. Also, Garland is making it an affordable and ideal solution for home and small office/home office (SOHO) setups.

Garland's creator is an experienced white hat hacker, so the cybersecurity solution's design effectively detects and prevents sophisticated cyber threats. The Garland Intrusion Detection and Prevention System utilizes the malicious hacker's inside knowledge of current and potential malicious hacker tactics. And it provides complete transparency and is hassle-free for users.

Protecting digital assets should be a priority, and Garland Intrusion Detection and Prevention System meets this need. With this reliable and easy-to-use cybersecurity solution, individuals and small office/home office businesses can feel secure knowing that their digital assets are protected, and their data is secured against cyberattacks.

In summary, Garland Intrusion Detection and Prevention System is an effective, user-friendly, and accessible cybersecurity solution that can cater to the varying security needs of individuals and small office/home office businesses.

当技术不断进步时，网络安全威胁也会不断增加，这可能使个人和小型企业容易受到网络犯罪的侵害。公共网络和电脑面临来自世界各地黑客的日常攻击，而「茼蒿」入侵防御系统（IDPS）则为应对此类威胁提供了高效、超低延迟的解决方案。

「茼蒿」的主要优势之一是其用户友好设计，它可供任何人使用，无论其在网络安全监控（NSM）或信息安全（InfoSec）方面的技术水平如何。此外，「茼蒿」以「随插即用，并且可以忘记之」的方式运行，无需进行复杂的配置或维护。同时，「茼蒿」使其成为适合家庭和小型办公室/家庭办公室（SOHO）设置的负担得起的解决方案。

「茼蒿」的设计者是一位经验丰富的「白帽黑客」，因此这个网络安全方案的设计可以有效地检测和防范复杂的网络威胁。「茼蒿」入侵防御系统利用恶意黑客对当前和潜在的恶意黑客策略的深入了解，为用户提供完全透明、无麻烦的网络安全解决方案。

保护数字资产应该是一个优先考虑的问题，「茼蒿」入侵防御系统可以满足这一需求。有了这个可靠且易于使用的网络安全方案，个人和小型办公室/家庭办公室可以放心，他们的数字资产得到了保护，他们的数据得到了安全的保护，不会受到网络攻击的侵害。

总之，「茼蒿」入侵防御系统是一个有效、用户友好且易于获取的网络安全解决方案，可以满足个人和小型办公室/家庭办公室不同的安全需求。

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

- 有效阻挡已知的恶意行为, 例如网络攻击等  
- 极低的延迟性能有效地播放 4K 多媒体和玩要求速度的网络游戏
- 兼容微软视窗、苹果电脑、Linux 及 Apple iOS、Google Android、Huawei HarmonyOS 等各大移动系统
- 自动更新
- 随插即用，并且可以忘记之
- 完全透明
- 无需设定

## HARDWARE

### FriendlyElec NanoPi R5S

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

## DEPLOYMENT  

The following is the recommended connection method of Garland.  However, you can connect it behind router too.

建议将防御入侵系统放置于路由器之前，但亦可以放置在路由器之后。

```
            (LAN1)             (LAN2 to Router's WAN)          (Router's LAN)          
   Modem ----------- Garland ----------------------- Router ----------------- PCs & Laptops
                          |                           (WIFI)                      
                          |                             | (Router's LAN)                   
                          +-----------------------------+
                              (WAN to Router's LAN)
```
```
                                                                                +------- Laptops
                                                                                |
            (LAN1)           (LAN2 to Router's WAN)     (Switch's LAN)          |
   Modem ----------- Garland ------------------ Router -------- Switch ---------+
                          |                      (WIFI)             |           |
                          |                                         |           |
                          +-----------------------------------------+           +------- PCs
                                   (WAN to Switch's LAN)

```
```
                                                                    
                                                                   
            (LAN1)          (LAN2 to WIFI AP's WAN)               
Modem with ----------- Garland ---------------- WIFI AP -------------------- PCs & Laptops
WIFI Router (unused)      |                        |                
                          |                        |               
                          +------------------------+                
                            (WAN to WIFI AP's LAN)

```
```
                                                                    +------- WIFI AP
                                                                    |
            (LAN1)          (LAN2 to Switch's Port #1)              |
Modem with ----------- Garland ---------------- Switch -------------+
WIFI Router (unused)      |                        |                |
                          |                        |                |
                          +------------------------+                +------- PCs & Laptops
                            (WAN to Switch's LAN)

```
```
                                                                    +------- WIFI AP
                                                                    |
            (LAN1)          (LAN2 to Switch's Port #1)              |
5G Modem ----------- Garland ------------------ Switch -------------+
WIFI Router (unused)      |                        |                |
                          |                        |                |
                          +------------------------+                +------- PCs & Laptops
                            (WAN to Switch's LAN)

```

Do NOT use the wifi that comes with 5G modem or modem with WIFI router as the traffic flow will NOT be protected by Garland.

不要使用 5G 调解器或调解器有无线网络功能的无线网络，因为其无线网络不受「茼蒿」的保护。

## FAQ  

### When will the rules are updated?

#### 24/7
Between 0600 and 0630 hours every day, Garland will do the housekeeping and updating.  The defending work of Garland may be interrupted during this period.  

#### non 24/7
Garland can be turned off and it is not required to operate 24/7.  The update will be carried out within half an hour when the Garland is booting up.  It is advised NOT to turn off the Garland between 0600 and 0630 hours as it will do the update automatically.  If you do so, you may break the Garland.  Meanwhile, if you turn off the Garland within half an hour of the booting up, you may also break the system too.    

### How many detecting / blocking rules in Garland?  
There are over 34,000 rules in Garland and they are all free of charge.  The number of rules are increasing.    

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

所有规则都是免费的，已经超过 3 万 4 千多条，而且亦每日在增加中。

### 防御入侵系统是否能够解密所有加密的连接？

不能。但她能够识别及阻挡自签 SSL/TLS 证书的流量等。

### 我仍是否需要在电脑上安装防毒软件？

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

System price : Contact Samiux  (NOT including delivery)

Copyright (c) 2023 Samiux  

## 售价

系统售价 ：联络 Samiux  (不包括邮费)

版欋 (c) 2023 Samiux  

## SUPPORT AND ENQUIRY

Discord samiux @samiux   (#3445)  

## 支援及查询

Discord samiux @samiux   (#3445) 

## REFERENCE

- [FriendlyElec NanoPi R5S Offical Site](https://www.friendlyelec.com/index.php?route=product/product&product_id=287)  
- [NanoPi R5S评测-全面超越R2S 配置全面 接口丰富 小白用户首选](https://www.youtube.com/watch?v=AMLvqHbQwMI)  

## SEE ALSO

- [平价适合家用的防御入侵系统](/nanopi.md)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
