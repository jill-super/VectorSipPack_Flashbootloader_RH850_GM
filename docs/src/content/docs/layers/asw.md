---
title: Application Software (ASW)
description: Demo application layer
---

Demo applications that run above (or beside) the bootloader: download
containers, GM headers, jump-to-FBL logic.

- Canonical page: [Demo applications](../modules/asw/demo/)
- Folders: `Demo/DemoAppl/Appl` (incl. `ApplHdr_without_cal`,
  `ApplHdr_2Part_3cal`, `ApplHdr_3Part_each_1Cal`), `Demo/DemoUpdater/Appl`
- Key files: `Appl/Source/fbl_ap*.c`, `fbl_jmp_to_fbl.c`, `startup.c`,
  `Gen_All.bat`, `ModGenBase*.xml`, `SignerInfoDummyKey.hex`
- Converted reading: [GM containers](../modules/bsw-services/fbl/technical-reference-fbl-gm-containers/)

[Back to top](#top)
