[⚠️ Suspicious Content] # MGRS Locator 军用座标定位

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

Military Grid Reference System (MGRS) 军用座标系统是香港常用的座标系统之一，很多政府部门都在使用，例如香港警务处及香港消防处等。在陆上救援行动上亦大派用场，例如拯救行山者等。

现在我开发了一个网页版的 MGRS 座标定位，只要有网络或卫星通讯就可以使用，卫星通讯方面，例如中国电信的天通卫星。如果使用天通卫星可以使用华为的 Pura 70 Ultra 手机或类似的服务及设备。天通卫星通讯需要有该服务的 SIM 卡，而且需要付费。

请先允许获取定位位置及其权限。

[MGRS Locator 的网址](https://samiux.github.io/mgrs.html)  

欢迎免费使用。祝远足活动安全快乐！

## 如何阅读座标？

例如 50QKK1234567890

50Q -- 大部份的香港地方是位于全球的 50Q 网格内，这个网格是独一无二的；  

KK -- 是 50Q 网格内的香港在军用地图的网格，香港绝大部份位置是位于其中一个网格 KK 中；如果你在大屿山等地，有可能不是 KK；  

1234567890 -- 10 位数字，5 个为一组，共两组，是 KK 网格内的座标。

## 使用方法 ：

在手机开启卫星定位 (GPS)，打开网页，获取座标，截图并传送给救援人员，或向救援人员读出或报告座标。救援人员就可以从军用地图中得知被救援者的正确位置了。

如果身处在香港的话，不需要报告 50Q，只需报告 KK1234567890 这段座标就可以了。

## 如何阅读结果

MGRS -- MGRS 座标  (有误差率)  
Horizontal Accuracy -- 水平的准确度，以米计  (有误差率)  
Altitude -- 高度，以米计  (只供参考)  
Altitude Accuracy -- 高度的准确度，以米计   (只供参考)     

## 高级使用方法

只要在有网络时，显示了这个网页，其后是可以在没有网络的情况下仍然可以使用，最重要的是这个网页需要仍然在显示中。

### 已知问题

卫星定位是高耗电量的应用。

当被问及是否「允许网站获取你的位置」时，必须选择「允许」。不然有些手机不能在没有网络时获取座标，即「高级使用方法」。

若果你需要离线使用而你的手机不支援，可以联繫我，因为安卓手机是可以安装网页服务器在手机内的。至于苹果手机我就不太清楚了。已知有些安卓手机在飞行模式下是不能获取定位卫星位置的。

「高度」资料比较不准确，只供参考。另外，座标亦有误差率的，原因是民用的卫星定位没有高精准度。

如果不在户外空旷地方的话，有些手机并未能全部显示所有资料，但 MGRS 座标基本上是可以获取的。

## 声明

本应用不会收集个人或定位信息，所有数据在你个人的手机内显示，并不会储存。

Samiux    
二零二四年八月七日，中国香港  
更新 二零二四年八月八日，中国香港  
更新 二零二五年二月八日，中国香港   

## 参考资料

- [MGRS Locator 与 HKSOS 比较](/hksos_vs_mgrs.md)  
- [通話清晰有驚喜，HUAWEI Pura 70 Ultra 天通衛星通話實測! -- Mobile Magazine](https://www.mobilemagazinehk.com/2024/08/huawei-pura-70-ultra-tiantong-satellite-service-test.html)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
