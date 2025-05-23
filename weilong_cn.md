# 威龙  Weilong - Intrusion Detection and Prevention System  防御入侵系统
# Model 6 Version 2

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

[English](/weilong_en.md)  

### 「威龙」是我国第五代隐形战机 歼-20 的称号。

当技术不断进步时，网络安全威胁也会不断增加，这可能使个人和小型企业容易受到网络犯罪的侵害。公共网络和电脑面临来自世界各地黑客的日常攻击，而「威龙」入侵防御系统（IDPS）则为应对此类威胁提供了高效、超低延迟的解决方案。

「威龙」的主要优势之一是其用户友好设计，它可供任何人使用，无论其在网络安全监控（NSM）或信息安全（InfoSec）方面的技术水平如何。此外，「威龙」以「随插即用，并且可以忘记之」的方式运行，无需进行复杂的配置或维护。同时，「威龙」使其成为适合家庭和小型办公室/家庭办公室（SOHO）设置的负担得起的解决方案。

「威龙」的设计者是一位经验丰富的「白帽黑客」，因此这个网络安全方案的设计可以有效地检测和防范复杂的网络威胁。「威龙」入侵防御系统利用恶意黑客对当前和潜在的恶意黑客策略的深入了解，为用户提供完全透明、无麻烦的网络安全解决方案。

保护数字资产应该是一个优先考虑的问题，「威龙」入侵防御系统可以满足这一需求。有了这个可靠且易于使用的网络安全方案，个人和小型办公室/家庭办公室可以放心，他们的数字资产得到了保护，他们的数据得到了安全的保护，不会受到网络攻击的侵害。

总之，「威龙」入侵防御系统是一个有效、用户友好且易于获取的网络安全解决方案，可以满足个人和小型办公室/家庭办公室不同的安全需求。

## 功能概览

- 有效阻挡已知的恶意行为，例如网络攻击等
- 有效阻挡已知的恶意软件，例如勒索软件等
- 有效阻挡已知的恶意网站及钓鱼网站等  
- 监控、检测网络流量以作分析  
- 极低的延迟性能有效地播放 4K 多媒体和玩要求速度的网络游戏
- 兼容微软视窗、苹果电脑、Linux 及 Apple iOS、Google Android、Huawei HarmonyOS 等各大移动系统
- 无需年费或使用费
- 自动更新
- 随插即用，并且可以忘记之
- 完全透明
- 无需设定

## 特点

「威龙」入侵防御系统与其他同类型产品比较，其出类拨萃之处在于其能够迷惑黑客。

举个例子，如果有贼人要爆窃一间屋时，通常会经门窗进入。但是如果贼人找不到或看不见门窗，虽然这间屋的门窗其实是存在的，他如何爆窃这间屋呢？

同样道理，黑客找不到或看不见任何入侵点，虽然入侵点其实是存在的，他们如何入侵你的电脑或网络呢？

这个是源头打击的设计概念，经试验证实可行、可靠及实用，非常有效御防黑客的入侵。

## 被入侵后之威脋

黑客入侵后是可以留下或拿走任何资料，而且更可以利用你的电脑或网络做任何事情，包括用以作为跳板入侵其他的电脑或网络等。

## 硬体

- 最高功耗 5W，无风扇无噪
- 大小约大于一张信用卡
- 96.5mm (长) x 68mm (濶) x 30mm (高)  

## 安装配置

建议将防御入侵系统放置于路由器之前，但亦可以放置在路由器之后，分别在于，如果放在路由器之前是看不到内网的。

若果将其配罝到路由器之前将会有很多告警产生。但是若果情况许可而又有端口开放的话，建议将其放在路由器前面。

- 图一，下图不能看见内网。

```
            (WAN)             (LAN1 to Router's WAN)          (Router's LAN)          
   Modem ----------- Weilong ----------------------- Router ----------------- PCs & Laptops
   (or with WIFI)         |                           (WIFI)                      
     (unused)             |                             | (Router's LAN)                   
                          +-----------------------------+
                              (LAN2 to Router's LAN)
```

- 图二，下图不能看见内网。

```
                                                                                +------- Laptops
                                                                                |
            (WAN)           (LAN1 to Router's WAN)     (Switch's LAN)           |
   Modem ----------- Weilong ------------------ Router -------- Switch ---------+
   (or with WIFI)         |                      (WIFI)             |           |
     (unused)             |                                         |           |
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

不要使用 5G 调解器或调解器有无线网络功能的无线网络，因为其无线网络不受「威龙」的保护。

## 常问问题

### 何时会更新防御入侵系统的规则？

#### 全日运作

每日的凌晨 0600 至 0630 时更新和维护，其间有可能对防御入侵系统的运作有些少影响。

#### 非全日运作

每当启动后的半小时内其会自行更新维护，所以不要在其间或在 0600 至 0630 时其间内关闭防御入侵系统，因为有可能会损坏防御入侵系统。

### 防御入侵系统内有多少条规则？

所有规则都是免费的，已经超过 3 万 8 千多条，而且亦每日在增加中。

### 防御入侵系统是否能够解密所有加密的连接？

不能。但她能够识别及阻挡自签 SSL/TLS 证书的流量等。

### 我仍是否需要在电脑上安装防毒软件？

需要。除此之外，我更建议在「火狐」或 Chrome 浏览器安装以下附加组件，使得上网时更安全。

- uBlock Origin  
- Malwarebytes Browser Guard  
- Avast Online Security & Privacy  (Firefox 除外）  
- MalwareAI Browser Security  
- VT4Browsers  

## 已知问题

公共网域名称系统会将网域查询加宻而影响防御入侵系统的防御能力，所以不能使用此等设定，例如：

- Cloudflare DNS
- Quad9 DNS
- NextDNS
- OpenDNS
- DNSWatch

## 售价

系统售价 ：请联络 Samiux  (不包括邮费)

整套设备包括 ：设备 x 1，电源适配器 x 1，USB Type-C 线 x 1，以及 CAT 6 网络线 x 2。

版欋 (c) 2012-2025 Samiux  

## 支援及查询

Discord samiux @samiux   (#3445)  

## 更多资讯

- [Intrusion Detection, Intrusion Prevention, and Antivirus: The Differences](https://bestructured.com/intrusion-detection-intrusion-prevention-and-antivirus-the-differences/)
- [洋葱式防御 - 网络空间安全篇 (最新篇）](/onion-defense_3.md)

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
