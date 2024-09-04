# 除暴安良系列 (二) -- 虚拟服务器

[English](/defense_02_vps_en.md)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

大概两年前左右，我的朋友有一部虚拟服务器 (VPS) 用作网站，他的供应商投诉他的 VPS 攻击他人的 VPS，要求他停止这个行为，但我的朋友没有理会，随后他的 VPS 服务被中止了。此时朋友就求助于我。经过一轮交涉，供应商终于答应重开他的 VPS。除暴安良行动就此展开。

从友人得知他的 VPS 的 SSH 密码非常简单，只有 6 位，是甚么 123 的。而且 VPS 账户名称是 root。那就提供了一个非常好的攻击面给黑客了。我立即更改了一个强度高的 root 密码。

经过一轮检查，发现黑客隐藏了一个加密了，而且很难被发现的木马。清除后，我亦为其 VPS 加固。之后这两年间，我友人从未被投诉攻击他人的 VPS 了。

## 总结

所有密码应该为高强度，而且要包括大小楷英文字母、数字及符号，更需要比较长的字串，更重要的是不要被人很轻易的估算得到的密码，例如 MyStr0ngP@ssw0rd，这类密码是要不得的。

服务器应该在保安上作出加固，例如安装杀毒软件、入侵防御系统 (IDPS)、网页防火墙 (WAF) 等。

Samiux    
OSCE  OSCP  OSWP     
二零二四年九月四日，中国香港    


|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|



