# 除暴安良系列 (一) -- 路由器

[English](/defense_01_router_en.md)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

日前我的朋友投诉他的网络奇慢，网速由 900Mbps 以上骤跌至 300Mbps 左右。起初怀疑是我的入侵防御系统 (IDPS) 拖慢了，我当然不相信，除暴安良行动就此展开。

因为他没有安装入侵检测系统 (IDS)，而只安装了 IDPS，只发现有些不寻常的流量是经 123 端口往外连接，但不知道是由那部机器进行，需要遂部机器去捡测求证。

所以我一度怀疑是他的视窗系统感染了恶意软体。经过知名的防毒软体扫描后，发现有一隻木马隐藏在一个 ISO 文件里。不过在理论上来说，这隻木马应该并没有运作，当删除了之后，IDPS 仍然发现有不寻常流量，就证实了这个结论不关 ISO 文件的事。

进而开始怀疑是他的路由器感染了恶意软体，所以搜索一下这个路由器的型号等资料，发现香港官网内的这型号固件由 2020 年之后就再没有更新，而且更发现自 2022 年至 2024 年间有多个极高危的漏洞。得知这些资料之后，我相信他的路由器一定是被黑了及安装了恶意软体。再经过一轮爬文之后，发现其他国家的官网有 2024 年的固件更新。他更新后并重置路由器，网速立即回復正常。

经过更多一轮的排查，虽然路由器己经更新及重置后网速回復正常，但仍然有一些 123 端口的不寻常流量，相信恶意软体的后门仍在路由器中。而这个后门的流量虽然是被拦截了，但亦不应不处理。其后更换一个新的路由器就再没有发现这个问题了。

## 总结

除了电脑、手机系统等需要定时更新外，路由器的固件更新亦不可以忽视的。

另外，IDPS 除了能够拦截大部份的恶意攻击，也能有效地排查网络的网安问题，是一件不可或缺的好工具。

Samiux    
OSCE  OSCP  OSWP     
二零二四年九月三日，中国香港 

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
