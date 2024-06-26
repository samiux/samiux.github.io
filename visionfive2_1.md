|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Howto Custom Made VisionFive2 SD Card Image (RISC-V)

VisionFive2 is a single board computer with RISC-V JH7110 CPU that is making by StarFive.  It comes with either 4GB or 8GB RAM and your can choose NVMe SSD or eMMC model.  You even can have both NVMe SSD and eMMC on one single board too.  It comes with SD Card slot by default.  It runs with normal smartphone SuperCharge 3.0 charger.  The temperature of the CPU is between 45°c and 85°c when turning on.  I recommend to run the board with heatsink or metal case.

## Step 1 :

Download the latest version of VisionFive2 Debian Desktop SD Card image.

[StarFive Official VisionFive2 Debian images](https://debian.starfivetech.com/)  

Select ```OneDrive```, folder ```202405``` and folder ```sd``` to download the image file, where ```202405``` is the latest at the time of this writing.

Extract it and burn the .img file to SD card (16GB or more) with balenaEtcher.

## Step 2 :

Placing the VisionFive2 with Ethernet ports at the bottom.  Set the switch on the top left corner of the board to ```ON``` for the upper row (1) and set the switch on the lower row (2) to ```OFF``` in order to boot from SD Card.  Default is both ```ON```.

Boot up VisionFive2 with the SD Card and login to the mininal desktop.  Username is ```user``` and password is ```starfive```, <strike>while root username is ```root``` and password is also ```starfive```</strike>.  If you do not need GNOME, just uninstall it.

Select ```Terminal``` and type the following commands to uninstall the GNOME desktop to make the device command line only and it is optional.

```bash
sudo apt autoremove --purge gnome* libreoffice* nodejs* qt* chromium* libcamera* opencv* firefox ffmpeg libasound2-plugins libgd3 libsdl2-2.0-0 libswresample4 libvlc-bin libvlc5 libvlccore9 vlc-data vlc-plugin-access-extra vlc-plugin-base vlc-plugin-fluidsynth vlc-plugin-jack vlc-plugin-notify vlc-plugin-qt vlc-plugin-samba vlc-plugin-skins2 vlc-plugin-svg vlc-plugin-video-splitter vlc-plugin-visualization libavcodec59 libavdevice59 libavfilter8 libavformat59
```

## Step 3 :

Update the hosts file.

```bash
sudo nano /etc/hosts
```

Add ```starfive``` next to the ```127.0.0.1 localhost``` making it to look like ```127.0.0.1 localhost starfive```.

## Step 4 :

Resize the partition to fit the larger size SD card.  It is because the official image is only around 3GB size that is insufficient to install any software.

```bash
df -h
```

To find out the partition with ```/``` directory.  For example, ```/dev/mmcblk1p4```.

To delete the partition ```/dev/mmcblk1p4```.

```bash
sudo fdisk /dev/mmcblk1
```
Type ```d``` to delete.

Select ```4``` (or default is already 4).

Type ```n``` and type ```4``` (or default is already 4).

Type ```w``` to write the changes to the SD Card.

```bash
sudo resize2fs /dev/mmcblk1p4
```

Type ```Enter``` for all the questions or inputs.

Double check the partition and to confirm that the ```/``` partition is occupied all the capacity of the SD card.

```bash
df -h
```

## Step 5 :

Reset the current time zone.

```bash
sudo dpkg-reconfigure tzdata
```

Generate English locales. 

```bash
sudo dpkg-reconfigure locales
```

Select all prefix is ```en``` items and set your country as default.

## Step 6 :

Set /tmp to tmpfs.

```bash
sudo cp -v /usr/share/systemd/tmp.mount /etc/systemd/system/

sudo systemctl enable tmp.mount
sudo systemctl start tmp.mount
```

## Step 7 :

Update the system.

```bash
sudo nano /etc/apt/source.list
```

Replace with the following.

```bash
deb https://deb.debian.org/debian/ unstable main contrib
deb-src https://deb.debian.org/debian/ unstable main contrib
```

Save it and run the following commands to update the system.

```bash
sudo apt update && sudo apt full-upgrade && sudo apt autoremove
```

Then you can install your desired softwares.  Such as 

```bash
sudo apt install net-tools pciutils
```

Make sure you have installed ```net-tools```.  Otherwise, you cannot run ```sudo ifconfig``` command.

## KNOWN ISSUE : 

```sudo reboot``` does not really reboot the device, it just only turn it off instead.  To power on the device, you can either re-plug in the power cable.  Wait for a few seconds.  When green light is flashing, the device is turning on.  

There is no SWAP partition.

### WORKAROUND 

```
sudo apt -y install watchdog
sudo systemctl enable watchdog.service
sudo systemctl start watchdog.service
```
Samiux  
OSCE  OSCP  OSWP    
August 12, 2023, Hong Kong, China    
Updated on October 17, 2023, Hong Kong, China  
Updated on May 13, 2024, Hong Kong, China  

### REFERENCE

- [StarFive VisionFive2 Single Board Computer](https://www.starfivetech.com/en/site/boards)  
- [StarFive Official VisionFive2 Debian images](https://debian.starfivetech.com/)  
- [WaveShare Wiki VisionFive2 SD Card Switch Setting - Chinese](https://www.waveshare.net/wiki/VisionFive2#.E5.BC.80.E6.9C.BA)  
- [VisionFive2 Github](https://github.com/starfive-tech/VisionFive2)  
- [Howto create VisionFive2 SD Card Image](https://huggingface.co/csukuangfj/visionfive2-sd-card-img)  
- [VisionFive2 Metal Case - Passive Cooling](https://forum.rvspace.org/t/new-arrival-visionfive-2-new-metal-case/3073)  
- [VisionFive2 Metal Case - Active Cooling](https://www.waveshare.com/visionfive2-case-a.htm)
- [StarFive VisionFive 2 - Ubuntu wiki](https://wiki.ubuntu.com/RISC-V/StarFive%20VisionFive%202)  
- [StarFive VisionFive 2 Documentation Centre](https://doc-en.rvspace.org/Doc_Center/visionfive_2.html)

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
