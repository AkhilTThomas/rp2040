# Led blink on Raspberry Pi Pico Zero

datasheet
cross compile
flashing

# Pre requisite

Install [Usbipd](https://github.com/dorssel/usbipd-win)
`winget install usbipd`
This is needed to allow USB pass through to WSL2

Tools for cross-compiling and flashing
Cross compiler : `sudo apt install gcc-arm-none-eabi`
Add the compiler toolchain for rust: `rustup target add thumbv6m-none-eabi`
`cargo install cargo-binutils`
`cargo install elf2uf2-rs`

## How to flash

Press and hold the BOOTSEL pin before connecting the USB to the PC to enter USB mode.
RP2 should now get listed as a storage device

Verify by running `lsusb`
```
Bus 002 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
Bus 001 Device 004: ID 2e8a:0003 Raspberry Pi RP2 Boot
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
```

### VSCode tasks
1. Attach Raspberry Pi RP2 Boot - Queries the usb devices for RP2 and attaches to WSL2
2. Detach Raspberry Pi RP2 Boot - Detach RP2 from WSL2 to windows

### Reference
[0] https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf
[1] https://www.fullstacklabs.co/blog/rust-raspberry-pi-pico-blink
