|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# PWN and RE on Ubuntu 22.04 LTS

Linux Binary Exploitation (PWN) and Reverse Engineering (RE) on Ubuntu 22.04 LTS requires to install the following packages (software), they are pwntools, pwndbg, libc-database, gdb and Ghidra.  

## pwntools Installation

```
sudo apt install python3-pip python3-dev git libssl-dev libffi-dev build-essential
python3 -m pip install --upgrade pip
python3 -m pip install --upgrade pwntools
```

## pwndbg Installation

```
git clone https://github.com/pwndbg/pwndbg
cd pwndbg
./setup.sh
```

## libc-database Installation (Optional)

```
sudo apt install jq zstd rpm2cpio

git clone https://github.com/niklasb/libc-database
cd libc-database
./get all

or 

./get ubuntu debian
```

## Ghidra Installation

Download Ghidra (e.g. ghidra_10.1.3_PUBLIC_20220421.zip) from [official site](https://github.com/NationalSecurityAgency/ghidra/releases).

```
sudo cp ghidra_10.1.3_PUBLIC_20220421.zip /usr/local/bin

cd /usr/local/bin
sudo unzip ghidra_10.1.3_PUBLIC_20220421.zip

cd ghidra_10.1.3_PUBLIC

sudo ln -s /usr/local/bin/ghidra_10.1.3_PUBLIC/ghidraRun /usr/local/bin/ghidra
```

Samiux    
OSCE  OSCP  OSCE    
April 27, 2022, China, Hong Kong    

### Reference

- [Parrot Security](https://www.parrotsec.org/)    
- [pwntools](https://github.com/Gallopsled/pwntools)    
- [pwntools Documentation](https://docs.pwntools.com/en/stable/)    
- [pwndbg](https://github.com/pwndbg/pwndbg)    
- [pwndbg Documentation](https://browserpwndbg.readthedocs.io/en/docs/)    
- [libc-database](https://github.com/niklasb/libc-database)    
- [libc database search](https://libc.blukat.me/)    
- [gdb](https://www.sourceware.org/gdb/)    
- [gdb Documentation](https://www.sourceware.org/gdb/documentation/)    
- [Ghidra](https://ghidra-sre.org/)    

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
