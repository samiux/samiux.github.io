|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# 洋葱式防御 - 网络空间安全篇 (更新）

网络空间安全防御有如洋葱一样，层层包裹着核心的设施。外来的攻击或入侵者必须要过五关斩六将，工程非常之浩大，目的是要增加其入侵的成本。

## （一）流动装置篇

### 第一层

以「安卓」为例，由 Android 9 版本开始，已经可以设定「加密 DNS」(Secure DNS 或 Private DNS) 了。经过多番实验，在众多的供应商中，我觉得表现非常好的供应商就是 neustar UltraDNS。其分为收费和免费两种产品，收费版本话说可以提供 DNS Over HTTPS (DoH) 和 DNS Over TLS (DoT)，而免费的是不可以的，基本上免费版本的功能已经足够了。免费版本又分为三个过滤模式，分别为 Threat Protection、Family Secure 和 Business Secure。

Threat Protection 能够过滤恶意软件、恶意网站等。Family Secure 能够过滤 Threat Protection 的功能外，还能过滤色情网站或色情内容的网站、暴力、仇恨和赌博等网站。而 Business Secure 除了有以上的所有功能外，还能过滤一些「代理伺服器」(Proxy) 等，因为此等设备能够绕过其过滤功能的。

因为 neustar UltraDNS 没有提供有关 DNS 的网址，所以要改变网络供应商的 DNS 是需要靠一个可以改变 DNS 的软件，而这个软件是可以免费获得，它就是 DNS Smart Changer。  它内置了几乎所有已知的 Secure DNS，所有的选项都可以选择，但我个人比较喜欢选择 neustar UltraDNS 的 Business Secure。

当然，它能过滤的内容全部都是已知的，如果有一些不为人知的网站或恶意软件，它是不能够过滤的。

若果阁下以前已经在手机设定了 Secure DNS 选项，而且亦安装及设定了 DNS Smart Changer 的话，可以直接将手机中的设定为自动 (Auto) 就可以了，不然的话阁下是不能上网的。

### 第二层

大多数的中国产的「安卓」手机或平板都预装防毒软件，当然都是只能够阻挡已知的病毒和恶意软件。

最好就是取消「谷歌」(Google) 的广告设定了，因为它实在非常烦忧。

### 第三层

「安卓」用户可以安装 Comodo Mobile Security Antivirus。其有免费的「防火墙」 (Firewall)、「安全上网」 (Safe Browsing) 和 「无綫网络安全」 (Wifi Security) 可供使用。「安全上网」能够增加在浏览网页时的安全性，而「无綫网络安全」能够在使用无綫网络时的安全性。当然又是只可以对付已知的威胁。

另一个要安装的是 Malwarebytes，它可以免费使用的恶意软件扫描器，但就需要人手每次进行扫描了。经常更新其资料库，并进行扫描整部手机或平板。但若果阁下的手机是华为品牌的话，暂时未有提供下载安装。

### 第四层

如果是使用「火狐」(Firefox) 版本的话，可以安装以下组件 (Add-on)：uBlock Origin 和 Ghostery。这两个组件能够阻挡一些网页中的不受欢迎或恶意的脚本，例如  JavaScript 或广告 。

### 第五层

不连接公共无綫网络，不论是否需要密码与否，尤以无需密码的为更甚，利用 4G 或 5G 网络相对比较安全。

### 第六层

经常更新所有应用软件和系统软件，如果系统软件在半年至一年时间都不获更新，恳请阁下立即购买最新版本的手机。因为其所有漏洞 (Vulnerability) 都不会被修正，漏洞一旦被恶意黑客利用 (Exploit) 就会损失惨重。

### 第七层

不要点击来历不明的超连结 (Hyperlink)，更不要好奇地浏览一些可疑的网站，因为有可能在你点击后，对方已经传递了其恶意软件；色情网站、侵犯版权网站、声称能提供优惠或折扣的网站或网址可疑的网站等都不应该浏览。

尽可能减少使用浏览器，在搜寻器找到的资料要看清楚其网址超连结是否有可疑，因为网络上已经充斥着很多恶意网站了，这亦称为 「搜索引擎优化中毒」 (Search Engine Optimization (SEO) Poisoning)，恶意网站会刻意伪冒阁下搜寻的内容及骗过搜寻器而今其恶意网站的排名在十名之内，一不留神就会中招！

不要安装不明功能和来历的应用软件，须知道「应用市场」(Google Play Store) 内的软件未必全部都是安全的，绝大部份都是其后开发者将其转为恶意的。

最后，不要随便相信任何来电者或发短讯、电邮者，应该必先核实才行动。尤以「保安码」(Security Code)、「认证码」(2FA)，一旦将有关「保安码」、「认证码」交与他人，阁下将会损失浩大。

## （二）桌面电脑篇

### 第一层

安装及使用「牛角包」(Croissants) 防御入侵系统 (Intrusion Detection and Prevention System)。这个系统由我独力开发，是免费提供给每一个人使用。它安装后是基本上不需要再理会或维护的设备。它是「随插即用，并且可以忘记之」的高效开源 (Open Source) 产品。

