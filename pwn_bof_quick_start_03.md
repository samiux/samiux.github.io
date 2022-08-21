|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Linux 栈溢出夺旗赛入门速成技巧 - 第三天 -- 展望将来

今天是这系列的最后一天。昨天的示范介绍的是最基本的栈溢出漏洞利用，亦称为 ret2win 技巧。尚有更多的技巧，例如 ret2libc、ret2system  等，都是利用返回导向编程 (ROP) 技术来完成。有时也可以配合其他的漏洞，例如格式化 (Format String)、堆 (Heap) 等来完成利用而获得 Shell。所以练好 ROP 和 pwntools 技术是最好的资产。

随着 Glibc 的版本更新，大量的安全机制的改良和更新，有的利用技术己经一去不返了。

国外有很少这类夺旗赛的书籍，但国内现在可有几本，虽然其中讲述的觧题例子比较旧，但亦有包含一些基本技术说明，是入门的好书籍。以我所知这些书籍大概有以下几本比较好的，它们都可以在淘宝买到 :

- ```从 0 到 1 - CTFer 成长之路``` -- [Nu1L 战队]( https://www.nu1l.com/#/) 编著  (ISBN 978-7-121-37695-5)  
- ```CTF 竞赛权威指南 - Pwn 篇``` -- 杨超 编著  (ISBN 978-7-121-39952-7)  

至于网站方面，国内外都有大量这类资料可供参考学习，不过有些比较老旧。当然，你必须要了觧每个技术的原理才可以在觧题方面得心应手。现在附上一些网址以供参考学习 ：

- [Nightmare](https://guyinatuxedo.github.io/)  

最后，我邀请你参与我所建立的[挑战](/ctf-pwn.md)，一同学习，一同进步。

```「教为战、练为战。」-- 习近平```

Samiux   
OSCE  OSCP  OSWP   
二零二二年五月二日，中国香港   

## 参考资料 ：

- [CryptoCat](https://www.youtube.com/channel/UCEeuul0q7C8Zs5C8rc4REFQ)  
- [Linux 栈溢出夺旗赛入门速成技巧 - 第零天 -- 工具安装和使用](pwn_bof_quick_start_00.md)  
- [Linux 栈溢出夺旗赛入门速成技巧 - 第一天 -- 基础知识](/pwn_bof_quick_start_01.md)  
- [Linux 栈溢出夺旗赛入门速成技巧 - 第二天 -- 利用开发例子](/pwn_bof_quick_start_02.md)    

## TryHackMe - PWN101 - Beginner level binary exploitation challenges

- [PWN101 - Beginner level binary exploitation challenges](https://tryhackme.com/room/pwn101)  

### TryHackMe - PWN101 - Tutorials

- [Endianness Explained. Little-Endian and Big-Endian for 32 and 64 bits - Binary Exploitation (PWN)](https://www.youtube.com/watch?v=T8E_JRqN0fY)  
- [Intro - Binary Exploitation (PWN101) - TryHackMe](https://www.youtube.com/watch?v=8FEYdpZdftQ)  
- [Understanding Buffer Overflows (BOF) - pwn101 - PWN101 - TryHackMe](https://www.youtube.com/watch?v=0_merdYty4Y)  
- [Buffer Overflow to Modify Variable Values - pwn102 - PWN101 - TryHackMe](https://www.youtube.com/watch?v=DiyFDCuyPqg)  
- [Execution Flow Hijacking (ret2win) - pwn103 - PWN101 - TryHackMe](https://www.youtube.com/watch?v=-VUtXwDm5yQ)  
- [Shellcode Execution (ret2shellcode) - pwn104 - PWN101 - TryHackMe](https://www.youtube.com/watch?v=6Yiupj3XHrM)  
- [Integer Under/Overflow - pwn105 - PWN101 - TryHackMe](https://www.youtube.com/watch?v=Mfaq4PW8H1I)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
