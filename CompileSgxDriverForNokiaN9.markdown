# prepare

cd <NITDROID_DIRECTORY>
export NITDROID_DIRECTORY=\`pwd`
export KERNELDIR=...

# making kernel modules

cd hardware/ti/sgx
make -C eurasiacon/build/linux2/omap4430_android KERNELDIR=$KERNELDIR SGXCORE=530 SGXCOREREV=125 CROSS_COMPILE=arm-eabi- OMAPES=5.x ARCH=arm

# installing userland binaries (graphics HAL)

cd gfx_rel_es5.x_android/
./install.sh \--root $NITDROID_DIRECTORY/out/target/product/n9 -v
