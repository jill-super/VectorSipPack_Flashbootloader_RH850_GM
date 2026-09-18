---
title: Demo applications
description: DemoFbl, DemoAppl, DemoUpdater, Demo_Fee, Demo_Tja1145
---

<span class="origin-vector">Vector-provided</span> customised · `Demo/`

## Purpose

Copy-and-adapt integration baselines. Each `Appl` pairs handwritten
`Source` (OEM hooks) with `GenData` (GENy) and `Config` (DaVinci inputs):

- `DemoFbl/Appl` — bootloader demo (`fbl_ap*.c`, `fbl_apnv*.c`,
  `comdat.c`, `startup.c`, `WrapNv_Cfg.c`, `_dummySba.c`).
- `DemoAppl/Appl` — application demo + GM containers
  (`ApplHdr_without_cal`, `ApplHdr_2Part_3cal`, `ApplHdr_3Part_each_1Cal`,
  each with `Gen_All.bat`, `ModGenBase*.xml`, `*_plain.*` to-send-to-GM vs
  `*_sign.*` demo containers, `fbl_jmp_to_fbl.c`).
- `DemoUpdater/Appl` — updater demo (`upd_ap*.c`, `DemoFbl.c`).
- `Demo_Fee` — FEE-share configs (`ECUC`, `AUTOSAR`, `ServiceComponents`).
- `Demo_Tja1145` — transceiver configs.

## Key integration files

`fbl_ap.c` (application callbacks), `fbl_apdi.c` (diagnostics),
`fbl_apnv*.c` incl. `fbl_apnv_fee.c` / `fbl_apnv-nofee.c` (NV),
`fbl_apwd.c` (watchdog), `comdat.c`, `applvect.c`, `startup.c`,
`WrapNv_Cfg.c`, `*_cfg.c` (CAN/SPI/transceiver).

Start from `DemoFbl`, diff against `DemoAppl` for app-side extras, and read
[GM containers](../../bsw-services/fbl/technical-reference-fbl-gm-containers/)
before signing flows.

[Back to top](#top)
