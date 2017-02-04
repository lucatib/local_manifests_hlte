manifests
=========

Local manifests for hlte

//---------------------

Kernel:
crossdev --gcc 5.4.0 --genv 'USE="-fortran -mudflap -nls -openmp multilib" EXTRA_ECONF="--with-cpu=cortex-a15 -mfpu=neon-vfpv4 -ffast-math --with-float=hard"' -t arm-linux-gnueabihf

ARCH=arm scripts/kconfig/merge_config.sh arch/arm/configs/selinux_defconfig arch/arm/configs/msm8974_sec_hlte_eur_defconfig

//---------------------

Image:

emerge heimdall

sudo heimdall flash --SYSTEM out/target/product/hlte/system.img

sudo heimdall flash --BOOT out/target/product/hlte/boot.img
