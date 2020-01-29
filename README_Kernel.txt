
HOW TO BUILD KERNEL FOR GT-S7278

1. How to Build
	- get Toolchain
	download and install arm-eabi-4.6 toolchain for ARM EABI.
	Extract kernel source and move into the top directory.

	add below 3 lines to kernel Makefile 

	export CROSS_COMPILE=../arm-eabi-4.6/bin/arm-eabi-
	export ARCH=arm
	export USE_SEC_FIPS_MODE=true
	
	
	$ make logan-vlx_defconfig
	$ make
	$ make zImage

2. Output files
	- Kernel : kernel/arch/arm/boot/zImage
	- module : kernel/drivers/*/*.ko
	
3. How to make .tar binary for downloading into target.
	- change current directory to Kernel/arch/arm/boot
	- type following command
	$ tar cvf GT-S7278_Kernel.tar zImage
