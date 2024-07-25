# demeter

The hydroBUILD firmware.

## Design Guidelines

Keep demeter as dumb as possible (delegate everything that can be delegated, to noMoreHouston).

## Setting up project for the first time.

```bash
sudo apt install git
mkdir kryzen
cd kryzen
# Follow this link if you're facing authentication issues
# https://stackoverflow.com/a/68781050
git clone "paste_link"
```
```bash
pip install esptool
```

## Flashing Instructions

* `esptool.py --chip esp32c6 -b 460800 --before=default_reset --after=hard_reset write_flash --flash_mode dio --flash_freq 80m --flash_size 8MB 0x0 bootloader/bootloader.bin 0x10000 ESP32-MQTT.bin 0x8000 partition_table/partition-table.bin`


## UID Instructions

* `esptool.py read_mac`
Note the MAC address from the output, as it is UID of the device.
