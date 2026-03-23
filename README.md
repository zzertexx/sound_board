# Soundboard — 16-key Macropad

A custom 16-key macropad built with a Seeed Studio XIAO RP2040, per-key RGB LEDs, and a 0.91" OLED display. Made for [Hack Club](https://hackclub.com/).

---

## Features

- 16 MX-compatible switches in a 4×4 matrix
- Per-key SK6812 MINI-E RGB LEDs
- 0.91" OLED display (I2C)
- Seeed Studio XIAO RP2040 microcontroller
- KMK firmware (CircuitPython)
- 3D printed case with heatset inserts

---

## Bill of Materials

| Component | Quantity |
|---|---|
| Seeed Studio XIAO RP2040 | 1 |
| MX-style switches | 16 |
| 1N4148 diodes (through-hole) | 16 |
| SK6812 MINI-E LEDs | 16 |
| 0.91" OLED display (GND-VCC-SCL-SDA) | 1 |
| DSA white blank keycaps | 16 |
| Capacitor 100µF | 1 |
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

Designed in KiCad 7. All source files are in the `/pcb` directory.

- 4×4 keyboard matrix with diodes for anti-ghosting
- SK6812 MINI-E LEDs placed on bottom layer under each switch
- OLED connected via I2C
- Decoupling capacitors on 5V rail for LED stability

---

## License

MIT License — do whatever you want with it!

---

*Built as part of Hack Club's hardware grant program.*
