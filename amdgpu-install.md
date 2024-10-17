# AMD Graphics Cards Open Source Driver by AMD

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

To identify your model of your AMD Graphics Card :

```
lspci -nn | grep -E 'VGA|Display'
```

The output may be :

```
06:00.0 VGA compatible controller [0300]: Advanced Micro Devices, Inc. [AMD/ATI] Renoir [Radeon RX Vega 6 (Ryzen 4000/5000 Mobile Series)] [1002:1636] (rev c1)
```

The ```Radeon RX Vega 6``` is now supported by AMD Open Source Driver.

Go to the official site to download the driver at [Linux® Drivers for AMD Radeon™ Graphics](https://www.amd.com/en/support/download/linux-drivers.html).  

For Ubuntu, it supports 24.04.1 HWE and 22.04.5 HWE Kernel at the time of this writing.

Made sure your APT Ubuntu Source supports to install i386 libraries.

For example, 24.04.1 HWE version driver is downloaded from  ```https://repo.radeon.com/amdgpu-install/6.2.3/ubuntu/noble/amdgpu-install_6.2.60203-1_all.deb```

Install :

```
sudo dpkg -i amdgpu-install_6.2.60203-1_all.deb
sudo amdgpu-install
```

If the driver is installed successfully, reboot your system.

Samiux  
October 17, 2024, Hong Kong, China  

## REFERENCE

- [Linux® Drivers for AMD Radeon™ Graphics](https://www.amd.com/en/support/download/linux-drivers.html)  
- [Radeon™ Software for Linux® Installation](https://amdgpu-install.readthedocs.io/en/latest/)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
