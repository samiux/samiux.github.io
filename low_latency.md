# Low latency Kernel for Ubuntu 24.04 LTS and Debian 12.5

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

A low-latency Linux kernel is designed to minimize the time it takes for the kernel to respond to events. This responsiveness is crucial for applications that require real-time or near-real-time performance. Here are the primary advantages of using a low-latency Linux kernel:

1. **Improved Responsiveness**: The low-latency kernel can respond to interrupts and scheduling requests more quickly, making it ideal for applications where timing is critical, such as in audio processing, video processing, or gaming.

2. **Better Real-Time Performance**: For real-time applications, having a kernel that can guarantee or significantly reduce latency is essential. The low-latency kernel supports real-time scheduling policies, making it suitable for applications that require deterministic response times.

3. **Enhanced Multithreading Support**: Applications that utilize multiple threads benefit from improved context switching and scheduling, allowing threads to be processed in a more timely manner, which can result in smoother performance.

4. **Lower Jitter**: Jitter refers to the variability in delays experienced by packets or data. A low-latency kernel provides more consistent processing times, which is especially important in audio and video streaming applications.

5. **Optimized Scheduling**: The scheduler in a low-latency kernel is optimized for preemption, allowing high-priority tasks to run without significant delay, which can be beneficial for interactive applications.

6. **Suitable for Embedded Systems**: Many embedded systems that require real-time capabilities can leverage a low-latency kernel, making it appropriate for applications like robotics, industrial automation, and telecommunications.

7. **Improved Performance Under Load**: In scenarios where multiple processes compete for CPU resources, a low-latency kernel can manage these processes more effectively, minimizing delays even under heavy load conditions.

8. **Support for High-Frequency Devices**: Devices with high sampling rates, such as audio interfaces and sensors, benefit from low-latency performance, which allows them to keep up with data input and minimize delays in processing.

9. **Compatibility with Real-Time Extensions**: Many low-latency kernels are designed to work with or provide a foundation for real-time extensions (like the PREEMPT-RT patches), allowing for even tighter control over task scheduling and execution.

In summary, using a low-latency Linux kernel is crucial for applications where timing is paramount. It allows for improved performance, reduces response times, and enhances the overall user experience in real-time and interactive applications.

## Setting it up

Linux kernel version 6.1.x or above can be configured to low latency kernel.  Ubuntu 22.04 comes with 6.8.x kernel while Debian 12.5 comes with 6.1.x kernel.  

"A fully preemptible kernel is most suitable for low-latency workloads, such as gaming, live streaming, multimedia and etc."

"Typical server of high performance computing workloads may be prefer a less responsive kernel with fewer interruptions, yet capable of sustaining higher computational performance. In such a scenario, voluntary preemption may be preferred."

However, Intrusion Detection and Prevention System (IDPS) is suitable for fully preemptible kernel in my own opinion.  Meanwhile, the desktop and server performance are also boosted a lot under the low latency kernel.

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
preempt=full nohz=on nohz_full=all threadirqs rcu_nocbs=all rcutree.enable_rcu_lazy=1
```

The final looking is 
``` bash
GRUB_CMDLINE_LINUX_DEFAULT="preempt=full nohz=on nohz_full=all threadirqs rcu_nocbs=all rcutree.enable_rcu_lazy=1 quiet splash"
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

My CPU is AMD Ryzen 7 4800U and the grub setting is :

```
GRUB_CMDLINE_LINUX_DEFAULT="amd_pstate=guided preempt=full nohz=on nohz_full=all threadirqs rcu_nocbs=all rcutree.enable_rcu_lazy=1 libata.force=noncq iommu.strict=1 iommu.passthrough=1 quiet splash"
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

In the case of lock up when boot, you need to press either ```ESC``` or ```Shift``` key, depends on whether it is BIOS or EFI, when boot up to go to GRUB boot menu in order to boot from previous kernel. 

## Reference

- [Fine-Tuning the Ubuntu 24.04 Kernel for low latency, throughput, and power efficiency](https://discourse.ubuntu.com/t/fine-tuning-the-ubuntu-24-04-kernel-for-low-latency-throughput-and-power-efficiency/44834)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
