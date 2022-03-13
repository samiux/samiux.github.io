|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# 夺旗赛中的 PWN 会消失吗？！

在未讨论这个问题之前，我想先谈谈无綫网络 (Wifi) 这问题。

早在 2018 年第三季时，当时 WPA3 制式仍未正式发布，正处于审议阶段。当时知名的爆破软件 Hashcat 的开发者们在硏究 WPA3 的破觧方法时，无意地发现了一项非常先进的 WPA2 攻击方法。直至目前为止，仍未有人发现可以破觧 WPA3 的方法。

基于 WPA3 是向下兼容的，所以所有由 WPA3 制式的路由器所提供的 WPA2 服务都受到 WPA3 的制式所保护。随着世界各地的无綫网络路由器更新至 WPA3 制式，攻击无綫路由器这个门路，至少直到目前为止，其实已经是一项「不可能的任务」了。

话说回头，夺旗赛中的 PWN 都正在步向这境地。PWN 的题目大多是 Linux 二进制档案 (Binary File)，主要是针对栈 (Stack) 和堆 (Heap) 的利用 (Exploit)。

虽然在过往有很多 Linux 二进制档案的栈安全机制可以被绕过而被利用，但随着 Glibc 2.31 的出现，连最后能利用的 Canary 的安全制式都被堵塞了。至于堆的利用，亦随着 Glibc 2.35 的出现，基本上堆的利用也成绝响。若果在未有新的利用方法之前，或再没有新的漏洞的话，相信 Linux 二进制档案的利用也成为另一项「不可能的任务」了。

只要 Glibc 2.35 或之前的版本不再支援时，而仍未有新的利用方法出现时，再加上 Glibc 没有新的漏洞时，相信比较进取的夺旗赛中的 Linux 二进制档案栈和堆 PWN 题目将会消失。那时候，Linux 的二进制档案相信是比较安全的了。

可是随着新功能的增加，漏洞或设计上的失误时有出现，所以这又有可能是一场幻觉吧！

Samiux   
OSCE  OSCP  OSWP   
二零二二年二月十九日，中国香港   

## 后记 ：

最近 Ubuntu 18.04 LTS 的 libc-2.27.so (Glibc 2.27) 已经更新，栈和堆的利用已经不像以前般那么容易了。

二零二二年三月十三日，中国香港  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
