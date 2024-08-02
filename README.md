# labrador-linux-6.9

Linux 6.9 kernel source code for Caninos Labrador.

## About

This repository contains the source code for both the Caninos Labrador's
 64-bit and 32-bit Linux kernels, along with Debian-specific patches and
 security updates.

## Clean Build

Before compilation, please ensure that you have the following libraries and/or
 tools installed on your machine:
 
1) GNU Binutils environment and Native GCC compiler
2) GCC cross-compiler targeting "gcc-aarch64-linux-gnu"
3) GCC cross-compiler targeting "gcc-arm-linux-gnueabihf"
4) Make build tool
5) Git client
6) Bison and Flex development libraries
7) NCurses and LibSSL development libraries
8) Pahole and LibELF development libraries
9) U-Boot Tools libraries

```
$ sudo apt update
$ sudo apt install build-essential binutils make git
$ sudo apt install gcc-arm-linux-gnueabihf gcc-aarch64-linux-gnu
$ sudo apt install bison flex libncurses-dev libssl-dev u-boot-tools
$ sudo apt install libelf-dev pahole
```

After installing these tools, clone this repository to your computer.
 Then, navigate to its main directory and execute its makefile.

```
$ git clone https://github.com/caninos-loucos/labrador-linux-6.9.git
$ cd labrador-linux-6.9
$ make all
$ make all32
```

## Incremental Build (32-bit/64-bit)

If you want to perform an incremental build, follow these steps:

1) To load the configuration:

```
make config32
```
```
make config
```

> Note: This will overwrite any previously configured settings.

2) To customize which modules are compiled into your kernel image:

```
make menuconfig32
```
```
make menuconfig
```

3) To compile the device tree binary blob:

```
make dtbs32
```
```
make dtbs
```

4) To compile your kernel image:

```
make kernel32
```
```
make kernel
```

5) To reset all configurations:

```
make clean32
```
```
make clean
```
6) To copy the kernel image and modules to an SDcard:

```make install```

```make install32```

## Kernel

After successful compilation, kernel should be located in the "release" folder.

## Contributing

**Caninos Loucos Forum: <https://forum.caninosloucos.org.br/>**

**Caninos Loucos Website: <https://caninosloucos.org/>**
