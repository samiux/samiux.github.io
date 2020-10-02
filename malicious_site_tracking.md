|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# 恶意网站追蹤记

中秋国庆双节当日，友人传来一段信息和一幅画片，说其朋友传给他的。内容是有关「家居警察内联网」(POINT From Home) 的恶意网站连结，我当时随便看了一下，不以为然。其后查看我自家的防御入侵系统，看见了一条阻挡警告 (Blocking Alert)，是由我的家人点击的有关类似折扣优惠的连结，而其内容竟然和我友人的连结所得的一模一样。因此引发我的好奇心和职业病，决定来一次恶意网站大追蹤。

当时的连结是 www[.]pidwxl[.]co 会跳转到以下网站 sdfsys[.]xyz，cnokla[.]xyz 及 thoughtminuteschool1[.]live 至 thoughtminuteschool15[.]live (任何其中之一)，或 surpriseseparatemy1[.]live 至 surpriseseparatemy15[.]live (任何其中之一)，相信其是存有恶意程式 (代码)，其代码是用 JavaScript 编写的。初步得知其会截取受害人曾经登入过的网站的 Cookie 及 Session ID，从而可以冒认受害人的身份登入该等网站。所截获的 Cookie 及 Session ID 相信将会转到 [.]xyz 或 [.]live 结尾的网站来给黑客查看和利用。

随着其恶意的意图被发现及被广传，其 [.]live 结尾的网站是会随时变更的，现在只发现两组吧了。

在追查那些网址时得知，pidwxl[.]co 是在 2019-11-30 注册，sdfsys[.]xyz 是在 2020-06-09 注册，cnokla[.]xyz 是在 2020-03-25 注册，thoughtminuteschool1[.]live 至 thoughtminuteschool15[.]live，一共十五个都是在 2020-09-30 2100 至 2115 时期间注册，surpriseseparatemy1[.]live 至 surpriseseparatemy15[.]live, 一共十五个都是在 2020-10-1 1210 至 1215 时期间注册，相信 [.]live 结尾的网站是会随着被发现而更改的；而 mobile-global-apps-storage[.]life 是在 2020-09-09 注册，而所有持有人的资料都被隐藏或没有标示；有些以上的恶意网站都是由 Cloudflare 所保护，因此其网络位址是被隐藏的。

再查证得知 mobile-global-apps-storage[.]life 的网络地址为 139[.]180[.]144[.]155，这是一个建立在位于澳洲的 vultr.com 虚拟私人伺服器 (Virtual Private Server, VPS)，其伺服器开放了 80 和 443 端口，并运作 nginx 网页伺服器。这个网站相信只是用作跳转到 Google Pay 网站之用。

至于 [.]live 结尾的网站是运作 nginx 网页伺服器，并开放 80，443 及 2200 端口，而 2200 端口是运作 OpenSSH 7.4p1，其作业系统相信是 Debian 10。这些网站的网络位址 (IP Address) 现在是可以很容易查找得到的。

至于 [.]co 和 [.]xyz 结尾的网站是由 Cloudflare 所保护，其信息并不易查找得到。在追蹤过程中发现黑客可能是居住在中国香港的所谓「香港人」。

根据搜寻器 (Google Search) 对 POINT From Home 的搜寻结果显示，相信已经有很多警察朋友中招。如果曾经浏览过或点击过这连结，请尽快重启电脑或手机，并且清除浏览器中的所有快取 (Cache) 和 Cookie；如果曾经点击过此连结而又登入过「家居警察内联网」的话，请在重启电脑或手机，并且清除浏览器中的所有快取 (Cache) 和 Cookie，之后更改密码。重启电脑或手机的原因是其恶意代码是由 JavaScript 编写的，除了编写在网页中，JavaScript 只会存在于快取 (Cache) 和电脑或手机的记忆体中。

至于除了其他的目标外，为何也会针对「家居警察内联网」？我相信其网站或者有一些不为人知并且可被利用的漏洞吧！在这方面我不便更深入查证和了觧了！希望其网站的有关人员可以详细和全面渗透测试 (Penetration Test) 一下，以保障其网站的使用者的信息安全。我相信「家居警察内联网」早于 2019-11-30 开始已经被入侵。

最后，我建议不要点击来源不明或者可疑的连结，尤以在使用手机时！有时亲朋传来的信息未必完全安全的，更应审慎处理。切记安装具有侦测网页恶意软件能力的防毒软件；或使用具有防毒功能或者更有防御入侵功能的路由器。

如果阁下的系统可以将恶意网址等列入黑名单的话，只需要将 [.]co 及 [.]xyz 的域名列入黑名单就可以了。

恶意网站和网络地址一览表 ：  
www[.]pidwxl[.]co  
sdfsys[.]xyz  
cnokla[.]xyz  
thoughtminuteschool1[.]live  
thoughtminuteschool2[.]live  
thoughtminuteschool3[.]live  
thoughtminuteschool4[.]live  
thoughtminuteschool5[.]live  
thoughtminuteschool6[.]live  
thoughtminuteschool7[.]live  
thoughtminuteschool8[.]live  
thoughtminuteschool9[.]live  
thoughtminuteschool10[.]live  
thoughtminuteschool11[.]live  
thoughtminuteschool12[.]live  
thoughtminuteschool13[.]live  
thoughtminuteschool14[.]live  
thoughtminuteschool15[.]live  
surpriseseparatemy1[.]live  
surpriseseparatemy2[.]live  
surpriseseparatemy3[.]live  
surpriseseparatemy4[.]live  
surpriseseparatemy5[.]live  
surpriseseparatemy6[.]live  
surpriseseparatemy7[.]live  
surpriseseparatemy8[.]live  
surpriseseparatemy9[.]live  
surpriseseparatemy10[.]live  
surpriseseparatemy11[.]live  
surpriseseparatemy12[.]live  
surpriseseparatemy13[.]live  
surpriseseparatemy14[.]live  
surpriseseparatemy15[.]live  
mobile-global-apps-storage[.]life  
139[.]180[.]144[.]155  

Samiux  
OSCE  OSCP  OSWP  
二零二零年十月二日，中国香港  
	
|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
