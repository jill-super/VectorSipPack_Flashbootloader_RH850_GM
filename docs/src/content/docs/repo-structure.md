---
title: Repository structure
description: Annotated tree of the delivery
sidebar:
  order: 2
---

```text
BSW/                  # bootloader + BSW modules (mostly Vector-provided)
  Fbl/                # FBL core: diag, memory, CAN wrapper, HW, watchdog
  FblUpd/             # bootloader updater
  SecMod/             # HIS security module + cryptovision actCLibrary
  WrapNv/             # NV-memory wrapper (FEE / no-NV use cases)
  Cmpr_Lzma/          # LZMA decompression wrapper
  Flash/              # flashdrv wrapper + Renesas FCL (FlashLib) + Build/
  FblCanTrcv_Tja1145/ # TJA1145 CAN-transceiver driver
  FblSpi_RenesasCsih/ # CSIH SPI driver (Renesas RH850)
  FblSpi_VectorIf/    # SPI abstraction interface
  FblAsrStubs/        # AUTOSAR BSW stubs (Dem/Det/EcuM/Os/…)
  _Common/            # v_def.h common types
  <each>/_Template/   # integration templates (_fbl_ap*, _upd_*, _dummySba…)

Demo/                 # integration examples (Vector templates, customised per ECU)
  DemoFbl/            # bootloader demo app (Source + GenData + Config)
  DemoAppl/           # application demo incl. ApplHdr_* GM containers
  DemoUpdater/        # updater demo
  Demo_Fee/           # FEE share demo (ECUC/AUTOSAR/ServiceComponents)
  Demo_Tja1145/       # transceiver demo config

Doc/                  # SIP documentation (all converted under General/Modules)
  TechnicalReferences/ 9× TR PDFs
  ApplicationNotes/    2× AN PDFs
  UserManuals/         1× user manual PDF
  DeliveryInformation/ readme/test/issue PDFs + HTML + XML + license addendum

Generators/Components # GENy/DaVinci plugins (*.dll/*.pco/*.pcu) + _Schemes/*.arxml
MakeSupport/          # Vector PES Makesupport 3.13 + GNU/Cygwin cmd tools
Misc/                 # HexView, HdrGen, Cmpr_Lzma tools, DemoKey_2048, Config
FlashTool/            # vFlash template installer + seedkey.zip
docs/                 # THIS site (Astro Starlight project)
.github/              # Pages deploy + validation + Dependabot
```

`GenData` folders (`Demo/*/Appl/GenData`, `gendata`) are DaVinci/GENy outputs
(serial `CBD1500635`, tool `06.04.03.01.50.06.35.03.00.00`) — treat as
*Vector-provided, customised* (regenerate, don't hand-edit).
`_Template` folders are the copy-sources for `fbl_ap*`/`upd_*` integration.

[Back to top](#top)
