# Pro Micro ADB "Shield"

<img alt="3D render of PCB" src=pro-micro-adb-shield-crop.png width=500px>

A simple PCB designed to add an Apple Desktop Bus (ADB) port to an Arduino
Pro Micro board to create a USB-ADB converter with a few extra features.
Uses mostly through-hole components.

Software is based on TMK's existing USB-ADB converter, see the
[firmware repo][fwrepo] for more details.

## Features
- DIP switch for on-the-fly modification of keymaps
- LEDs for Caps and Num Lock status
- Uses through hole components for ease of assembly (+ aesthetics, really)
- Based on a Pro Micro to avoid reinventing the atmega32 wheel, and to give
  some modicum of insurance against chip shortage insanity

## BOM / Assembly

Parts List:

| Ref.   | Description / Value                                                           |
| ------ | ----------------------------------------------------------------------------- |
| U1     | Arduino Pro Micro (5V)                                                        |
| J1     | 4 pin DIN socket, Kycon `KMDGX-4S-BS` or compatible                           |
| SW1    | Through-hole mini pushbutton, TE Connectivity `1825910-7` or compatible       |
| SW2    | 4 position surface mount DIP switch, CTS Electronics `214-LPST` or compatible |
| R1, R2 | 1/4 W through hole resistor, value dependent on LED                           |
| R3     | 1/4 W through hole resistor, 1-4.7K (pullup for ADB, see [here][tmkwiki])     |
| D1, D2 | 3mm through-hole LEDs                                                         |

[tmkwiki]: https://github.com/tmk/tmk_keyboard/wiki/Apple-Desktop-Bus#pull-up-resistor


Steps:

1. Solder SMD DIP switch to shield
2. Solder all through hole parts to shield, trim legs
3. Short jumper on Pro Micro to set 5V logic levels
4. Solder headers to Pro Micro
5. Test LEDs, etc -- you won't be able to remove them later!
6. Stack boards together and solder headers to shield
7. Trim excess header length from shield side
8. Flash Pro Micro with [firmware][fwrepo]; optionally customize keymaps

[fwrepo]: https://github.com/cnorthway/tmk_keyboard/tree/cnorthway/adapter
