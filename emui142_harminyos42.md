# 华为国际版 EMUI 14.2 及国行版 HarmonyOS 4.2 攻略

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

这篇文章的出现只因为华为更新了 microG Service。

华为国际版 EMUI 14.2 如果安装了「华为应用市场」内的  microG 的话，你的装置将能够兼容大部份谷歌框架 (Google Mobile Services, GMS) 的应用，当然除了谷歌钱包 (Google Wallet) 及 谷歌支付 (Google Pay) 外 (更有说订阅游戏等支付亦支援)，基本上是九成兼容 GMS 的。

方法如下：

从「华为应用市场」安装 microG Service，其会一拼安装 microG Companion。再到 microG Project 官网下载并安装 Services Framework Proxy。

接着授与所有权限给 microG Service 及 microG Companion，并且检查 microG Services 是否伪装所有选项成功，并关启其他设定。登入 Google Account 可以不于理会，除非你想登入。

接着就是到 Aurora Store 官网下载 Aurora Store 4.6.1 版本或以上，此乃 Google Play 的兼容版，所有在其内下载的 App 都是从 Google Play 下载的。紧记再在黑名单内设置华为应用市场下载的 App 以免有不良后果。

为何我不直接安装 Google Play 呢？这是因为我不想登入谷歌账号，如果你不介意登入的话，是可以直接安装 Google Play 而不需要 Aurora Store 的。

再者，在不登入谷歌账号 (Google Account) 也能运作正常。因为我不想登入谷歌账号，所以无法测试如果登入了有那些方便的使用体验。如果你不介意登入的话可以一试。

至于国行版 HarmonyOS 4.2 的「华为应用市场」内有 microG Service 的话，步骤与 EMUI 14.2 是一样的。

至于 HarmonyOS 2.0 或 EMUI 13 的装置，应该「华为应用市场」内是没有 microG Service 的，那就要往官网下载没有 hw 结尾的 microG Service、microG Companion 及 Service Framework Proxy。其后设置步骤与以上相同。

广东话语音输入需要安装 GBoard、Google (Search) 旧版及 Speech Recognition and Synthesis，并在「语言及输入法」内启动及设定。

最后，以我观察所得，EMUI 14.2 有可能是 HarmonyOS 3.0 的可能性很大。

### 已知问题

以下应用并不兼容 microG Service 的：

香港地区的「麦当劳」App。

以下应用有小瑕疵：

「KMB, LWB」App 不能显示路线地图。Google Authenticator 不能使用扫描器。但 microG Service 官网版本没有这问题。

### 版本

microG Service 华为版是 0.3.3.1.240913-hw
microG Companion 华为版是 0.3.3.1.40226-hw

microG Service 官网版是 0.3.3.240913
microG Companion 官网版是 0.3.3.40226

Services Framework Proxy 官网版是 0.1.0

Aurora Store 4.6.1

Samiux    
二零二四年九月卅日，中国香港            


## 参考资料

- [通話清晰有驚喜，HUAWEI Pura 70 Ultra 天通衛星通話實測! -- Mobile Magazine](https://www.mobilemagazinehk.com/2024/08/huawei-pura-70-ultra-tiantong-satellite-service-test.html)  
- [【Harmony OS 專區】口講輸入無難度，EMUI 14 廣東話語音輸入教學! -- Mobile Magazine](https://www.mobilemagazinehk.com/2024/08/harmony-os-emui-14-microsoft-swiftkey-ai-keyboard.html)  
- [microG Project](https://microg.org/download.html)    
- [Aurora Store](https://f-droid.org/packages/com.aurora.store)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
