---
title: AUTOSAR stubs (FblAsrStubs)
description: Minimal Dem/Det/EcuM/Os/Rte/SchM shims for the bootloader
---

<span class="origin-vector">Vector-provided</span> customised · `BSW/FblAsrStubs/`

## Purpose

Lets bootloader code compile/run without a full AUTOSAR stack by stubbing
`Dem_ReportErrorStatus`, `GetCounterValue` (Os), EcuM/Rte/SchM and
`MemIf`/`CanIf` types. `SchM_Fls.h` shows the data-protection hooks used by
the flash path.

Files: `Std_Types.h`, `CanIf.h`, `Can_GeneralTypes.h`, `ComStack_Cfg.h`,
`Dem.c|h`, `Det.c|h`, `EcuM.c|h`, `EcuM_Cbk.h`, `MemIf_Types.h`, `Os.h`,
`Rte.h`, `Rte_Type.h`, `SchM_CanIf.h`, `SchM_CanTrcv_30_Tja1145.h`,
`SchM_Fee.h`, `SchM_Fls.h`, `SchM_PduR.h`.

Adapt these stubs when wiring real BSW (notably Fee/Fls SchM guards and
`Det`/`Dem` reporting).

[Back to top](#top)
