---
title: LZMA compression (Cmpr_Lzma)
description: Decompression service for compressed download segments
---

<span class="origin-vector">Vector-provided</span> · `BSW/Cmpr_Lzma/`

## Purpose

Decompresses LZMA segments during download (`FBL_ENABLE_COMPRESSION_MODE`).
Thin Vector wrapper (`cmpr_lzma.*`, `_cmpr_lzma_cfg.h`) over the
`COMPRESS_LZMA_DECODE*` core.

## Key files

`cmpr_lzma.c|h`, `_cmpr_lzma_cfg.h`, `COMPRESS_LZMA.h`,
`COMPRESS_LZMA_DECODE*.h`, `COMPRESS_LZMA_Decode.c`,
`COMPRESS_LZMA_Int.h`. Host tools: `Misc/Cmpr_Lzma/COMPRESS_LZMA_ENCODE.dll`,
`COMPRESS_LZMA_Util.exe`. Demo config: `Demo/*/Appl/Include/cmpr_lzma_cfg.h`.

## Public API

```c
tFblResult CmprLzmaDeinit(tProcParam *procParam);
tFblResult CmprLzmaDecompress(tProcParam *procParam);
```

Wire `procParam` (input/output buffers, watchdog hook) and call
`CmprLzmaDecompress` per segment; `FblMem` routes compressed blocks here
when compression is enabled.

## Dependencies

FBL memory path; GM compression interface TR below.

## Converted documentation

- [TR CmprLzma](./technical-reference-cmprlzma/)
- [TR GM compression interface](../fbl/technical-reference-fbl-gm-cmpr/)

[Back to top](#top)
