---
title: Common types + generated data
description: v_def/v_cfg/v_par and GENy outputs
---

<span class="origin-vector">Vector-provided</span> customised ·
`BSW/_Common/`, `Demo/*/Appl/GenData`, `Demo/*/Config`

## Purpose

- `BSW/_Common/v_def.h` — Vector common type definitions (platform-specific;
  never mix across derivatives).
- `GenData` (`v_cfg.h`, `v_inc.h`, `v_par.c|h`, `fbl_cfg.h`, `fbl_mtab.c|h`,
  `fbl_cw_cfg.*`, `fbl_apfb.*`, `ftp_cfg.h`, `SecMPar.*`, `SecM_cfg.h`) —
  GENy output for serial `CBD1500635` (tool `06.04.03.01.50.06.35.03.00.00`,
  ECU `Hw_Rh850Cpu`/GHS/P1M). Regenerate on config change.
- `Config` (`Demo_Fee`, `Demo_Tja1145`: `ECUC`, `InternalBehavior`,
  `AUTOSAR`, `ServiceComponents`, `McData`) — DaVinci inputs.

[Back to top](#top)
