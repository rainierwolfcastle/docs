# Getting started

This document describes how to get started with the Device Connector.

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

### Create a Device Connector account

Go to the [Device Connector](connector.mbed.org) website and make a note of your API token and domain.

### mbed Build instructions

#### Building

1. Connect the frdm-k64f to the internet using the ethernet cable
2. Connect the frdm-k64f to the computer with the micro-USB cable, being careful to use the micro-usb port labled "OpenSDA"
3. Install Yotta. See instructions from [Yotta](http://docs.yottabuild.org/#installing)
4. Install needed toolchains (arm-none-eabi-gcc). Refer to the yotta installation page (in step 1 above) for instructions on how do install the toolchains.
5. Clone **connector-mbed-client** from [connector-mbed-client](https://github.com/ARMmbed/connector-mbed-client)
6. Change to the connector-mbed-client directory e.g. `cd connector-mbed-client`
7. Open file main.cpp, edit your domain in place of `CS_DOMAIN = xxxx`. For example, if your domain is `abc123`, you would enter `abc123`
8. Set up target device, `yotta target frdm-k64f-gcc`
9. Type `yotta build`

The binary file will be created in the `build/frdm-k64f-gcc/source` folder.

#### Flashing to target device

1. Plug in the USB cable in J26 port on the K64F board and other end into a USB port on your computer.
2. Drag and drop the binary file to
board's usb mass storage device. This will flash the binary to target MCU after reset. You can find the binary file in `build/frdm-k64f-gcc/test/connector-mbed-client` with following name `connector-mbed-client.bin`.
3. Press the reset button to run the program.

## Deploying a sample web app

This repository contains a simple web site that demonstrates the use of the Device Connector's web API.

### One click deploy to Heroku

Go to [connector-sample-webapp](https://github.com/ARMmbed/connector-sample-webapp) and click on the purple "Deploy to Heroku" button.

### Using the website

Plug these values into the boxes on the Device List web site and click the "Get My Devices" button. Your registered devices should then appear in a table.
