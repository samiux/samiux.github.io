# 2024 年第一季的华为手机试用报告

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

## 前言

自从 2017 年 12 月开始，美国打压华为。2019 年 5 月将华为列入实体清单，华为不能在其安卓系统 (Android) 使用谷歌内核，即 Google Mobile Service，GMS。到 2020 年 5 月更不批准向华为销售芯片。

幸好华为不是一间海外上市公司，而未能被美国控制。华为随后开发华为核心，即 Huawei Mobile Service，HMS 及鸿蒙系统，即 HarmonyOS 来取代安卓系统。更于 2023 年生产麒麟 9000S 及 9000S1 芯片用于 Mate 60 系列。而作业系统就更新至鸿蒙 4.0。

于 2024 年第一季，鸿蒙系统更新至 4.2 版本及生产麒麟 9010 芯片，而鸿蒙星河版，即 HarmonyOS Next 更可能在 2024 年第三季推出。Pura 70 Pro 以上机型已经用上麒麟 9010 芯片。华为在 2023 年第四季开始再重返国际市场，国内版本使用鸿蒙系统 4.2，而国际版本就使用 EMUI 14.2。

## 鸿蒙 4.2

鸿蒙 4.2 版本的 nova 12 Pro 在香港使用时，有很多香港常用的 App 需要在其他地方下载。因我在手机输入中文文字时通常会「打繁出简」，所以使用了谷歌的 GBoard，而广东话语音输入就用华为的小艺输入法，基本上没有太大的问题。虽然如此，但仍有有些 App 不能安装或使用，例如 Udemy 或九巴等。因为 App 不是由华为应用市场安装，所以需要经常要自己检查有否更新，那就比较麻烦了。亦可以考虑安装开源的 Aurora Store，因其可以安装大部份 App，例如 Firefox 和 Github 等，但仍然有些 App 不能全面使用，例如九巴 App 等，但亦可以带来一些方便，不需要经常要自己到处检查更新。

不过，我们仍然可以前往 microG Project 官网下载华为版本的 microG Services，就是 com.google.android.gms-hw，com.android.vending-hw 及 com.google.android.gsf (Services Framework Proxy)，再配合 Aurora Store 就天衣无缝了。那么就可以使用大部份的 App 了，例如九巴 App (可以显示九巴路线地图，不需要安装 Google Map) 及 Udemy 等。切记要设置 microG Services 及 microG Companion 的权限。

另外，我友人的 HarmonyOS 4.2 Pura 70 Ultra 可以在华为应用商店安装华为版的 microG Services，至于 microG Companion 会自动下载，而 Services Framework Proxy 就需要到官网下载，而且可以运行大部份安卓软体，例如九巴 App。

## EMUI 14.2

EMUI 14.2 系统可以在 microG 官方网站下载最新版 (现时是 Preview 版本) 官方版本的 microG Services、microG Companion 及 Services Framework Proxy，此乃开源的 GMS，当然不是百份百与 GMS 一样，但其可以做到大概九成的效果。再下载开源的 Aurora Store 来安装香港常用的 App，效果也非常好。切记要设置 microG Services 及 microG Companion 的权限。

当然可以安装谷歌钱包 (Google Wallet) 及 Google Pay，在 NFC 里不能选择 Google Pay，所以不能以 NFC 使用 Google Pay；至于 Google Wallet 和 Google Pay 我并没有测试是否可用。有网红说可以在游戏里付款，但并没有说明信用卡可否绑卡及付款。

但 Play Store 里安装的八达通 App 是不能激活手机八达通的 (这个情况是在 microG 并没有登入 Google 账号下)，除非在华为应用商店内安装，而且你的手机亦被支援才可以使用手机八达通。

至于广东话语音输入法就不能使用，包括 GBoard 及小艺，取而代之是要安装 Google (Search) App (旧版) 或 Speech Recognition and Synthesis (新版)，并在输入法里激活，来输入广东话，但输出是繁体中文，并不是我想要的简体中文。

## 绑卡

国际版的 nova 12 系列已经可以使用电子版本的八达通了；而国际版的 Pura 70 系列直至目前为止，即 2024 年 6 月 19 日仍未可以使用，但估计很快就可以使用了。

