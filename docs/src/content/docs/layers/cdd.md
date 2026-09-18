---
title: Complex Device Drivers (CDD)
description: Bootloader-specific drivers outside standard BSW
---

The bootloader core behaves as a CDD: direct CAN/flash/NV access with its own
diagnostics and memory lib, bypassing a full AUTOSAR stack.

- Canonical pages: [FBL core](../modules/bsw-services/fbl/),
  [Updater](../modules/bsw-services/updater/)
- Folders: `BSW/Fbl` (`fbl_main`, `fbl_diag*`, `fbl_mem*`, `fbl_cw`, `fbl_tp`,
  `fbl_hw`, `fbl_flio`, `fbl_hdr`, `fbl_wd`), `BSW/FblUpd` (`upd_main`)
- Converted reading: [FBL GM SLP6](../modules/bsw-services/fbl/technical-reference-fbl-gm-slp6/)

[Back to top](#top)
