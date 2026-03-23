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
| Capacitor 100nF | 1 |
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

## Firmware

This macropad runs [KMK](https://github.com/KMKfw/kmk_firmware) — a CircuitPython keyboard firmware.

### Setup

1. Flash CircuitPython onto the XIAO RP2040
2. Copy KMK library to the board
3. Copy `code.py` to the root of the board

### Basic `code.py` example

```python
import board
from kmk.kmk_keyboard import KMKKeyboard
from kmk.keys import KC
from kmk.scanners import DiodeOrientation

keyboard = KMKKeyboard()

keyboard.col_pins = (board.D7, board.D8, board.D9, board.D10)
keyboard.row_pins = (board.D0, board.D1, board.D2, board.D3)
keyboard.diode_orientation = DiodeOrientation.COL2ROW

keyboard.keymap = [
    [
        KC.A, KC.B, KC.C, KC.D,
        KC.E, KC.F, KC.G, KC.H,
        KC.I, KC.J, KC.K, KC.L,
        KC.M, KC.N, KC.O, KC.P,
    ]
]

if __name__ == '__main__':
    keyboard.go()
```

---

## Case

3D printed case designed in Fusion 360. Files are in the `/case` directory.

- **Top plate** — 14mm × 14mm holes for MX switches
- **Bottom shell** — holds PCB with M3 heatset inserts
- **USB cutout** — on the top edge for XIAO USB-C port
- **OLED window** — cutout on top face for display

---

## Build Guide

1. Solder heatset inserts into the bottom case
2. Solder diodes onto the PCB (bottom layer, cathode toward column)
3. Solder SK6812 MINI-E LEDs onto the PCB (bottom layer)
4. Solder XIAO RP2040 onto the PCB
5. Solder switches into the PCB from the top
6. Connect OLED display to J1 connector
7. Flash firmware
8. Screw PCB into case

---

## License

MIT License — do whatever you want with it!

---

*Built as part of Hack Club's hardware grant program.*