至于国内版本和国际版本的香港华为账号的华为钱包是不能绑信用卡的，但可以经国内版本的华为手錶，即 Huawei Watch GT3 Pro 以上系列，绑信用卡，从而可以利用手錶刷信用卡。

## 流动数据网速

至于流动数据网速方面，我仍然相信华为是有 5G 射频芯片的。而国际版本就限制在 4G+ 速度上，但华为的算法非常了得，如果能够接驳到 5G SA 基站时，其速度可以高达 300Mbps 或以上 (我在香港九龙钻石山荷里活广场中国移动门店外利用 EMUI 14.2 版本的 Pura 70 Ultra 实测速的结果)。而国内版本就能够高达 700Mbps 或以上 (见参考资料)。

如果没有连接到 5G SA 基站时，EMUI 14.2 的 Pura 70 Ultra 4G 网速大致在 10 至 50Mbps 左右，而 4G+ 就略为快些至 70 至 90Mbps 或以上，我曾经测试到 159Mbps；而鸿蒙 4.2 的 Pura 70 Ultra 就大概在 100Mbps 左右或以上。因为 EMUI 14.2 版本的 Pura 70 Ultra 被限制在 4G+ 的速度内，其网络表现没有鸿蒙 4.2 版的 Pura 70 Ultra 好。但使用体验并不差，非常流畅，但如果比较喜欢 5G 嘅表现的话，鸿蒙 4.2 版的 Pura 70 Ultra 是不二之选。

## 安全

至于安全方面，除了有杀毒软件、电话黑名单及信息黑名单外，鸿蒙 4.2 还有「防伪基站」、信息 (SMS) 之「恶意网址识别」和「验证码安全保护」；而 EMUI 14.2 就只有信息之「恶意网址识别」。

## 总结

最后，鸿蒙星河版是否可以使用香港常用的 App 暂时仍是不清楚的。我认为以现在的华为应用商店规模来看，内里的 App 应该会全面兼容鸿蒙星河版，不然会有很多 App 用不了而影响鸿蒙系统的占有率。所以，以目前来说，香港用户是没有必要一定要购买国际版本的华为手机了。但是担心将来的鸿蒙星河版是否会兼容 APK 的话，还是选择国际版好了。

至于 Aurora Store 是需要用户定时自行到官网 F-Droid 更新。如果不是在华为应用商店安装的华为版 microG 的话，用户亦需要到 microG Project 官网自行下载安装官方版或华为版的 microG。建议将华为应用商店内安装的 App 及官方或华为版本的 microG 在 Aurora Store 内列入黑名单以免被 Aurora Store 自动更新而做成不知名的影响。

另外，我更在运行 EMUI 13 的国际版 Mate 40 Pro 安装官方版的 microG Services、microG Companion 及 Services Framework Proxy，虽然权限要自行设置，但在效果方面与 EMUI 14.2 及 HarmonyOS 4.2 的没有太大的分别。

再者，如果是虚拟私人网络 (VPN) 或「防骗视伏器 App」之类，鸿蒙 4.2 系统就在权限设置内允许上层运行，而 EMUI 14.2 系统就在电池启动管理设置内设定为手动启动管理，以免连接断开或不能连接网络。

如果不需要以 Google Pay 来付款的话 (但我没有测试过)，microG 及 Aurora Store 可以不必登入 Google 账号。

北斗卫星通讯和电话录音功能在国际版本的 Pura 70 Ultra 是没有的。

亦成功为国际版鸿蒙 2.0 的 MatePad Pro 5G 安装华为版本的 microG 和 Aroura Store，而且大部份的 App 也能使用。

实验得知鸿蒙 4.0 以下及 EMUI 13 或以上是需要安装官方的 microG，而鸿蒙 4.0 或以上 (暂时不包括鸿蒙星河版，HarmonyOS Next) 是需要安装华为版的 microG。

利申：  
2024 年第一季时，我持有国内版本鸿蒙 4.2 的 nova 12 Pro 和国际版本 EMUI 14.2 的 Pura 70 Ultra，以及国际版的 EMUI 13 的 Mate 40 Pro。还有国内版本鸿蒙 4.0 的华为手錶 GT3 Pro 及 国际版鸿蒙 2.0 的 MatePad Pro 5G，以及国际版 EMUI 12 有 GMS 和 HMS 的 P30。我还有运行鸿蒙 2.0 的 国际版 MatePad Pro 5G。

