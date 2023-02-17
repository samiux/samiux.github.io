|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Lychee 荔枝 - ClamAV On-Access Scanning Installer Script

ClamAV's On-Access scanning can detect the known malwares/virus in real time.  Any Debian/RPM based Linux system can install this script when FANOTIFY is configured in your Linux kernel.

## Verify

```
cat /boot/config-$(uname -r) | grep FANOTIFY
```

The suitable display is :

```
CONFIG_FANOTIFY=y
CONFIG_FANOTIFY_ACCESS_PERMISSIONS=y
```

When you see the following message, your Linux system is not suitable for this script.

```
CONFIG_FANOTIFY_ACCESS_PERMISSIONS is not set
``` 

## Softwares

- ClamAV 1.0.1
- Ubuntu 22.04.1 LTS and Fedora 37 are tested

Remarks : ClamAV uses about 3GB RAM.

## Change Log

### Version 0.5 (Dated FEB 16, 2023) (Latest)  
- Updated to ClamAV 1.0.1  

### Version 0.4 (Dated JAN 05, 2023)   
- Minor modified  

### Version 0.3 (Dated JAN 01, 2023)   
- Add configure file  

### Version 0.2 (Dated DEC 30, 2022)   
- Add uninstallers  

### Version 0.1 (Dated DEC 28, 2022)   
- First release for ClamAV 1.0.0  

Remarks : This script is developed by Samiux and it is released under GPLv3.  It is an Open Source Project.

## Install and/or Update

Download the script.
```
git clone https://github.com/samiux/lychee
```

Edit the related parts at the top parts of the script.
```
cd lychee

nano lychee.conf
```

Then run the script to install ClamAV On-Access scanning.
```
sudo chmod +x clamav-installer
sudo ./clamav-installer
```
Please allow about 1 to 2 minutes for ClamAV to load the signatures.   
You can run this script at any time on the same Linux system box without any harm.

## Uninstall

(a) DEB Package
```
sudo chmod +x deb-clamav-uninstaller
sudo ./deb-clamav-uninstaller
``` 

(b) RPM Package
```
sudo chmod +x rpm-clamav-uninstaller
sudo ./rpm-clamav-uninstaller
``` 

(c) Remove lychee directory
```
sudo rm -R lychee
```

## Test file
- [Eicar Test File](https://www.eicar.org/download-anti-malware-testfile/)  

## Known issues

- [BUG : /home and it's sub-directories cannot be used in OnAccessIncludePath](https://github.com/Cisco-Talos/clamav/issues/799)  
- ClamAV uses at least 3GB RAM.  
- Non-existent directory will cause high CPU usage.  
- Cannot detect virus on Pen Drive.  

## Reference

- [ClamAV Official Site](https://www.clamav.net/)  
- [ClamAV Downloads](https://www.clamav.net/downloads)  
- [ClamAV Documentation](https://docs.clamav.net/)  
- [ClamAV GitHub](https://github.com/Cisco-Talos/clamav)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
