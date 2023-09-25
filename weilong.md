|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# 威龙  Weilong - Intrusion Detection and Prevention System  防御入侵系统

「威龙」是我国第六代隐形战机 歼-20 的称号。

As technology advances, so do cybersecurity threats, which can leave individuals and small businesses vulnerable to cybercrime. Public-facing networks and computers are highly susceptible to daily hacker attacks from around the world. In response to this need, the Weilong Intrusion Detection and Prevention System (IDPS) was developed as a highly efficient and ultra-low latency security solution.

One of the most significant benefits of Weilong is its user-friendly design, making it accessible to everyone, regardless of their technical expertise in Network Security Monitoring (NSM) or Information Security (InfoSec). This "Plug, Play and Forget" system efficiently eliminates the need for any complex configurations or maintenance. Also, Weilong is making it an affordable and ideal solution for home and small office/home office (SOHO) setups.

Weilong's creator is an experienced white hat hacker, so the cybersecurity solution's design effectively detects and prevents sophisticated cyber threats. The Weilong Intrusion Detection and Prevention System utilizes the malicious hacker's inside knowledge of current and potential malicious hacker tactics. And it provides complete transparency and is hassle-free for users.

Protecting digital assets should be a priority, and Weilong Intrusion Detection and Prevention System meets this need. With this reliable and easy-to-use cybersecurity solution, individuals and small office/home office businesses can feel secure knowing that their digital assets are protected, and their data is secured against cyberattacks.

In summary, Weilong Intrusion Detection and Prevention System is an effective, user-friendly, and accessible cybersecurity solution that can cater to the varying security needs of individuals and small office/home office businesses.

当技术不断进步时，网络安全威胁也会不断增加，这可能使个人和小型企业容易受到网络犯罪的侵害。公共网络和电脑面临来自世界各地黑客的日常攻击，而「威龙」入侵防御系统（IDPS）则为应对此类威胁提供了高效、超低延迟的解决方案。

「威龙」的主要优势之一是其用户友好设计，它可供任何人使用，无论其在网络安全监控（NSM）或信息安全（InfoSec）方面的技术水平如何。此外，「威龙」以「随插即用，并且可以忘记之」的方式运行，无需进行复杂的配置或维护。同时，「威龙」使其成为适合家庭和小型办公室/家庭办公室（SOHO）设置的负担得起的解决方案。

「威龙」的设计者是一位经验丰富的「白帽黑客」，因此这个网络安全方案的设计可以有效地检测和防范复杂的网络威胁。「威龙」入侵防御系统利用恶意黑客对当前和潜在的恶意黑客策略的深入了解，为用户提供完全透明、无麻烦的网络安全解决方案。

保护数字资产应该是一个优先考虑的问题，「威龙」入侵防御系统可以满足这一需求。有了这个可靠且易于使用的网络安全方案，个人和小型办公室/家庭办公室可以放心，他们的数字资产得到了保护，他们的数据得到了安全的保护，不会受到网络攻击的侵害。

总之，「威龙」入侵防御系统是一个有效、用户友好且易于获取的网络安全解决方案，可以满足个人和小型办公室/家庭办公室不同的安全需求。

## FEATURES

- Blocks known malicious activities, e.g. internet attacks
- Blocks known malwares, e.g. ransomwares  
- Compatible with Bittorrent and 4K video streaming  
- Ultra-low latency for demanding online games  
- Compatible with Microsoft Windows, GNU Linux, Apple macOS, Apple iOS, Google Android and Huawei HarmonyOS  
- No subscription and annual fee  
- Automatically update  
- Plug, Play and Forget!  
- Totally transparent  
- Setup is not required   

## 功能概览

- 有效阻挡已知的恶意行为，例如网络攻击等
- 有效阻挡已知的恶意软件，例如勒索软件等
- 极低的延迟性能有效地播放 4K 多媒体和玩要求速度的网络游戏
- 兼容微软视窗、苹果电脑、Linux 及 Apple iOS、Google Android、Huawei HarmonyOS 等各大移动系统
- 无需年费或使用费
- 自动更新
- 随插即用，并且可以忘记之
- 完全透明
- 无需设定

## HARDWARE

- 8 cores CPU
- 8GB RAM
- Max. power consumption 5W, fanless, no noise  
- Slightly larger than a credit card  
- 96.5mm (L) x 68mm (W) x 30mm (H)   

## DEPLOYMENT  

You are recommended to connect the Weilong behind router.  However, you can connect it in front of router too.  If you connect the Weilong in front of router, you cannot see the intranet.

建议将防御入侵系统放置于路由器之后，但亦可以放置在路由器之前，分别在于，如果放在路由器之前是看不到内网的。


- 图一，下图不能看见内网。

```
            (WAN)             (LAN1 to Router's WAN)          (Router's LAN)          
   Modem ----------- Weilong ----------------------- Router ----------------- PCs & Laptops
                          |                           (WIFI)                      
                          |                             | (Router's LAN)                   
                          +-----------------------------+
                              (LAN2 to Router's LAN)
```

- 图二，下图不能看见内网。

