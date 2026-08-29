# Dactyl CC ZMK

ZMK configuration for a 52-key wireless Dactyl CC using two nice!nano v2
controllers. Each half has four rows of six keys and two thumb keys. The left
half is the split central (master).

## OLED

The left half has one vertically mounted 128x32 SSD1306 I2C OLED. It displays
the battery percentages in left-then-right order and the active layer (`BASE`
or `FN`). The right firmware does not enable a display.

Wire the OLED to the left nice!nano v2 as follows:

| OLED | nice!nano v2 |
| --- | --- |
| GND | GND |
| VCC | VCC (3.3 V) |
| SDA | D2 |
| SCL | D3 |

The configured I2C address is `0x3C`.

## Matrix

The new matrix reuses the first five existing row connections and all six
existing column connections. The old sixth row connection (`P1.06`) is no
longer used. The thumb switches occupy row 4, columns 4 and 5 on each half.

Builds are generated for `dactyl_cc_left`, `dactyl_cc_right`, and
`settings_reset`. Flash both halves after changing the matrix definition or
split battery configuration.
