# Getting started

This document describes how to get started with the Device Connector.

## Required hardware

* An [FRDM-K64F](http://developer.mbed.org/platforms/frdm-k64f/) board.
* An Ethernet connection to the internet.
* An Ethernet cable.
* A micro-USB cable.

## Required software

* [yotta](https://github.com/ARMmbed/yotta): used to programs. Please note that **yotta has its own set of dependencies**, listed in the [installation instructions](http://armmbed.github.io/yotta/#installing-on-windows).
* [ARM GCC toolchain](https://launchpad.net/gcc-arm-embedded). Refer to the yotta installation page (above) for instructions on how to install the toolchains.
* If your OS is Windows, please follow the installation instructions [for the serial port driver](https://developer.mbed.org/handbook/Windows-serial-configuration).

## Setting up the environment

There are three main phases to this example:

- Setting up an account.
- Configuring an example mbed program with a server address, building with yotta, loading onto board and connecting the board using Ethernet.
- Deploying a sample web app.

### Create a Device Connector account

1. Go to the [Device Connector site](http://connector.mbed.org) and log in using your mbed.org username and password.
2. Make a note of your domain. It's printed in the top right-hand side of the website.
3. Click on the API Tokens tab at the top of the screen and create a new API token. Make a note of your API token.

### mbed build instructions

#### Building

1. Connect the FRDM-K64F to the internet using the Ethernet cable.
2. Connect the FRDM-K64F to the computer with the micro-USB cable, being careful to use the micro-USB port labeled "OpenSDA".
3. Clone **connector-mbed-client** from [connector-mbed-client](https://github.com/ARMmbed/connector-mbed-client).
4. Open the file `main.cpp` and replace `CS_DOMAIN = xxxx` with your domain. For example, if your domain is `abc123`, you would enter `CS_DOMAIN = abc123`.
5. Open a terminal and navigate to the connector-mbed-client directory (e.g. `cd connector-mbed-client`).
6. Set up the target device by entering `yotta target frdm-k64f-gcc`.
7. Enter `yotta build`.

#### Flashing to target device

1. Your binary file will be under `build/frdm-k64f-gcc/test/connector-mbed-client` and its name will be `connector-mbed-client.bin`. Drag and drop the binary file to the board. This will flash the binary to the target MCU.
2. Press the reset button to run the program.

## Deploying a sample web app

This repository contains a simple website that demonstrates the use of the Device Connector's web API.

### One click deploy to Heroku

Go to [connector-sample-webapp](https://github.com/rainierwolfcastle/app) and click on the purple "Deploy to Heroku" button. Once deployed go to your newly created website.

### Using the website

The front page contains a form with fields for your API Token and your domain.

1. Copy your API token and your domain into the form and click the "Get My Devices" button.
2. Your devices should then appear in a new page.
3. The Button Presses column shows how many times the SW2 button on your mbed has been pressed. Press the SW2 button on your mbed and watch the counter increase.
