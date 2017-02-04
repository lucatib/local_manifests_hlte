manifests
=========

Local manifests for hlte

//---------------------

Kernel:
crossdev -S -P -v EXTRA_ECONF="-march=armv7-a -mfpu=neon-vfpv4 -ffast-math" -t armv7a-hardfloat-linux-gnueabi

ARCH=arm scripts/kconfig/merge_config.sh arch/arm/configs/selinux_defconfig arch/arm/configs/msm8974_sec_hlte_eur_defconfig

ARCH=arm CROSS_COMPILE=armv7a-hardfloat-linux-gnueabi- make zImage -j10


//---------------------

Image:

emerge heimdall

sudo heimdall flash --SYSTEM out/target/product/hlte/system.img

sudo heimdall flash --BOOT out/target/product/hlte/boot.img
