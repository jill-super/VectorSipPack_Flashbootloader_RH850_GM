---
title: CAN transceiver TJA1145
description: FBL driver for the NXP TJA1145 CAN transceiver over SPI
---

<span class="origin-vector">Vector-provided</span> · `BSW/FblCanTrcv_Tja1145/`

## Purpose

Puts the TJA1145 into normal/sleep modes around flashing and diagnostics,
using the SPI interface above. GM/SLP6 low-power behaviour included.

## Key files

`fbl_can_trcv_tja1145.c|h`, `fbl_can_trcv_tja1145_inc.h`, `_Spi.h` (SPI
binding), `_fbl_can_trcv_tja1145_cfg.c|h` template; integration
`Demo/*/Appl/Source/fbl_can_trcv_tja1145_cfg.c`,
`Include/fbl_can_trcv_tja1145_cfg.h`; demo config `Demo/Demo_Tja1145`.

## Public API

```c
void FblCanTrcvTja1145Init(void);
void FblCanTrcvTja1145NormalMode(void);
void FblCanTrcvTja1145SleepMode(void);
void FblCanTrcvTja1145Deinit(void);
```

Call `Init` during `FblHw` init, `NormalMode` before diagnostics/flashing,
`SleepMode` on bus sleep.

## Dependencies

SPI (`FblSpi_VectorIf` + CSIH backend), CAN hardware init.

[Back to top](#top)
