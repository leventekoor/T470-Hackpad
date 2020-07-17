# T470-Hackpad
***Tested on:*** *macOS Catalina 10.15.x*\
***Apple Services:*** *tested and working*

![macOS Catalina on the ThinkPad T470](/catalina-t470.png)

## Introduction
This was my first hackintosh project, with a lot of learning and even more unexpected errors. I have yet to find a completed T470 setup for Catalina using OpenCore, so I decided to make one for myself and share with the community. So here we are... :) As I said being a first time hackintosher I ran into a lot of problems and did a LOT of research to get my system even to boot, then slowly worked myself towards a stable system. I hope this helps anyone who has a similar T470 setup or have a shared specific hardware that they hav problems with. I try to update this repo to the best of my ability.

## Tips & Notes
- Battery life is about the same as on Windows
- Never experienced any KPs while using Catalina
- Always keep a copy of your original dissassembled DSDT. (**Only edit DSDT using MaciASL**)
  - It is adviced to keep a copy after each change so you don't have to restart from the beginning if you messed something up.

## Hardware
#### Thinkpad T470
- Model: 20HES1SA00
- BIOS N1QET88W (1.63)
  - Settings:
    - Start from default settings
    - Config > USB > Always on USB: Disabled
    - Config > Thunderbolt 3 > All options: Disabled (No Security)
    - Security > Security Chip: Disabled (TPM2.0)
    - Security > I/O Port Access: WWAN, Fingerprint, TB3, WiGig: Disabled
    - Security > Secure Boot > Secure Boot: disabled
    - Startup > Boot Mode: UEFI Only
    - Startup > CSM Support: Disabled

| Device                                      | Status                 |
|---------------------------------------------|------------------------|
| Intel Core i5-7300U @ 2.6GHz / 3.4Ghz Turbo | Working and Tested     |
| Intel HD 620 Graphics                       | Working and Tested     |
| 1920x1080 IPS Panel (Matte)                 | Working and Tested     |
| 16GB DDR4 2133Mhz (Samsung & SK Hynix)      | Working and Tested     |
| Dual 3-cell batteries                       | Working and Tested     |
| USB - XHC 100-series chipset                | Working*               |
| Realtek ALC298                              | Working and Tested     |
| Integrated Camera (IMC Networks)            | Working and Tested     |
| Intel I219-LM Network Adapter               | Working and Tested     |
| Touchpad (Synaptics)                        | Working and Tested     |
| Trackpoint                                  | Working, needs testing |
| LCD backlight                               | Working and Tested     |
| Power button                                | Working and Tested     |
| Power management                            | Working and Tested     |
| Sleep/Wake                                  | Not Working*           |
| Thinkpad/Power button LED (sleep mode)      | Working and Tested     |
| Realtek USB 3.0 Card Reader                 | Not yet tested         |
| Headphone jack                              | Working and Tested     |
| WWAN                                        | Not Working**          |
| Function keys (except vol control)          | Not Working            |

_\*Still in progress of patching_\
_\*\*Planning on buying a compatible WWAN Card_

## Tools Used
- USB Flash Drive with OpenCore and MacOS Installer
- [gibMacOS](https://github.com/corpnewt/gibMacOS)
- [ProperTree](https://github.com/corpnewt/ProperTree)
- [iasl-win](https://www.acpica.org/downloads/binary-tools)
- [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
- [MaciASL](https://bitbucket.org/RehabMan/os-x-maciasl-patchmatic/downloads/)

## Kexts Used
- ACPIBatteryManager
- AppleALC
- AppleBacklightFixup
- CPUFriend
- IntelMausiEthernet
- Lilu
- USBInjectAll
- VirtualSMC
  - SMCLightSensor
  - SMCProcessor
  - SMCSuperIO
- VoodooPS2Controller
- WhateverGreen

_For versions see [KEXTVersions.md](/KEXTVersions.md)_

#### Important Notice
SystemUUID, SystemSerialNumber and MLB are cleared in the config file 

## Thanks
- [OpenCore Vanilla Laptop Guide](https://dortania.github.io/vanilla-laptop-guide/) - I started off with this guide and worked my way through this, very helpful for beginners
- [RehabMan](https://github.com/RehabMan) - Lot of kexts and DSDT, SSDT patches are his work, big thanks
- [digitaltec](https://github.com/digitalec/) - I managed to get my battery working from his T470 repo
