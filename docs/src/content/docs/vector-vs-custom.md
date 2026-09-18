---
title: Vector vs. custom vs. third-party
description: Origin policy for every file in the delivery
sidebar:
  order: 4
---

<span class="origin-vector">Vector-provided</span>
Copyright `Vector Informatik GmbH`. Covers `BSW/Fbl`, `BSW/SecMod` (except
`act*`), `BSW/WrapNv`, `BSW/Cmpr_Lzma` wrapper, `BSW/Flash/flashdrv.*`,
`BSW/FblUpd`, transceiver/SPI wrappers, `BSW/FblAsrStubs`, `BSW/_Common`,
`Demo/*` templates, `Generators/*`, `Doc/*`, `Misc/HexView`, PES makesupport.
Licensed under Vector conditions (see delivery addendum conversion:
[license addendum](./general/delivery/license-addendum-cbd1500635/)).

<span class="origin-custom">Custom / integration-owned</span>
Handwritten integration derived from `_Template` sources
(`Demo/*/Appl/Source/fbl_ap*.c`, `upd_ap*.c`, `WrapNv_Cfg.c`,
`*_cfg.c`, `startup.c`, `comdat.c`), GM container scripts
(`Gen_All.bat`, `ModGenBase*.xml`), `Misc/Config`, demo keys usage.
These plus `docs/`, `README.md`, `.github/` are MIT (see `LICENSE`).

<span class="origin-thirdparty">Third-party</span>
`BSW/Flash/FlashLib/*` — Renesas FCL (`r_fcl*`, disclaimer: Renesas
products only, "AS IS"). `BSW/SecMod/act*` — cryptovision actCLibrary.
`MakeSupport/cmd/*` — GNU/Cygwin (`GPL*`, `GNU_LGPL_v3.0.html`).
`BSW/Cmpr_Lzma/COMPRESS_*` decode core builds on LZMA SDK concepts.
`Misc/HexView/license.liz` governs HexView binaries.

**Rule:** the header inside each file wins. `GenData` outputs
(`v_cfg.h`, `fbl_cfg.h`, `fbl_mtab.*`, …) are Vector-generated for serial
`CBD1500635` — regenerate with GENy/DaVinci, don't hand-edit. `LICENSE` at
the repo root is MIT for the documentation/integration layer and explicitly
defers to the above proprietary headers.

[Back to top](#top)
