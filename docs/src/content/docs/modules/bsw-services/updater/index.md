---
title: Bootloader updater (FblUpd)
description: In-field updater for the bootloader itself
---

<span class="origin-vector">Vector-provided</span> · `BSW/FblUpd/` (+ `_Template/`)

## Purpose

Updates the resident bootloader to a new version (GM-specific flow in
`TechnicalReference_FBL_Updater_GM`). Small core (`upd_main.c|h`,
`upd_types.h`) plus per-project `_upd_ap*`, `_upd_hw_*`, `_upd_oem_*`,
`_upd_cfg.h` templates copied into `Demo/DemoUpdater/Appl/Source`
(`upd_ap.c`, `upd_hw_ap.c`, `upd_oem_ap.c`, `DemoFbl.c`).

## Public API (selection)

```c
/* upd_types.h */
typedef tFblResult (*tFblUpdFunc)(void);
/* upd_main.h — diag/memory hooks used by the updater build */
void FblDiagRxIndication(...);  void FblDiagTxConfirmation(...);
tFblMemSegmentNr FblMemSegmentNrGet(...);
```

## Usage

Build `DemoUpdater` with the Makesupport flow, stage the updater image per
the updater TRs, trigger via diagnostics; the updater rewrites the FBL area
and hands back. Helpers: `Misc/FblUpd/FblUpd_Prepare.bat`.

## Converted documentation

- [TR FBL updater](./technical-reference-fbl-updater/)
- [TR GM updater specifics](./technical-reference-fbl-updater-gm/)

[Back to top](#top)
