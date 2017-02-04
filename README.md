manifests
=========

Local manifests for hlte

//---------------------

Kernel:

ARCH=arm scripts/kconfig/merge_config.sh arch/arm/configs/selinux_defconfig arch/arm/configs/msm8974_sec_hlte_eur_defconfig

//---------------------

Image:

emerge heimdall

sudo heimdall flash --SYSTEM out/target/product/hlte/system.img

sudo heimdall flash --BOOT out/target/product/hlte/boot.img
