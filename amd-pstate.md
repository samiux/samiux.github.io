|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# AMD Ryzen CPU Performance Scaling Driver (amd-pstate) in Ubuntu 22.04.1 LTS

What is amd-pstate driver?

According to the [Admin Guide of Kernel](https://docs.kernel.org/admin-guide/pm/amd-pstate.html), amd-pstate is the AMD CPU performance scaling driver that introduces a new CPU frequency control mechanism on modern AMD APU and CPU series in Linux kernel. The new mechanism is based on Collaborative Processor Performance Control (CPPC) which provides finer grain frequency management than legacy ACPI hardware P-States. Current AMD CPU/APU platforms are using the ACPI P-states driver to manage CPU frequency and clocks with switching only in 3 P-states. CPPC replaces the ACPI P-states controls and allows a flexible, low-latency interface for the Linux kernel to directly communicate the performance hints to hardware.

According to [bug tracking thread of Ubuntu](https://bugs.launchpad.net/ubuntu/+source/linux/+bug/1956509), the kernel starting from 5.15.0-35-generic can use amd-pstate driver.  The current Ubuntu 22.04.1 LTS kernel is 5.15.0-52-generic (as at this writing), you can set it up with no pain.  However, CPPC setting is a must in your BIOS.  The Ryzen 4000 series or later supports CPPC in the features.

First of all, make sure your BIOS, CPU and kernel is support for amd-pstate.

```
lshw | grep cppc
```

If you see "cppc", your CPU is support amd-pstate.

```
cat /boot/config-5.15.0-52-generic | grep PSTATE
```

if you see the following, your Ubuntu kernel is support amd-pstate.

```
CONFIG_X86_INTEL_PSTATE=y
CONFIG_X86_AMD_PSTATE=y
```

Make sure you ```Enable``` ```CPPC``` setting in your BIOS.  Then add ```amd_pstate.enable=1``` to the ```/etc/default/grub```.

For example :
```
GRUB_CMDLINE_LINUX_DEFAULT="amd_pstate.enable=1 acpi_enforce_resources=lax trace_clock=local tsc=unstable amdgpu.cik_support=1 amdgpu.si_support=1 libata.force=noncq iommu.strict=1 iommu.passthrough=1 scsi_mod.use_blk_mq=1 quiet splash"
```

Run ```sudo update-grub``` and then reboot your box.

To verify the driver, you can do the following and make sure you see the amd-psate :

Method 1 :
```
journalctl -b 0 | grep pstate
```
```
powernow_k8: WTF driver: amd-pstate
```

Method 2 :
```
cat /sys/devices/system/cpu/cpu0/cpufreq/scaling_driver
```
```
amd-pstate
```

Method 3 :
```
sudo apt install linux-tools-generic
sudo apt install cpupower
sudo cpupower frequency-info
```
```
analyzing CPU 0:
  driver: amd-pstate
  CPUs which run at the same hardware frequency: 0
  CPUs which need to have their frequency coordinated by software: 0
  maximum transition latency: 131 us
  hardware limits: 400 MHz - 4.33 GHz
  available cpufreq governors: conservative ondemand userspace powersave performance schedutil
  current policy: frequency should be within 400 MHz and 4.33 GHz.
                  The governor "conservative" may decide which speed to use
                  within this range.
  current CPU frequency: Unable to call hardware
  current CPU frequency: 1.10 GHz (asserted by call to kernel)
  boost state support:
    Supported: yes
    Active: yes
    Boost States: 0
    Total States: 3
    Pstate-P0:  1800MHz
    Pstate-P1:  1700MHz
    Pstate-P2:  1400MHz
```

After some experiments with this [documentation](https://www.kernel.org/doc/Documentation/cpu-freq/governors.txt), I find out that the lowest fan noise for my AMD Ryzen 7 4800U is by setting the CPU to ```conservative``` instead of ```ondemand``` or ```schedutil```.  You can set it my the following script.

```
#!/bin/bash

# Description : set "conservative" cpufreq governor for modern CPU script
# Author      : Samiux (https://samiux.github.io)
# Date        : Dec 19, 2021
# Version     : 0.2
# Resources   : (1) https://linux-sunxi.org/Cpufreq
#               (2) https://www.kernel.org/doc/Documentation/cpu-freq/governors.txt

# colour defined
GREEN='\033[0;32m'
RED='\033[0;31m'
RESET='\033[0m'

# get the total number of core/thread
CORES=$(nproc --all)
# better for battery powered device
GOVERNOR="conservative"
# most likely default setting
#GOVERNOR="ondemand"
#GOVERNOR="schedutil"
#GOVERNOR="userspace"
#GOVERNOR="powersave"
#GOVERNOR="performance"

# check if CPU has this feature
cat /sys/devices/system/cpu/cpu0/cpufreq/scaling_available_governors | grep $GOVERNOR &> /dev/null
if [ $? == 0 ]; then
	# this one
	for (( i=0; i<=$CORES-1; i++ ))
	do
		echo $GOVERNOR | sudo tee -a /sys/devices/system/cpu/cpu$i/cpufreq/scaling_governor &> /dev/null
	done
	# or simply just one liner
	#echo $GOVERNOR | sudo tee -a /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor &> /dev/null

	# display result
	echo -e "${GREEN}Governor $GOVERNOR is set!${RESET}"
else
	# display result
	echo -e "${RED}Governor $GOVERNOR is NOT supported by CPU!${RESET}"
fi

# EOF
```

Samiux    
OSCE  OSCP  OSWP    
November 6, 2022, Hong Kong, China    

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
