# MK1 Xiao ESP32-C6

This fork adapts the MK1 firmware for the Seeed Studio XIAO ESP32-C6.

Open `Mk1_C6_a0a3/Mk1_C6_a0a3.ino` in Arduino IDE. The sketch folder also
contains `prefs_keys.h` and `web_pages.h`; keep all three files together.

## Pin assignments

| Hardware | D pin | GPIO |
|---|---:|---:|
| Outer RGB ring, 64 LEDs | D10 | 18 |
| Inner RGBW ring and core | D8 | 19 |
| Button | D0 | 0 |
| Battery sense | D2 | 2 |

The existing three-zone layout is retained: 64 outer LEDs, 8 inner LEDs, and 1 core LED. The total LED index count is 73.

The outer ring uses WS2812-compatible output in GRB order. The inner ring and
sequentially last center LED use SK6812 RGBW LEDs in GRBW order on D8/GPIO19.
The FastLED RGBW conversion targets the 6500K dedicated white channel.
