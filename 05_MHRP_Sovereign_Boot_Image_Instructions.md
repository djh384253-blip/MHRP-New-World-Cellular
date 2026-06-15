# 05_MHRP_Sovereign_Boot_Image_Instructions

This document details how to build a custom, secure, and lightweight Linux distribution for the Raspberry Pi 4 from scratch using Buildroot.

## 1. Configuration (configs/mhrp_rpi4_defconfig)
Ensure the following parameters are set to enable sub-4-second boot times and native cellular SDR support:
* BR2_aarch64=y
* BR2_cortex_a72=y
* BR2_LINUX_KERNEL_DEFCONFIG="bcm2711"
* BR2_TARGET_ROOTFS_INITRAMFS=y
* BR2_PACKAGE_LIBUSB=y

## 2. Cellular Init Script (/etc/init.d/rcS)
This script initializes the custom SDR driver and boots the cellular engine:
```bash
#!/bin/sh
mount -t proc proc /proc
mount -t sysfs sysfs /sys
mount -t tmpfs tmpfs /tmp
mount -t tmpfs tmpfs /dev
mdev -s
ifconfig lo 127.0.0.1 up
/usr/bin/mhrp-cellular-engine --config /etc/mhrp-cellular/cell_config.cfg &
```

## 3. Building the Image
1. Clone or download the Buildroot repository
2. Copy the mhrp_rpi4_defconfig to buildroot/configs/
3. Run: `make mhrp_rpi4_defconfig`
4. Run: `make` to compile the entire image
5. The resulting kernel and rootfs will be ready for deployment