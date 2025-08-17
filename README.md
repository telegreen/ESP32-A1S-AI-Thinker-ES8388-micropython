# ESP32-A1S AI-Thinker Audio kit v2.2 with ES8388 DAC Micropython 1.23 Firmware Build 
### ESP32-A1S AI-Thinker Audio kit v2.2 Micropython integration
  Successfully tested on Ai-Thinker Audio kit v2.2 A436 board with DAC ES8388 
#### (DAC config: `bck=27,ws=25,do=26,sda=33,scl=32,i2c=16`)

![alt text](https://github.com/telegreen/ESP32-A1S-AI-Thinker-ES8388-micropython/blob/main/img/photo_2025-01-03_21-14-17.jpg)

Check board id:  

`esptool --chip esp32 --port COM6 flash_id`
```
esptool.py v4.7.0
Serial port COM6
Connecting.........
Chip is ESP32-D0WD-V3 (revision v3.1)
Features: WiFi, BT, Dual Core, 240MHz, VRef calibration in efuse, Coding Scheme None
Crystal is 40MHz
MAC: 08:a6:f7:b2:27:f8
Uploading stub...
Running stub...
Stub running...
Manufacturer: 20
Device: 4016
Detected flash size: 4MB
Hard resetting via RTS pin...
```

Burn firmware to board from folder ./firmware :

`esptool -p COM6 -b 460800 --before default_reset --after hard_reset --chip esp32  write_flash --flash_mode dio --flash_size detect --flash_freq 40m 0x1000 bootloader.bin 0x8000 partition-table.bin 0x10000 mpy-1.23.0-ESP32-A1S-Audio-DAC-ES8388.bin`

```
...
Configuring flash size...
Auto-detected Flash size: 4MB
Flash will be erased from 0x00001000 to 0x00006fff...
Flash will be erased from 0x00008000 to 0x00008fff...
Flash will be erased from 0x00010000 to 0x001edfff...
Compressed 23040 bytes to 14711...
Wrote 23040 bytes (14711 compressed) at 0x00001000 in 0.5 seconds (effective 387.2 kbit/s)...
Hash of data verified.
Compressed 3072 bytes to 115...
Wrote 3072 bytes (115 compressed) at 0x00008000 in 0.1 seconds (effective 178.5 kbit/s)...
Hash of data verified.
Compressed 1954384 bytes to 1314503...
Wrote 1954384 bytes (1314503 compressed) at 0x00010000 in 34.8 seconds (effective 449.4 kbit/s)...
Hash of data verified.
```


```
MicroPython v1.23.0-preview.322.g5114f2c1e.dirty on 2024-12-31; ESP-Audio Lyart v4.3 with ESP32
Type "help()" for more information.
```

## Links:

- Success building ESP-ADF with Audio command into Micropython?
https://esp32.com/viewtopic.php?t=34960

- Build ESP-ADF firmware:
https://github.com/espressif/esp-adf/tree/master/micropython_adf

- Use MicroPython: 
https://github.com/espressif/esp-adf/tree/master/micropython_adf/examples

https://github.com/Ai-Thinker-Open/ESP32-A1S-AudioKit


## Related projects with ESP32 A1S AI-Thinker Audio Kit Board:

### - Squeezelite-esp32 
- is an audio software suite made to run on espressif's esp32 and esp32-s3 wifi (b/g/n) and bluetooth chipsets.
- https://sle118.github.io/squeezelite-esp32-installer/