它的特点是有效阻挡已知的恶意行为和有效阻挡已知的恶意软件，并且具有极低的延迟性能，可以播放 4K 多媒体和玩要求速度的网络游戏；它更会自动更新，并且兼容现有通用的所有作业系统 (Operating System)。

### 第二层

购买一台具有防御入侵系统和防毒软件的「路由器」(Router)。经常更新其固件 (Firmware) 和防毒资料库，并且确保其操作介面不会暴露于互联网 (Internet) 中，更加要更改预设的密码。如果是无綫路由器的话，一定要确保无綫密码要有足够的复杂和长度。

在路由器的 DHCP 选项中设定 DNS，这亦是 neustar UltraDNS 的产品：

Threat Protection - 156.154.70.2 和 156.154.71.2

Family Secure - 156.154.70.3 和 156.154.71.3

Business Secure - 156.154.70.4 和 156.154.71.4

再者，任何网络装置，例如「网络储存装置」（Network Attached Storage, NAS）、摄影机等，如果要向互联网开放的话，应该通过自家的「私人虚拟网络」（Virtual Private Network, VPN）进行操作。

### 第三层

桌面电脑必须安装或启动防火墙和安装防毒软件。不要使用侵权的防毒软件，这是会有一定的风险的。如果是微软视窗系统的话，可以使用其预载的防毒软件。更加要经常更新防毒资料库。

### 第四层

如果是使用「火狐」的话，建议安装以下组件 (Add-on)：uBlock Origin、Ghostery、Malwarebytes Browser Guard、Avast Online Security & Privacy、MalwareAI Browser Security 和 Decentraleyes。这些组件都是能够减少浏览网页时的风险。

在「火狐」可以启动 DNS over HTTPS 设定。如果阁下已经在路由器设定了 neustar UltraDNS 的话是可以不必设定的，最好二选其一就比较妥当了。其设定为 CleanBrowsing 的产品，一共分为 Security、Adult 和 Family。

其设定为：

Family Filter - ```https://doh.cleanbrowsing.org/doh/family-filter/```

Adult Filter - ```https://doh.cleanbrowsing.org/doh/adult-filter/```

Security Filter - ```https://doh.cleanbrowsing.org/doh/security-filter/```

但 Cleanbrowsing 的速度相对 neustar UltraDNS 的比较慢。

### 第五层

经常更新所有应用软件和作业系统，一旦漏洞被利用就后果不敢想像了。紧记请不要使用侵权软件。

### 第六层

不要点击来历不明的超连结 (Hyperlink)，更不要好奇地浏览一些可疑的网站，因为有可能在你点击后，对方已经传递了其恶意软件；色情网站、侵犯版权网站、声称能提供优惠或折扣的网站或网址可疑的网站等都应该不要浏览。

在搜寻器找到的资料要看清楚其网址超连结是否有可疑，因为网络上已经充斥着很多恶意网站了，这亦称为 「搜索引擎优化中毒」 (Search Engine Optimization (SEO) Poisoning)，恶意网站会刻意伪冒阁下搜寻的内容及骗过搜寻器而今其恶意网站的排名在十名之内，一不留神就会中招！

### 第七层

最后，不要随便相信任何来电者或发短讯、电邮者，应该必先核实才行动。尤以「保安码」(Security Code)、「认证码」(2FA)，一旦将有关「保安码」、「认证码」交与他人，阁下将会损失浩大。基本上与使用流动装置的行为和习惯一样。

以上的设施或设定是可以浏览西方「认为」不安全的，但绝对没有问题的网站，例如中国、俄罗斯、朝鲜等地区。我个人认为，Google、Cloudflare 和 Quad9 的 Secure DNS 比较不理想。

希望各位能够安心、安全和畅快地冲浪！

Samiux  
OSCE  OSCP  OSWP  
二零二一年六月廿六日，中国香港  
更新 二零二二年二月九日，中国香港 

参考连结：
- [neustar UltraDNS](https://www.publicdns.neustar)  
- [美國上半年受惡毒軟件襲擊贖金達5.9億 勢超越過去10年總和 -- 巴士的報](https://www.bastillepost.com/hongkong/article/9433867-%e7%be%8e%e5%9c%8b%e4%b8%8a%e5%8d%8a%e5%b9%b4%e5%8f%97%e6%83%a1%e6%af%92%e8%bb%9f%e4%bb%b6%e8%a5%b2%e6%93%8a%e8%b4%96%e9%87%91%e9%81%945-9%e5%84%84-%e5%8b%a2%e8%b6%85%e8%b6%8a%e9%81%8e%e5%8e%bb10) 
- [寓所物聯網設備 黑客易入侵操控 -- 巴士的報](https://www.bastillepost.com/hongkong/article/9812829-%e5%af%93%e6%89%80%e7%89%a9%e8%81%af%e7%b6%b2%e8%a8%ad%e5%82%99-%e9%bb%91%e5%ae%a2%e6%98%93%e5%85%a5%e4%be%b5%e6%93%8d%e6%8e%a7) 

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

