# Low latency Kernel for Ubuntu 24.04 LTS and Debian 12.5

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

Linux kernel version 6.1.x or above can be configured to low latency kernel.  Ubuntu 22.04 comes with 6.8.x kernel while Debian 12.5 comes with 6.1.x kernel.  

"A fully preemptible kernel is most suitable for low-latency workloads, such as gaming, live streaming, multimedia and etc."

"Typical server of high performance computing workloads may be prefer a less responsive kernel with fewer interruptions, yet capable of sustaining higher computational performance. In such a scenario, voluntary preemption may be preferred."

However, Intrusion Detection and Prevention System (IDPS) is suitable for fully preemptible kernel in my own opinion.

Check if the kernel is ready for low-latency settings :

```bash
uname -ra
```

If the output contains ```PREEMPT_DYNAMIC```, it is ready for that settings.

The most simply way is to set to kernel boot parameters.

```bash
sudo nano /etc/default/grub
```

Add the following to the ```GRUB_CMDLINE_LINUX_DEFAULT```

```bash
preempt=full nohz_full=all threadirqs rcu_nocbs=all rcutree.enable_rcu_lazy=1
```

The final looking is 
``` bash
GRUB_CMDLINE_LINUX_DEFAULT="preempt=full nohz_full=all threadirqs rcu_nocbs=all rcutree.enable_rcu_lazy=1 quiet splash"
```
```bash
sudo update-grub
```

Additional tuning for the performance.

```bash
sudo nano /etc/rc.local
```
```bash
echo 0 | sudo tee /sys/kernel/mm/ksm/run
echo 1000 | sudo tee /sys/kernel/mm/lru_gen/min_ttl_ms
```
```bash
sudo chmod +x /etc/rc.local
```

```bash
sudo nano /etc/sysctl.d/99-low_latency_kernel.conf
```
```bash
vm.compaction_proactiveness=0
vm.dirty_ratio=5
vm.dirty_background_ratio=5
```

To check if it works after reboot :
```bash
sudo dmesg | grep Preempt
```

The result will be :
```bash
Dynamic Preempt: full
```
## Extra

To install HWE kernel :

```bash
sudo apt install linux-generic-hwe-24.04 linux-headers-generic-hwe-24.04 linux-image-generic-hwe-24.04
```

To install HWE kernel tools :

```bash
sudo apt install linux-tools-generic-hwe-24.04
```

* Remark : You are not required to uninstall the generic kernel.

## IMPORTANT 

Do NOT try to boot from Real Time Kernel as your desktop/server will be locked up.  In the case of lock up, you need to press either ```ESC``` or ```Shift``` key, depends on whether it is EFI or BIOS, when boot up to go to GRUB boot menu in order to boot from previous kernel.


## Reference

- [Fine-Tuning the Ubuntu 24.04 Kernel for low latency, throughput, and power efficiency](https://discourse.ubuntu.com/t/fine-tuning-the-ubuntu-24-04-kernel-for-low-latency-throughput-and-power-efficiency/44834)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
