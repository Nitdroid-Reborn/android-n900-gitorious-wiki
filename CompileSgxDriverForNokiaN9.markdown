cd <NITDROID_DIRECTORY>
NITDROID_DIRECTORY=`pwd`

# making kernel modules

cd hardware/ti/sgx
make -C eurasiacon/build/linux2/omap4430_android KERNELDIR=$KERNELDIR SGXCORE=530 SGXCOREREV=125 CROSS_COMPILE=arm-eabi- OMAPES=5.x ARCH=arm

cd gfx_rel_es5.x_android/
./install.sh --root $NITDROID_DIRECTORY/out/target/product/n9 -v
