# grate-driver-linux-debian

An empty repository to host Debian packages of [grate-driver/linux](https://github.com/grate-driver/linux) kernels.

## Install

Use `dpkg -i ...` for installation.

It is still needed to update any boot configuration, e.g. `startup.nsh` to point to the right `vmlinuz-*` file. 

## Build

To build `.deb` packages,

```
make ARCH=arm grate_defconfig
make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- -j $(nproc) bindeb-pkg
```

- `.deb` files will be placed at parent directory `..`
- device tree files is at `arch/arm/boot/dts/*.dtb`


## Also see

- https://openrt.gitbook.io/open-surfacert/surface-rt/linux/efi/efi-stub-kernel
