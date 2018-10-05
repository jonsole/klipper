This document describes the steps required to build ARM micro-controller firmware under Windows 10.

Installing Required Tools
=========================

## Cygwin ##
1. Install Cygwin-x86_64 from https://cygwin.com/setup-x86_64.exe.
2. Select the following packages in addition to the defaults:
    * make
    * gcc-core
    * libncurses-devel
    * mingw64-x84_64-ncurses
    * python2
3. Set `CYGWIN` environment variable to `winsymlinks:nativestrict` to allow creation of softlinks

## Atmel/Microchip ARM Toolchain ##

1. Download ARM Toolchain 6.3.1 - Windows from http://www.microchip.com/mplab/avr-support/avr-and-arm-toolchains-c-compilers
2. Extract .zip file and copy to required location, for example `C:\arm-none-abi`
3. Append path of `bin` subdirectory (for example `C:\arm-none-abi\bin`) to `PATH` enrionment variable.


Building the micro-controller image
===================================

To compile the micro-controller code, start by Cygwin bash as administrator and then run this command to build and run the config tool:

```
make menuconfig
```

Select the appropriate micro-controller and review any other options
provided. For boards with serial ports, the default baud rate is
250000 (see the [FAQ](FAQ.md#how-do-i-change-the-serial-baud-rate) if
changing). Once configured, run:

```
make
```