### 后记

如果你有兴趣购买荣耀 X7b 5G 手机的话，请不要认为国行版的 MagicOS 能够安装 microG 成功及可用。小米国行版的 HyperOS 可以安装 Google Play Store 等谷歌软体。

### 已知问题

「麦当劳」App 及 HK Express App 并不兼容 EMUI 14.2 及 HarmonyOS 4.2。

Samiux  
二零二四年六月十九日，中国香港  
更新 二零二四年六月廿三日，中国香港  
更新 二零二四年六月廿六日，中国香港  
更新 二零二四年六月廿七日，中国香港  
更新 二零二四年六月廿九日，中国香港  
更新 二零二四年六月卅日，中国香港  
更新 二零二四年七月二日，中国香港  
更新 二零二四年七月十五日，中国香港  
更新 二零二四年七月十六日，中国香港  
更新 二零二四年八月四日，中国香港  

## 参考资料：

- [U.S. actions against China's Huawei -- reuters](https://www.reuters.com/graphics/USA-CHINA/HUAWEI-TIMELINE/zgvomxwlgvd/)  
- [HUAWEI Pura 70 Ultra 港行網速實試！網速夠用兼夜拍表現突出 -- ezone (港行)](https://ezone.hk/article/20032878/HUAWEI-Pura-70-Ultra-%E6%B8%AF%E8%A1%8C%E7%B6%B2%E9%80%9F%E5%AF%A6%E8%A9%A6-%E5%A4%9C%E6%8B%8D%E6%94%9D%E5%8A%9B%E5%86%8D%E5%8D%87%E7%B4%9A)  
- [呢兩日突然又有人問番Pura 70 Ultra嘅5G,有圖有真相,各位睇片 -- 三禾電氣 (国行)](https://www.facebook.com/Trinityelectronic/videos/%E5%91%A2%E5%85%A9%E6%97%A5%E7%AA%81%E7%84%B6%E5%8F%88%E6%9C%89%E4%BA%BA%E5%95%8F%E7%95%AApura-70-ultra%E5%98%855g%E6%9C%89%E5%9C%96%E6%9C%89%E7%9C%9F%E7%9B%B8%E5%90%84%E4%BD%8D%E7%9D%87%E7%89%87/805934984251913/)  
- [[初步評價] 華為 Nova12S 外觀吸引, 但... 拿上手就立即放回去？之後… -- hokoonho (港行)](https://www.youtube.com/watch?v=f6rFEPZQBsw)  
- [華為手機只有4G？我不想再解釋了.... 事實就是事實... Huawei Pura70 Ultra 網速測試 -- hokoonho (国行)](https://www.youtube.com/watch?v=4BHu24esPnU)
- [三禾電氣華為手機6月份最新報告 -- 三禾電氣](https://www.youtube.com/watch?v=ga9izwT6Kbg)
- [这回，我总算能给你们爆点原生鸿蒙的猛料了！ -- 观察者](https://user.guancha.cn/main/content?id=1255079)  
- [大厦室内5G覆盖标籤计划 -- OFCA](https://www.ofca.gov.hk/sc/consumer_focus/guide/help_for_consumers/indoor5g/index.html)  
- [DOXMARK - Huawei Pura 70 Ultra](https://www.dxomark.com/smartphones/Huawei/Pura-70-Ultra)  
- [中国成功搭建！“6G关键技术迎来新突破” -- 观察者](https://www.guancha.cn/industry-science/2024_07_12_741223.shtml)  
- [2024年7月华为手机鸿蒙4.2系统HarmonyOS 4.2最新版安装谷歌服务框架GMS -- Youtube](https://www.youtube.com/watch?v=eK78luv5A3Y)  
- [「花生」HarmonyOS NEXT显微镜级观察：极致流畅全新动画，从零做起真挺好～ -- Youtube](https://www.youtube.com/watch?v=5sg-bbpza1w)  
- [安卓Apk可以转换为鸿蒙Hap？Android原生也能实现跨平台！  -- Android出海](https://mp.weixin.qq.com/s/o58z9fsRoUiwAFR_3QbuTw)  
- [华为手机国际版 EMUI 14.2 攻略](/emui142.md)  
- [microG Project](https://microg.org/download.html)  
- [Aurora Store](https://f-droid.org/packages/com.aurora.store/)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
