# GameMan

A handheld Game Boy emulator with a Fat form factor,  tactile buttons, 3.5" display, and USB-C for both charging and loading ROMs. Built around the ESP32-S3.

## Schematic

<img width="1724" height="978" alt="GameMan" src="https://github.com/user-attachments/assets/ec9d37b4-7419-43f6-abf4-752a1b26f6dc" />

## PCB

<img width="430" height="641" alt="image" src="https://github.com/user-attachments/assets/c9a2e07b-a6f1-462d-a7f8-a4ba07ee2e87" />

Full schematic PDF: [GameMan.pdf](https://github.com/user-attachments/files/27543807/GameMan.pdf) <img width="1054" height="724" alt="image" src="https://github.com/user-attachments/assets/139d2297-83d3-4588-bc98-e76dda391d51" />


## How it works

The ESP32-S3 runs Peanut-GB and drives a 3.5" SPI display. ROMs live on an SD card built into the display module. , drag a ROM onto it, unplug, and play. 

Battery charging goes through a TP4056. The ESP32 controls the charge enable pin in software so I can add things like charge limiting later. Battery voltage reads through a voltage divider on an ADC pin for a charge percentage estimate.

Controls are nine buttons total. The D-pad is a 5-button cluster with SELECT in the center. A, B, Start, and Menu sit on the right side.

## Specs

| Component | Part |
|---|---|
| MCU | ESP32-S3-DevKitC-1 N8R8 |
| Display | 3.5" IPS ST7796U, 480×320 |
| Touch | FT6336U over I2C |
| Storage | Micro SD (on display module) |
| Battery | 3.7V LiPo |
| Charging | TP4056 |
| Regulation | AMS1117-3.3 LDO |
| USB | USB-C, charging + OTG game loading |

Full BOM is in `/Production/bom.csv`.

## Repo structure

- `/KiCad` — schematic and PCB files
- `/Production` — gerbers, BOM, drill files
- `/Firmware` — in progress

## Status

PCB design done. Firmware not started yet
