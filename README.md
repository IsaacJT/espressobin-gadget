# Marvell EspressoBin Gadget Snap

This repository contains the official Ubuntu Core gadget snap for the [Marvell EspressoBin v5](http://espressobin.net/).

See these other repositories for building an Ubuntu Core image:

- https://github.com/IsaacJT/espressobin-kernel-snap

## Gadget Snaps

Gadget snaps are a special type of snaps that contain device specific support code and data. You can read more about them in the [snapd wiki](https://github.com/snapcore/snapd/wiki/Gadget-snap).

## Building

To build the gadget snap locally please use `snapcraft`.

To cross-compile the snap on Ubuntu 20.04, use the following command:

    snapcraft --destructive-mode --target-arch=arm64 --enable-experimental-target-arch

## Booting

As the EspressoBin's U-Boot resides in the onboard SPI flash, the best way to update it is to flash the `flash-image.bin` file from within U-Boot using the `sf` tools.

In order to minimise the number of SPI flash updates, the boot script to load Ubuntu Core resides on the first partition of the generated Ubuntu Core SD card image. 
