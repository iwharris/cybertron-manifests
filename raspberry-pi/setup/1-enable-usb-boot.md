(from https://jamesachambers.com/new-raspberry-pi-4-bootloader-usb-network-boot-guide/)

## Set up an SD card with Raspberry Pi OS (Raspbian)

## Update everything

```bash
sudo apt update && sudo apt full-upgrade -y
```

## Verify that EEPROM is up to date

```bash
sudo rpi-eeprom-update
```

If updates are available, rerun the command and append `-a` to update

## Edit Bootloader configuration

```bash
sudo -E rpi-eeprom-config --edit
```

Change the `BOOT_ORDER` to `0xf41`, which will attempt to boot from USB first, falling back to SD

## Use the Raspberry Pi Imager to install an OS

Install Ubuntu 20.04.3 LTS and then follow the guide [here](https://jamesachambers.com/raspberry-pi-4-ubuntu-20-04-usb-mass-storage-boot-guide/) to make Ubuntu bootable (this won't be necessary in future releases).
