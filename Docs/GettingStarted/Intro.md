# Getting started

This document describes briefly the steps required to start use of LWM2M Client example application on mbed OS. LWM2M Client example application demonstrates how to perform OMA LWM2M bootstrap with bootstrap server and how to register and unregister to mbed Device Server.

## Required hardware

* A [FRDM-K64F](http://developer.mbed.org/platforms/frdm-k64f/) board
* An ethernet connection to the internet
* An ethernet cable
* A micro-USB cable

## Required Software

* [Yotta](http://docs.yottabuild.org/#installing) - to build example programs

## Setting up the environment

There are 3 main phases to this example:
- Setting up an account.
- Configure example mbed program with server address, build with yotta, load onto board, plug board into ethernet.
- Deploying a sample web app.

## Create a Device Connector account

## mbed Build instructions

### Building

1. Connect the frdm-k64f to the internet using the ethernet cable
2. Connect the frdm-k64f to the computer with the micro-USB cable, being careful to use the micro-usb port labled "OpenSDA"
3. Install Yotta. See instructions from http://docs.yottabuild.org/#installing
4. Install needed toolchains (arm-none-eabi-gcc). Refer to the yotta installation page (in step 1 above) for instructions on how do install the toolchains.
5. Clone **connector-mbed-client** from https://github.com/ARMmbed/connector-mbed-client
6. `cd ` **connector-mbed-client**
7. Open file main.cpp, edit your domain in place of `CS_DOMAIN = xxxx`. For example, if your domain is 'abc123', you would enter `abc123`
8. Set up target device, `yotta target frdm-k64f-gcc`
9. Type `yotta build`

Binary file will be created to /build/frdm-k64f-gcc/source/ - folder

### Flashing to target device

You need to plug in the USB cable on J26 port on the K64F borad and other end into  USB port of your computer.
Supported mbed board have drag&drop flashing capability. All you need to do is to copy the binary file to
board's usb mass storage device and it will be automatically flashed to target MCU after reset.
You can find the binary file from `cd connector-mbed-client/build/frdm-k64f-gcc/test/connector-mbed-client/` with following name `connector-mbed-client.bin`
Press the reset button to run the program.

## Deploying a sample web app

Instructions for deploying a sample webb app are available here: https://github.com/ARMmbed/connector-sample-webapp
