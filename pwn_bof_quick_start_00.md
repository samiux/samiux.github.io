|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Linux 栈溢出夺旗赛入门速成技巧 - 第零天 -- 工具安装和使用

因为大多数的 Linux Binary Exploitation (Pwn) 夺旗赛 (CTF) 题目都是源于 Ubuntu 的库 (glibc) 来编译的，而大多数玩家都会在 Ubuntu 内进行解题和利用开发 (Exploit Development) 。虚拟机器有助利用开发者 (玩家) 在原有的操作系统上运行 Ubuntu 进行解题。

如果有朋友对 Ubuntu 和虚拟机器没有经验的话，你必须去尝试安装 Ubuntu 在虚拟机器里。然后尝试使用 Linux 的命令行指令，例如 cd、ls、chmod、nano 等。在虚拟机器方面我比较喜欢使用开源工具，例如 Virtualbox。至于如何安装 Ubuntu 和 Virtualbox，可以参考 Ubuntu 官方网站。

在开始之前，必须在 Ubuntu 里安装所需的工具，它们就是 gdb、git、pwndbg、pwntools、ghidra 和 libc-database。

gdb 是 Linux debugger；pwndbg 是 gdb 的附加工具 (Plug-in) 有助于利用开发；ghidra 是 decompiler；而 libc-database 是 glibc 的所有知名 Linux 版本的库，最新的版本是 libc-2.35.so。安装 libc-database 极需时，请耐心等候。现附上安装这些工具的连结，虽然是关于 Ubuntu 22.04 LTS 的，但操作过程是大同小异的。其连结如下 ：

- [PWN and RE on Ubuntu 22.04 LTS](https://samiux.github.io/pwn_ubuntu.html)   

Ubuntu 18.04.6 LTS 是 libc-2.27.so；Ubuntu 20.04.4 LTS 是 libc-2.31.so；而最新版本的 Ubuntu 22.04 LTS 是 libc-2.35.so。基本上如果没有特别声明，我将会使用 Ubuntu Desktop 20.04.4 LTS 作示范觧说。

如果你有编程经验的话，在利用开发的过程中你会比较得心应手的，因为在 Python3 脚本 (Script) 的编写和 C 语言的源码和伪码 (Pseudo-code) 的阅读和理觧时比较有优势。

至于 Ghidra 的使用可以参考官方网站的视频。而 Python3、gdb 和 pwndbg 的使用方法请在互联网上搜索一下教程学习，现在不在此详细描述了。pwntools 的使用方法请参考官方文档和快速入门。

在未来的数天里，我将会向各位朋友介绍一些 Linux Binary Exploitation (Pwn) 夺旗赛基本入门速成技巧，其内容只涉及栈溢出 (Stack Buffer Overflow)，至于其他较高级的内容并不会触碰的。敬请理觧。

Samiux   
OSCE  OSCP  OSWP   
二零二二年四月廿九日，中国香港   

## 参考资料 ：

- [Ubuntu 20.04 LTS 影像档下载](https://releases.ubuntu.com/focal/)   
- [在 Virtualbox 安装 Ubuntu](https://ubuntu.com/tutorials/how-to-run-ubuntu-desktop-on-a-virtual-machine-using-virtualbox#1-overview)   
- [Ghidra 的使用视频](https://ghidra-sre.org)   
- [pwndbg 官网](https://github.com/pwndbg/pwndbg)   
- [pwndbg 官方文档](https://browserpwndbg.readthedocs.io/en/docs/)   
- [gdb 教学](https://www.tutorialspoint.com/gnu_debugger/index.htm)   
- [pwntools 官网](https://github.com/Gallopsled/pwntools)   
- [pwntools 官方文档](https://docs.pwntools.com/en/stable/)   
- [pwntools 快速入门](https://github.com/Gallopsled/pwntools-tutorial)   
- [libc-database 官网](https://github.com/niklasb/libc-database)   
- [libc database search 官网](https://libc.blukat.me)   
- [Linux 栈溢出夺旗赛入门速成技巧 - 第一天 -- 基础知识](/pwn_bof_quick_start_01.md)  
- [Linux 栈溢出夺旗赛入门速成技巧 - 第二天 -- 利用开发例子](/pwn_bof_quick_start_02.md)  
- [Linux 栈溢出夺旗赛入门速成技巧 - 第三天 -- 展望将来](/pwn_bof_quick_start_03.md)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
