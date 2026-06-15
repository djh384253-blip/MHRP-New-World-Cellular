# 05_MHRP_Sovereign_Boot_Image_Instructions

This document details how to build a custom, secure, and lightweight Linux distribution for the Raspberry Pi 4 from scratch using Buildroot[span_1](start_span)[span_1](end_span).

### 1. Configuration (configs/mhrp_rpi4_defconfig)
Ensure the following parameters are set to enable sub-4-second boot times and native cellular SDR support[span_2](start_span)[span_2](end_span):
* BR2_aarch64=y[span_3](start_span)[span_3](end_span)
* BR2_cortex_a72=y[span_4](start_span)[span_4](end_span)
* BR2_LINUX_KERNEL_DEFCONFIG="bcm2711[span_5](start_span)"[span_5](end_span)
* BR2_TARGET_ROOTFS_INITRAMFS=y[span_6](start_span)[span_6](end_span)
* BR2_PACKAGE_LIBUSB=y[span_7](start_span)[span_7](end_span)

### 2. Cellular Init Script (/etc/init.d/rcS)
This script initializes the custom SDR driver and boots the cellular engine[span_8](start_span)[span_8](end_span):
```bash
#!/bin/sh
mount -t proc proc /proc
mount -t sysfs sysfs /sys
mount -t tmpfs tmpfs /tmp
mount -t tmpfs tmpfs /dev
mdev -s
ifconfig lo 127.0.0.1 up
/usr/bin/mhrp-cellular-engine --config /etc/mhrp-cellular/cell_config.cfg &
