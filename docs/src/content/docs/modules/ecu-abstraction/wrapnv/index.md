---
title: NV wrapper (WrapNv)
description: NV-memory abstraction over FEE or no-NV configurations
---

<span class="origin-vector">Vector-provided</span> · `BSW/WrapNv/`

## Purpose

Uniform sync/async NV access for the bootloader regardless of whether FEE/NvM
is present (`WRAPNV_USECASE_FEE` vs no-NV). Backs identities/sequence state
(NBID), FBL-NV blocks and FEE sharing with the application.

## Key files

`WrapNv.c|h`, `_WrapNv_Cfg.c|h`, `_WrapNv_inc.h`; integration copies
`Demo/*/Appl/Source/WrapNv_Cfg.c`, `Include/WrapNv_Cfg.h|WrapNv_inc.h`;
generator scheme `Generators/Components/_Schemes/WrapNv/bswmd/*.arxml`
(`SysService_WrapperNv_*`).

## Public API

```c
FUNC(WrapNv_ReturnType, WRAPNV_CODE) WrapNv_ReadSync(uint16 id, uint16 idx, tWrapNvRamData buffer);
FUNC(WrapNv_ReturnType, WRAPNV_CODE) WrapNv_ReadPartialSync(uint16 id, uint16 idx, tWrapNvRamData buffer, uint16 offset, uint16 len);
FUNC(WrapNv_ReturnType, WRAPNV_CODE) WrapNv_WriteSync(uint16 id, uint16 idx, tWrapNvConstData buffer);
FUNC(WrapNv_ReturnType, WRAPNV_CODE) WrapNv_DeleteSync(uint16 id, uint16 idx);
FUNC(WrapNv_ReturnType, WRAPNV_CODE) WrapNv_ReadAsync(... , tWrapNvOpStatus opStatus);
FUNC(WrapNv_ReturnType, WRAPNV_CODE) WrapNv_WriteAsync(...);
FUNC(WrapNv_ReturnType, WRAPNV_CODE) WrapNv_DeleteAsync(...);
```

## Usage

```c
if (WrapNv_ReadSync(blockId, idx, buf) != WRAPNV_E_OK) { /* handle */ }
WrapNv_WriteAsync(blockId, idx, data, &status);
```

For app/bootloader FEE sharing see
[AN-ISC-8-1173](../../../general/app-notes/an-isc-8-1173-share-fee-blocks/)
and `Demo/Demo_Fee` configs.

## Dependencies

FEE/NvM (+ `FblAsrStubs` SchM) in FEE use-case; none in no-NV use-case.

## Converted documentation

- [TR NV wrapper](./technical-reference-nvwrapper/)

[Back to top](#top)
