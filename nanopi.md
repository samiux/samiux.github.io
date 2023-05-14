|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# 平价适合家用的防御入侵系统

虽然 FriendlyElec 的 NanoPi R6S 最初是作为路由器设计的，但我却将它们改造成了防御入侵系统。入侵防御系统不同于杀毒软件和防火墙，三者需要同时应用。对于大中小型企业，防御入侵系统是必不可少的网络安全设备之一。即便是家庭用户也需要这样的设备。  

我开发了基于嵌入式 Linux 的防御入侵系统，适用于 NanoPi R6S （Rosemary），有用户测试过下载速度大概有 800Mbps 左右以上。这防御入侵系统功耗极低，平均仅为 5W，运行时静音，体积非常小，只有信用卡大小。硬件设备可以在淘宝上购买，价格略高于一千多元港币左右。与数万元的企业级防御入侵系统相比，这些设备价格非常实惠。  

安装简单直接，只需将映像文件刻录到 micro SD 卡即可使用。无需设置或调试，即插即用，特别方便适合一般家庭用户或小型公司使用。这些防御入侵设备可达到 1000Mbps 的网络速度，极低的网络延迟让您可以在油管上享受 4K 视频或玩在线游戏，甚至可以使用 BT 下载。  

针对 micro SD 卡的选择，建议使用读取速度为 200Mbps，写入速度为 90Mbps 的 V30 规格高速 micro SD 卡，因其速度可能影响到设备的性能。此外，为了使设备正常运作，您需要准备普通手机适配器和 USB Type-C 线，以及额外两条 CAT 6 网络线。  

所有的镜像文件都采用了免费开源软件，因此完全可以免费获取。如果您对此感兴趣，但不知如何制作 micro SD 卡，可以联系我，我可以为您提供制作服务，而且费用全免（仅限亲朋好友）。实际上，网页上已经提供了详细的制作方法。我的目的是为了推广网络安全，并让防御入侵系统的使用成为一种普遍现象。此外，我自己也在使用这款设备，我采用的是 NanoPi R6S，希望能将这个好设备分享给更多人。  

欢迎回报可疑网址或钓鱼网址等恶意网站。  

最后，若果你想支持、打赏我这个开源项目的话，务请捐款支持「香港癌症基金会」，多谢大家。

祝各位安全地在网络上冲浪！并祝女神节快乐！  

* 后记，理论上安装这个防御入侵系统并不需要任何网络知识，但我遇到有一个个案是需要在路由器上设定外网地址为固定地址；又另一个案例是用户的网速是 30Mpbs 而只可用上 NanoPi R5S (Garland)。

# Affordable Intrusion Prevention System Suitable for Home Use

Although FriendlyElec's NanoPi R6S was originally designed as a router, I have modified them into an intrusion prevention system. Intrusion prevention systems are different from anti-virus software and firewalls, all three of which need to be used simultaneously. For large, medium and small enterprises, intrusion prevention systems are one of the essential network security devices. Even home users need such equipment.

I have developed an intrusion prevention system based on embedded Linux, suitable for NanoPi R6S (Rosemary). Some users have tested download speeds of around 800Mbps or more. This intrusion prevention system has extremely low power consumption, averaging only 5W, and runs silently, with a very small size about the size of a credit card. The hardware can be purchased on Taobao at a price slightly higher than HKD 1,000. Compared with enterprise-level intrusion prevention systems that cost tens of thousands of Hong Kong Dollar, these devices are very affordable.

Installation is simple and direct, just burn the image file to a micro SD card to use. There is no need for setup or debugging, it is plug-and-play, and it is especially convenient for general home users or small companies. These intrusion defense devices can achieve network speeds of up to 1000Mbps, with extremely low network latency that allows you to enjoy 4K videos on YouTube or play online games, and even use BT downloads.

Regarding the choice of micro SD card, it is recommended to use a V30 specification high-speed micro SD card with a read speed of 200Mbps and a write speed of 90Mbps, as its speed may affect the device's performance. In addition, in order to make the device operate normally, you need to prepare a regular mobile phone adapter and USB Type-C cable, as well as two additional CAT 6 network cables.

All image files are created using free open source software, so they can be obtained for free. If you are interested in this but do not know how to make a micro SD card, you can contact me and I can provide you with a production service, which is completely free (only for friends and family). In fact, the website has provided detailed production methods. My goal is to promote network security and make the use of intrusion prevention systems a universal phenomenon. In addition, I am also using this device myself. I have adopted the NanoPi R6S and hope to share this good device with more people.

Welcome to report suspicious websites or phishing websites and other malicious sites.

Finally, if you want to support and donate to my open source project, please donate to the "Cancer Fund". Thank you very much.

I wish everyone a safe surfing experience on the internet! And happy International Women's Day!

* Postscript: In theory, installing this intrusion prevention system does not require any network knowledge, but I encountered a case where it was necessary to set the external network address as a fixed address on the router, and another case where the user's network speed was 30Mbps and only the NanoPi R5S (Garland) could be used.

Samiux  
OSCE  OSCP  OSWP   
二零二三年三月八日，中国香港    
二零二三年五月十三日，中国香港    

## 开源项目：

- [Rosemary 迷迭香 - Intrusion Detection and Prevention System 防御入侵系统 (NanoPi R6S)](/rosemary.md)  
- [Garland 茼蒿 - Intrusion Detection and Prevention System 防御入侵系统 (NanoPi R5S)](/garland.md)      

## 参考网址：

- [FriendlyElec NanoPi R6S](https://www.friendlyelec.com/index.php?route=product/product&product_id=289)  
- [SanDisk Extreme Pro MicroSDXC UHS-I U3 A2 V30 64GB + 轉接器 ](https://www.amazon.com/-/zh_TW/SanDisk-Extreme-64GB-%E9%99%84%E8%BD%89%E6%8E%A5%E5%99%A8%E3%80%82%E5%85%A8%E9%AB%98%E6%B8%85%E5%92%8C-%E8%B6%85%E9%AB%98%E7%95%AB%E8%B3%AA%E5%BD%B1%E7%89%87%E9%8C%84%E8%A3%BD/dp/B07G3GMRYF)  

## 支持、打赏务请捐款至「香港癌症基金会」

- [香港癌症基金会](https://www.cancer-fund.org)  

## 参考：

- [洋葱式防御 - 网络空间安全篇 (最新篇）](/onion-defense_3.md)  
- [零死角无线网络](/mesh.md)  
- [小心被钓鱼](/phishing.md)  
- [如何成为反网络诈骗专家？](/anti-scam.md)  
- [网络空间安全及罪案消息 - 信用卡与电子支付](/e-pay.md)  
- [使用 Rosemary IPS 和 Nano Pi R6S 轻松保护您的家庭网络安全](/rosemary_ips.md)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

