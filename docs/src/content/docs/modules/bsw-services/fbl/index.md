---
title: FBL core (GM SLP6)
description: Bootloader core — diagnostics, memory, CAN wrapper, hardware
---

<span class="origin-vector">Vector-provided</span> `BSW/Fbl/` (+ `BSW/Fbl/_Template/`)

## Purpose

GM SLP6 bootloader core for RH850: UDS (ISO 14229) diagnostics over CAN,
download/erase/verify programming flow, GM header/container handling, CAN
transport (`fbl_tp`), communication wrapper (`fbl_cw`), memory abstraction
(`fbl_mem`, `fbl_mio`, `fbl_flio`), hardware init (`fbl_hw`, `fbl_vect`,
`applvect`), watchdog (`fbl_wd`) and version map (`v_ver.h`, SIP `06.04.03`).

## Key files

`fbl_main.c|h` (entry `FblStart`), `fbl_diag_core.c|h`, `fbl_diag_oem.c|h`,
`fbl_diag.h`, `fbl_mem.c|h`, `fbl_mem_oem.h`, `fbl_cw.c|h`, `fbl_tp.c|h`,
`fbl_hw.c|h`, `fbl_flio.c|h`, `fbl_hdr.c|h`, `fbl_mio.c|h`, `fbl_nbid.c|h`,
`fbl_wd.c|h`, `fbl_vect.c`, `applvect.h`, `fbl_def.h`, `fbl_sfr.h`,
`iotypes.h`, `v_ver.h`. Templates: `_Template/_fbl_ap*.c|h`, `_comdats.*`,
`_dummySba.*`, `_appParseSba.*`, `_MemMap.h`.

## Public API (selection, from headers)

```c
/* lifecycle */
void FblStart(void);
tFblMemRamData FblMemInit(void);
void FblMemDeinit(void);
/* communication wrapper */
void FblCwInit(void);  void FblCwDeinit(void);
void FblCwIdleTask(void);
vuint8 FblCwPrecopy(...);  void FblCwTransmit(...);
/* transport */
void FblTpTask(void);  void FblTpTransmit(...);  void FblTpConfirmation(...);
/* memory */
tFblMemStatus FblMemBlockStartIndication(...);
tFblMemStatus FblMemBlockEndIndication(void);
tFblMemStatus FblMemBlockVerify(...);
tFblMemStatus FblMemEraseRegion(...);
/* diagnostics */
void FblDiagInit(void);  void FblDiagRxIndication(...);  void FblDiagTxConfirmation(...);
vuint8 FblDiagCheckTesterSourceAddr(...);  void SetSecurityUnlock(...);
/* flash IO */
FlashDriver_RWriteSync / _REraseSync / _RReadSync / _DeinitSync (see fbl_flio.h)
/* watchdog */
void FblInitWatchdog(void);  void FblLookForWatchdog(void);
```

## Usage

1. Copy `_Template/_fbl_ap*.c|h` (+ `_fbl_inc.h`, `_MemMap.h`) into the demo
   `Appl/Source|Include`, implement OEM hooks (`fbl_apdi`, `fbl_apnv`,
   `fbl_apwd`), configure `GenData/fbl_cfg.h`, `fbl_mtab.c`, `v_cfg.h`.
2. Build with GHS `2015.1.7` via PES Makesupport; entry is `FblStart`.
3. Program GM containers (`ApplHdr_*`) and run UDS download.

## Dependencies

`SecMod` (verification), `WrapNv` (NV), `Cmpr_Lzma` (decompression),
`Flash/flashdrv` + FCL, SPI/transceiver drivers, `FblAsrStubs`, `_Common`,
generated `GenData`.

## Converted documentation

- [TR FBL GM SLP6](./technical-reference-fbl-gm-slp6/)
- [TR GM containers](./technical-reference-fbl-gm-containers/)
- [TR GM compression interface](./technical-reference-fbl-gm-cmpr/)
- [Template notes](../../../general/txt-docs/dummysba-readme/),
  [appParseSba](../../../general/txt-docs/appparsesba-readme/)

[Back to top](#top)
