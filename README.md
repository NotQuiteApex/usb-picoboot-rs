# usb-picoboot-rs - Communicating with RP2040 devices in BOOTSEL mode
## Disclaimer
- This project is intended as example code or reference implementation for communicating with Raspberry Pi Pico 1 devices directly over the PICOBOOT USB interface. This interface is exposed when the RP2040 is in BOOTSEL mode, alongside the pseudo-mass-storage-device that can also be used for flashing firmware onto a Pico device in BOOTSEL mode.
- The PICOBOOT USB interface is described in the [RP2040 datasheet](https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf) under section 2.8.5.
- PICOBOOT refers to this USB interface, and is not affiliated with or related to the [Nintendo Gamecube hardware mod](https://github.com/webhdx/PicoBoot) of the same name.
- This example code was written only for the RP2040 chip, any chips released after (such as the RP2350) are not officially supported by this program, but could function with additional work.

## How to use
Simply plug in a Raspberry Pi Pico 1 device while holding down the BOOTSEL button as you normally would when flashing firmware. Then run `cargo run` in this repo to run the program and flash the included `fw_blink.uf2` file. This firmware is provided by the [pico-examples repo](https://github.com/raspberrypi/pico-examples/).

## Notes
- When running on Linux, you may need to add some additional udev rules to allow the PICOBOOT interface to be usable by a userspace program. These udev rules can be found [here](https://github.com/raspberrypi/picotool/blob/master/udev/99-picotool.rules).
- When running on Windows, you may need to install a libusb compatible driver for the PICOBOOT interface. This driver can be installed by [Zadig](https://zadig.akeo.ie/). Simply plug in the Pico device while holding the BOOTSEL button, and install any of the listed drivers for the RP2 Boot device in Zadig.

## License
This project is provided with the 0BSD license.
