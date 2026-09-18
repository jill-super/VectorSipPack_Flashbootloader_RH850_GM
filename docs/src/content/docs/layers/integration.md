---
title: Integration and generated code
description: GenData, templates, stubs, common headers
---

- [AUTOSAR stubs](../modules/integration/asr-stubs/) — `Dem`, `Det`, `EcuM`,
  `Os`, `Rte`, `SchM_*`, `Std_Types`
- [Common + generated](../modules/integration/common-gendata/) —
  `v_def.h`, `v_cfg.h`, `fbl_cfg.h`, `fbl_mtab.*`, `_Template` copy-sources
- Rule: regenerate `GenData` with GENy/DaVinci (serial `CBD1500635`); copy
  `_Template/_fbl_*` and `_upd_*` into `Demo/*/Appl/Source|Include` and adapt.

[Back to top](#top)
