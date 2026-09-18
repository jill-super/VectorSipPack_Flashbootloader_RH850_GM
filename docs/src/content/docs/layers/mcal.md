---
title: MCAL
description: Microcontroller abstraction — flash and SPI hardware access
---

- [Flash driver + Renesas FCL](../modules/mcal/flash/) — `flashdrv.*`,
  `FlashRom.*`, `FlashLib/r_fcl*`, `BSW/Flash/Build/Makefile*`
- SPI CSIH backend shares its page with ECU abstraction:
  [SPI](../modules/ecu-abstraction/spi/)
- Converted reading: [FBL RH850 TR](../modules/mcal/flash/technical-reference-fbl-rh850/),
  [AN-ISC-8-1188](../general/app-notes/an-isc-8-1188-custom-flash-drivers/)

[Back to top](#top)
