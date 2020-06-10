|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Create Windows 10 2004 Installation USB in Ubuntu 20.04 LTS

[![](https://img.youtube.com/vi/WNc8GOps6TY/0.jpg)](https://www.youtube.com/watch?v=WNc8GOps6TY)

First of all, we need to download Windows 10 ISO from [Microsoft](https://www.microsoft.com/en-us/software-download/windows10ISO) in Ubuntu 20.04 LTS.

We are required to install ```wimtools``` by the following command.

```bash
sudo apt install wimtools
```

Create ```GPT``` for the USB drive and format it in ```FAT32```.  Make sure to set the partition as ```MBR``` and ```BIOS Bootable``` at ```Disks``` (Gnome Disk Utility).

Since ```install.wim``` under ```sources``` directory at Windows 10 2004 ISO is greater than 4GB, we need to split the ```install.wim``` into smaller size files or optimize the size of the file.

We have two options, either Option 1 or Option 2, to do with the ```install.wim``` file.  Option 2 requires a longer time to complete.  Optimize makes the file size smaller, it is about 3.3GB after the optimization.

## Option 1 - Split

```bash
wimlib-imagex split install.wim install.swm 2000
```

## Option 2 - Optimize

```bash
wimlib-imagex optimize install.wim
```

It is recommended to copy all the files from the ISO to another directory, namely ```splitted```.  Make sure to delete the original ```install.wim``` under ```sources``` directory before copying all the files to the USB drive from ```splitted``` directory.

When finished, your USB drive can be bootable to BIOS and UEFI computers.

Samiux  
OSCE  OSCP  OSWP  
June 11, 2020, Hong Kong, China  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
