---
title: AUTOSAR layers
description: How the repository maps to AUTOSAR software layers
sidebar:
  order: 3
---

| Layer | Directories | Role in this delivery |
|---|---|---|
| Application Software (ASW) | `Demo/DemoAppl`, `Demo/DemoUpdater/Appl` | Demo app + updater app, GM header containers (`ApplHdr_*`) |
| Complex Device Drivers (CDD) | `BSW/Fbl` (core), `BSW/FblUpd` | Bootloader behaviour that bypasses standard BSW stacks |
| BSW Services | `BSW/Fbl` (diag/mem), `BSW/SecMod`, `BSW/Cmpr_Lzma`, `BSW/FblUpd` | UDS diagnostics, verification, decompression, update |
| ECU Abstraction | `BSW/WrapNv`, `BSW/FblCanTrcv_Tja1145`, `BSW/FblSpi_VectorIf` | NV-wrapper, transceiver, SPI interface |
| MCAL | `BSW/Flash/FlashLib`, `BSW/FblSpi_RenesasCsih`, `BSW/Fbl/*hw*`, `BSW/Flash/flashdrv` | Renesas FCL, CSIH driver, CAN/RSCAN glue |
| Integration / generated | `Demo/*/Appl/GenData`, `Demo/*/Config`, `BSW/*/_Template`, `BSW/FblAsrStubs`, `BSW/_Common` | GENy outputs, copy-templates, AUTOSAR stubs |
| Tools & config | `Generators`, `MakeSupport`, `Misc`, `FlashTool` | GENy plugins, PES Makesupport+GHS, HexView/HdrGen, vFlash |

Layer detail pages: [ASW](./layers/asw/) · [CDD](./layers/cdd/) ·
[BSW Services](./layers/bsw-services/) · [ECU Abstraction](./layers/ecu-abstraction/) ·
[MCAL](./layers/mcal/) · [Integration](./layers/integration/) · [Tools](./layers/tools/).

The [module index](./modules/) follows the same layer grouping:
`modules/<layer>/<module>/`.

[Back to top](#top)
