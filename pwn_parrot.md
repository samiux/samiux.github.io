|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# PWN and RE on Parrot Security 5.0

Linux Binary Exploitation (PWN) and Reverse Engineering (RE) on Parrot Security 5.0 (Electro Ara) requires to install the following packages (software), they are pwntools, pwndbg and libc-database.  Meanwhile, gdb and Ghidra are already installed on official release.

## pwntools Installation

```
sudo apt install libssl-dev
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

Samiux    
OSCE  OSCP  OSCE    
April 12, 2022, China, Hong Kong    

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
