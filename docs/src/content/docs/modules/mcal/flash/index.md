---
title: Flash driver + Renesas FCL
description: FBL flash wrapper and RV40 code-flash access library
---

<span class="origin-vector">Vector-provided</span> wrapper + <span class="origin-thirdparty">Renesas FCL</span> · `BSW/Flash/`

## Purpose

`flashdrv.c|h` + `FlashRom.c|h` adapt the bootloader memory path to the
device; `FlashLib/r_fcl*` is Renesas' Code Flash Access Library for RV40
RH850; `Build/` holds the GHS/PES makefiles and `MkFlashRom.bat` that turns
a `.hex` driver into the `FlashRom.c` C-array.

## Key files

`flashdrv.c|h` (HIS interface: `tFlashParam`, `tFlashFct`, `wdTriggerFct`),
`FlashRom.c|h` (generated array), `FlashLib/r_fcl.h|_types|_env|_global`,
`r_fcl_user_if.c`, `r_fcl_hw_access.c|_asm.850`, `fcl_cfg.h`, `r_typedefs.h`,
`Build/Makefile*`, `MkFlashRom.bat`, `b.bat`, `m.bat`, `FlashDrv.hex`
(example output).

## Public API (HIS-style, via structs)

```c
typedef tFlashUint8 (*wdTriggerFct)(void);
typedef void (*tFlashFct)(tFlashParam *flashParam);
/* FBL-side sync wrappers: */
FlashDriver_RWriteSync / FlashDriver_REraseSync /
FlashDriver_RReadSync / FlashDriver_DeinitSync (fbl_flio.h)
```

Custom-driver integrators: implement the HIS polling function and respect
pipelined programming/verification — see
[AN-ISC-8-1188](../../../general/app-notes/an-isc-8-1188-custom-flash-drivers/).

## Dependencies

Called from `fbl_mem`/`fbl_flio`; needs correct derivative memory map
(`Makefile.derivative.memorymap`) and linker script.

## Converted documentation

- [TR FBL RH850](./technical-reference-fbl-rh850/)

[Back to top](#top)
