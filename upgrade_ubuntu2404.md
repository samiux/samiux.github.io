|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Upgrade from Ubuntu 22.04 LTS to Ubuntu 24.04 LTS

The release date of Ubuntu 24.04 LTS is April 25, 2024 (US Time).  I tried to upgrade my Ubuntu 22.04.4 LTS to Ubuntu 24.04 LTS on April 16, 2024 (GMT +8).

It is no problem to use the daily build dated April 15, 2024 for fresh install.  However, when you upgrade from Ubuntu 22.04.4 LTS to Ubuntu 24.04 LTS, you may reach ```"Oh no!  Something has gone wrong!"``` or ```black``` screen (when you are in Virtualbox) error in the middle of the installation.  Don't panic, you can fix it with a few simple steps.  Please do NOT reboot your box or you may lost your internet connection.

## Step 1 - Upgrade

```
sudo apt update && sudo apt -y full-upgrade
```

### Desktop
```
sudo update-manager -d
```

### Server
```
sudo do-release-upgrade -d
```

## Step 2 - Error or black screen

When you reach error or black screen, you just press ```CTRL``` + ```ALT``` + ```F2``` to go to terminal.  Login as usual.  When you encounter lost your internet connection, you just issue the following command to get it back.

```
sudo dhclient
```

## Step 3 - Fix it

```
sudo dpkg --configure -a
sudo apt --fix-broken install

sudo apt update && sudo apt -y full-upgrade

sudo apt install linux-image-generic-hwe-24.04

sudo apt update && sudo apt -y full-upgrade
sudo apt autoclean && sudo apt -y autoremove

sudo apt install resolvconf
sudo systemctl enable systemd-resolved.service
sudo systemctl start systemd-resolved.service
```

## Step 4 - Reboot

```
sudo reboot
```

Your Ubuntu 22.04.4 LTS is upgraded to Ubuntu 24.04 LTS now.

The ```gnome-shell-extension-manager``` has been changed, some extensions will not be available, such as ```Harddisk LED```.  Official release of Virtualbox do not compatible with Ubuntu 24.04 LTS at the moment, you can install it from Ubuntu 24.04 LTS respository.

## Update on April 27, 2024 (GMT+8)

According to the [Noble Numbat Release Notes](https://discourse.ubuntu.com/t/noble-numbat-release-notes/39890) that the upgrade from Ubuntu 22.04 LTS will be starting automatically on August 15, 2024 and beyond.  At this moment, you cannot upgrade Ubuntu 22.04 LTS to 24.04 LTS by any method mentioned above.

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
