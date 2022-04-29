|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Linux 栈溢出夺旗赛入门速成技巧 - 第一天 -- 基础知识

Linux 二进制执行档 (Binary File) 的格式是可执行与可链接格式 (Executable and Linkable Format,ELF)，在编译和链接时可以加入安全机制，而在现代的 GCC 及 Glibc 版本下的安全机制是默认开启的。它们分别是 RELRO、Canary、NX 和 PIE。

## 储存区唯读 (Relocation Read-Only,  RELRO)

全局偏移表 (Global Offset Table, GOT) 是一个执行档的段落 (Section)，主要纪录在动态链接 (Dynamic Link) 时的每个程序中的函数 (Function) 的载入位址。

如果 RELRO 是启动 (Enabled) 的话，全局偏移表 (GOT) 是唯读的。

## 金丝雀 (Canary)

如果是启动 (Enabled) 的话，栈 (Stack) 底会设置一个随机的 Canary 值。如果侦测其为被改变的话，栈溢出的利用就会不成功，并显示 Stack Smashing Detected 讯息。如果未能事先获得 Canary 的值，在栈溢出利用时必定会失败。

在编译时可以手动不启动 (Disabled)，```-fno-stack-protector```。

## 不能执行 (No-eXecute, NX)

如果是启动 (Enabled) 的话，栈就不能执行程序，而令致利用失败。

在编译时可以手动不启动 (Disabled)，```-z execstack```。

## 位址执行随机化 (Position Independent Executables, PIE)

如果是启动 (Enabled) 的话，执行档及库每次运行时的载入位址随机化，使得大大增加利用的难度。

在编译时可以手动不启动 (Disabled)，```-no-pie -fPIE```。

另外，在程序编译时默认地址空间配置随机加载 (Address Space Layout Randomization, ASLR) 是启动的，但可以手动不启动 (Disabled)，```-fno-stack-protector -z execstack```。

亦可以在 Linux 中暂时不启动，这样有时可以方便我们在利用的开发 ：

```
echo 0 | sudo tee /proc/sys/kernel/randomize_va_space
```

还原设定 ：

```
echo 2 | sudo tee /proc/sys/kernel/randomize_va_space
```

## 利用开发要点

在利用开发时可以利用 GOT 的位址泄漏而取得 libc 的版本，从而计算出 libc 的正确位址以便利用返回导向编程 (Return-Oriented Programming, ROP) 技术执行 Shell。

至于 RELRO、NX 和 PIE 可以利用 ROP 技术来绕过限制。

基本上 Canary 在 libc-2.31.so 时是可以爆破 (Brute Force) 的，但大前提是程序一定要运行在进程复制 (Fork) 中；但在 libc-2.35.so 的情况下就不能爆破了。在 libc-2.31.so 之前是利用其他的技术来绕过限制，在这里不详述了，可以上网查询一下。

在栈溢出的利用开发中，要计算栈的位址偏移时就会利用 pwndbg 的 cyclic 功能。

建构 50 个字符 ：

```
cyclic 50
```

输入之前建构的字符使程序崩溃，如果程序能够崩溃的话，表明字符足够使程序崩溃，而且程序是存在栈溢出漏洞，之后查看 RBP 的值 (必须是 4 bits) 然后计算偏移值 ：

```
cyclic --offset laaa
```

明天我会示范一下如何制作一个简单的栈溢出的利用开发例子。在开发前，首先一定要了觧程序的流程，它正在做些什么事情。之后就要分析程序和计划如何利用这个栈溢出漏洞。

在开发时，我们会利用 pwntools 这个工具，它可以大大减轻我们的开发时间，而且开发过程会变得更简单轻鬆，更会大大缩短工序增加效率，更加突出的优点是开发者对汇编语言 (Assemble Language) 的知识要求相对比较低。

Samiux   
OSCE  OSCP  OSWP   
二零二二年四月卅日，中国香港   

### 参考资料 ：

- [pwntools - ELF](https://github.com/Gallopsled/pwntools-tutorial/blob/master/elf.md)     
- [pwntools - ROP](https://github.com/Gallopsled/pwntools-tutorial/blob/master/rop.md)   

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
