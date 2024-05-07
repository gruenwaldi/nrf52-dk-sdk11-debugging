# nrf52-dk-sdk11-debugging

This repository can only be used in combination with [Nordic SDK 11.0.0](https://www.nordicsemi.com/Products/Development-software/nRF5-SDK/Download#infotabs) and the NRF52 Development kit.

> **Please download the SDK11 and then copy the [.vscode](./.vscode) folder into the SDK11 folder.**


It is used to demonstrate and test debugging of the NRF52 Development Kit.
Further information can be read at [Embedded Explorer](https://embeddedexplorer.com/nrf52-debug-vscode/), thus the content here is modified to the necessary requirements.

## Requirements

This example is based on following components:

- NRF52_DK
- [Nordic SDK 11 with s132](https://www.nordicsemi.com/Products/Development-software/nRF5-SDK/Download#infotabs)
- VSCode
    - [Cortex-Debug](https://marketplace.visualstudio.com/items?itemName=marus25.cortex-debug)
- [GNU Arm Enbedded Toolchain v10.3](https://developer.arm.com/downloads/-/gnu-rm)
- make 
- [NRF Commandline Tool](https://www.nordicsemi.com/Products/Development-tools/nrf-command-line-tools/download)

This example was tested on: 
- NRF52_DK version 2.0.0 and 3.0.0
- NRF Commandline tool v10.21.0

## Examples

The following examples have been tested and the corresponding debug configuration was created:

- [Blinky Example blank](https://infocenter.nordicsemi.com/topic/com.nordic.infocenter.sdk5.v11.0.0/gpio_example.html)
- [Blinky Example s132](https://infocenter.nordicsemi.com/topic/com.nordic.infocenter.sdk5.v11.0.0/gpio_example.html)
- [Experimental BLE Blinky Application](https://infocenter.nordicsemi.com/topic/com.nordic.infocenter.sdk5.v11.0.0/ble_sdk_app_blinky.html)

## Setup toolchain, compile and run code

Follow this [developing guide](https://embeddedexplorer.com/nrf52-gcc-tutorial/) to install all the tools you need. 
**Beware that the versions might be different to this example!**

>  **Make sure to correctly setup your `<InstallFolder>/components/toolchain/gcc/Makefile.posix`, so that it points to your installed GNU Arm Embedded Toolchain**

## launch.json

The file [`launch.json`](./.vscode/launch.json) holds the necessary information for debugging the examples.

## Compile and debug the examples

The examples are build from the commandline, so you need to open a Terminal for that

### Blinky Example blank

- go to `<InstallFolder>/examples/peripheral/blinky/pca10040/blank/armgcc`
- type `make` to build the firmware
- type `make flash` to program the firmware onto the *NRF52_DK* board
- go to your **Run and Debug** extension and select *Cortex Debug blinky blank* 
    - now you can start the debugging

### Blinky Example s132

- go to `<InstallFolder>/examples/peripheral/blinky/pca10040/s132/armgcc`
- type `make` to build the firmware
- type `make flash_softdevice` to program the **Softdevice** onto the *NRF52_DK* board
- type `make flash` to program the firmware onto the *NRF52_DK* board
- go to your **Run and Debug** extension and select *Cortex Debug blinky blank* 
    - now you can start the debugging

### Experimental BLE Blinky Application

- go to `<InstallFolder>/examples/ble_peripheral/experimental_ble_app_blinky/pca10040/s132/armgcc`
- type `make` to build the firmware
- type `make flash_softdevice` to program the **Softdevice** onto the *NRF52_DK* board
- type `make flash` to program the firmware onto the *NRF52_DK* board
- go to your **Run and Debug** extension and select *Cortex Debug blinky blank* 
    - now you can start the debugging
- now you can also start your NRF Connect App on your Smartphone and connect and play with the board

#### Additional information sources

- [debugging guide](https://embeddedexplorer.com/nrf52-debug-vscode/)

                 
Have fun ;-) 



