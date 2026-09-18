---
title: Getting started
description: Build prerequisites, build steps, and first programming flow
sidebar:
  order: 1
---

## Prerequisites

- **Hardware:** Renesas RH850 P1M (e.g. `R7F701363`, RV40 flash).
- **Compiler:** Green Hills `2015.1.7` (version recorded in `BSW/Fbl/v_ver.h`
  and `Demo/*/Appl/GenData/v_cfg.h`).
- **Host tools:** GNU Make via `MakeSupport/cmd/make.exe` + Cygwin DLLs
  (`cygwin1.dll`), `HexView` (`Misc/HexView/hexview.exe`), GENy/DaVinci
  generator plugins (`Generators/Components/*.dll`), `vFlashTemplateInstaller`
  (`FlashTool/`).
- **Docs site (optional):** Node.js `>= 20` and npm for `docs/` (Astro Starlight).

## Build the flash driver

```bat
cd BSW\Flash\Build
MkFlashRom.bat <your-driver.hex>
```

What happens: `MkFlashRom.bat` writes a `FlashRom.ini`, then calls
`Misc\HexView\hexview.exe … -o ..\FlashRom.c` to emit a C-array flash driver
(`BSW/Flash/FlashRom.c|.h`). The GHS makefiles in the same folder
(`Makefile`, `Makefile.config`, `Makefile.derivative.*`,
`Makefile.RH850.GHS.*`) build the standalone flash-driver image
(`FlashDrv.hex` is a checked-in example output).

## Build the demos

Each of `Demo/DemoAppl`, `Demo/DemoFbl`, `Demo/DemoUpdater` ships its own
`Appl/Makefile*` set plus `b.bat`/`m.bat` wrappers around the same Vector
PES Makesupport (`3.13`) flow. Typical flow:

```bat
cd Demo\DemoFbl\Appl
m.bat
```

Generated configuration lives in `Appl/GenData` (`fbl_cfg.h`, `fbl_mtab.c`,
`v_cfg.h`, …) and handwritten integration in `Appl/Source`
(`fbl_ap.c`, `fbl_apdi.c`, `fbl_apnv*.c`, `fbl_apwd.c`, `startup.c`, …).

## Program and verify

1. Flash the bootloader + `ApplHdr_*` containers (see
   [GM containers](./modules/bsw-services/fbl/technical-reference-fbl-gm-containers/)
   and `Demo/DemoAppl/Appl/ApplHdr_*/Gen_All.bat`).
2. Run UDS download over CAN (see
   [FBL GM SLP6](./modules/bsw-services/fbl/technical-reference-fbl-gm-slp6/)).
3. Check `Doc/DeliveryInformation/TestReport_CBD1500635.pdf` conversion under
   [Delivery](./general/delivery/test-report-cbd1500635/) for the integration
   test baseline.

## Docs site locally

```sh
cd docs
npm ci
npm run dev     # preview
npm run build   # static output in docs/dist
```

[Back to top](#top)
