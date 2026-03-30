# Soundboard — 16-key Macropad

A custom 16-key macropad built with a Seeed Studio XIAO RP2040, per-key LEDs, and a 0.91" OLED display. Made for [Hack Club](https://hackclub.com/).

---

## Features

- 16 MX-compatible switches in a 4×4 matrix
- Per-key SK6812 MINI-E RGB LEDs
- 0.91" OLED display
- Seeed Studio XIAO RP2040 microcontroller
- QMK firmware
- 3D printed case with sandwitch mounting

---

## Bill of Materials

| Component | Quantity |
|---|---|
| Seeed Studio XIAO RP2040 | 1 |
| MX-style switches | 16 |
| 1N4148 diodes | 16 |
| SK6812 MINI-E LEDs | 16 |
| 0.91" OLED display | 1 |
| DSA white blank keycaps | 16 |
| Resistor 330 ohms | 1 |
| M3x16mm screws | 4 |
| M3x5x4mm heatset inserts | 4 |

---

## Pin Assignment

| Pin | Signal |
|---|---|
| GP0 (PA02) | Row 0 |
| GP1 (PA4) | Row 1 |
| GP2 (PA10) | Row 2 |
| GP3 (PA11) | Row 3 |
| GP4 (PA8 SDA) | OLED SDA |
| GP5 (PA9 SCL) | OLED SCL |
| GP6 (PB08) | Column 0 |
| GP7 (PB09) | Column 1 |
| GP8 (PA7 SCK) | Column 2 |
| GP9 (PA5 MISO) | Column 3 |
| GP10 (PA6 MOSI) | LED Data |

---

## Schematic & PCB

Designed in KiCad 9.0. All source files are in the `/pcb` directory.

- 4×4 keyboard matrix with diodes
- SK6812 MINI-E LEDs placed on bottom layer under each switch
- OLED connected via I2C
- Resistor on GP10 rail for LED stability

---

## Images

<img width="1532" height="908" alt="sch" src="https://github.com/user-attachments/assets/5f8f5f90-bc32-4e90-9154-2b26d3328ea6" />
<img width="693" height="870" alt="pcb" src="https://github.com/user-attachments/assets/75dc8b23-704c-4a1c-90fb-1e438f0c019d" />
<img width="1067" height="775" alt="case" src="https://github.com/user-attachments/assets/4f814eb1-2566-4d88-881f-ed4a09825b28" />