```
                                                                                +------- Laptops
                                                                                |
            (WAN)           (LAN1 to Router's WAN)     (Switch's LAN)           |
   Modem ----------- Weilong ------------------ Router -------- Switch ---------+
                          |                      (WIFI)             |           |
                          |                                         |           |
                          +-----------------------------------------+           +------- PCs
                                   (LAN2 to Switch's LAN)

```

- 图三，下图可以看见内网。

```
                                                                                +------- Laptops
                                                                                |
            (WAN)           (to Weilong's WAN)     (LAN1 to Switch's LAN1)      |
   Modem ----------- Router ------------------ Weilong -------- Switch ---------+------- WIFI AP
                     with WIFI (unused)           |                 |           |
                                                  |                 |           |
                                                  +-----------------+           +------- PCs
                                                 (LAN2 to Switch's LAN)

```

- 图四，下图可以看见内网。

```
                                                                   
                                                                    
            (WAN)          (LAN1 to WIFI AP's WAN)                  
Modem with ----------- Weilong --------------- WIFI AP -------------------- PCs & Laptops
WIFI Router (unused)      |                        |               
                          |                        |               
                          +------------------------+              
                            (LAN2 to WIFI AP's LAN)

```

- 图五，下图可以看见内网。

```
                                                                    +------- WIFI AP
                                                                    |
            (WAN)          (LAN1 to Switch's Port #1)               |
Modem with ----------- Weilong ---------------- Switch -------------+
WIFI Router (unused)      |                        |                |
                          |                        |                |
                          +------------------------+                +------- PCs & Laptops
                            (LAN2 to Switch's LAN)

```

- 图六，下图可以看见内网。

```
                                                                    +------- WIFI AP
                                                                    |
            (WAN)          (LAN1 to Switch's Port #1)               |
5G Modem ----------- Weilong ------------------ Switch -------------+
WIFI Router (unused)      |                        |                |
                          |                        |                |
                          +------------------------+                +------- PCs & Laptops
                            (LAN2 to Switch's LAN)
```

Do NOT use the wifi that comes with 5G modem or modem with WIFI router as the traffic flow will NOT be protected by Weilong.

不要使用 5G 调解器或调解器有无线网络功能的无线网络，因为其无线网络不受「威龙」的保护。

## USER INTERFACE

```
http://192.168.x.200:5636
```

For example, ```http://192.168.0.200:5636```.

__WARNING : Please DO NOT allow this interface to be accessed in the internet as it will endanger to your network.__

## 使用者介面

```
http://192.168.x.200:5636
```

例如 ```http://192.168.0.200:5636```.

__警告 ：切勿开放此网址到互联网，因为这样做会危害内网的安全。__

[![](https://img.youtube.com/vi/MGkS28dqfWA/0.jpg)](https://www.youtube.com/watch?v=MGkS28dqfWA "Weilong Intrusion Detection and Prevention System")  

## FAQ  

### When will the rules are updated?

#### 24/7
Between 0600 and 0630 hours every day, Weilong will do the housekeeping and updating.  The defending work of Weilong may be interrupted during this period.  

#### non 24/7
Weilong can be turned off and it is not required to operate 24/7.  The update will be carried out within half an hour when the Weilong is booting up.  It is advised NOT to turn off the Weilong between 0600 and 0630 hours as it will do the update automatically.  If you do so, you may break the Weilong.  Meanwhile, if you turn off the Weilong within half an hour of the booting up, you may also break the system too.    

### How many detecting / blocking rules in Weilong?  
There are over 34,000 rules in Weilong and they are all free of charge.  The number of rules are increasing.    

### Can Weilong decrypt the SSL/TLS traffic?
Weilong cannot decrypt the SSL/TLS traffic well.  However, it can handle a limited SSL/TLS traffic flow.  Therefore, it is not ideal for using it as Web Application Firewall (WAF).  For example, Weilong can detect and drop self signed SSL/TLS certificate traffic, detect and drop malicious JA3 Fingerprint and etc.  

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

- Cloudflare DNS
- Google Public DNS
- Quad9 DNS
- NextDNS
- OpenDNS
- DNSWatch

## 已知问题

公共网域名称系统会将网域查询加宻而影响防御入侵系统的防御能力，所以不能使用此等设定，例如：

- Cloudflare DNS
- Google Public DNS
- Quad9 DNS
- NextDNS
- OpenDNS
- DNSWatch

## PRICE

System price : Please contact Samiux  (NOT including postage)

Package included : device x 1, power adapter x 1 and USB Type-C cable x 1, as well as CAT 6 network cables x 2.

Copyright (c) 2023 Samiux  

## 售价

系统售价 ：请联络 Samiux  (不包括邮费)

整套设备包括 ：设备 x 1，电源适配器 x 1，USB Type-C 线 x 1，以及 CAT 6 网络线 x 2。

版欋 (c) 2023 Samiux  

## SUPPORT AND ENQUIRY

Discord samiux @samiux   (#3445)  

## 支援及查询

Discord samiux @samiux   (#3445)  

## SEE ALSO

- [Intrusion Detection, Intrusion Prevention, and Antivirus: The Differences](https://bestructured.com/intrusion-detection-intrusion-prevention-and-antivirus-the-differences/)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
