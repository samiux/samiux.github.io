# Realtime Kernel for Ubuntu 24.04 LTS

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

To enable Realtime Kernel in Ubuntu 24.04 LTS should be registered to Ubuntu Pro first.  After the registered, you can enable the realtime kernel and following the instruction on the screen.

```bash
sudo apt install ubuntu-pro-client
sudo pro attach <token>
sudo pro enable realtime-kernel
```

The most simply way is to set to kernel boot parameters.

```bash
sudo nano /etc/default/grub
```

Add the following to the ```GRUB_CMDLINE_LINUX_DEFAULT```

```bash
amd_pstate=disable rcu_nocb_poll rcu_nocbs=1-15 nohz=on nohz_full=1-15 kthread_cpus=0 irqaffinity=0 isolcpus=managed_irq,domain,1-15
```

The final looking on my AMD Ryzen 7 4800U (8-core 16 threadings) is as the following and make sure pstate is disabled.
``` bash
GRUB_CMDLINE_LINUX_DEFAULT="amd_pstate=disable rcu_nocb_poll rcu_nocbs=1-15 nohz=on nohz_full=1-15 kthread_cpus=0 irqaffinity=0 isolcpus=managed_irq,domain,1-15 libata.force=noncq iommu.strict=1 iommu.passthrough=1 quiet splash"
```
```bash
sudo update-grub
```

## IMPORTANT 

In the case of lock up when boot, you need to press either ```ESC``` or ```Shift``` key, depends on whether it is BIOS or EFI, when boot up to go to GRUB boot menu in order to boot from previous kernel. 

Virtualbox does not work on realtime kernel on my desktop for example.  It is because not all applications can work for realtime kernel.  Meanwhile, the boot up time is slower than low-latency kernel.  I think low-latency kernel is more suitable for desktop usage.

## Reference

- [Tuning a real-time kernel](https://ubuntu.com/blog/real-time-kernel-tuning)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
