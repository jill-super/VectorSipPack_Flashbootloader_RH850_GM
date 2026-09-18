---
title: SPI (VectorIf + Renesas CSIH)
description: SPI abstraction and RH850 CSIH backend
---

<span class="origin-vector">Vector-provided</span> · `BSW/FblSpi_VectorIf/`, `BSW/FblSpi_RenesasCsih/`

## Purpose

`fbl_spi_if.h` defines the bootloader SPI interface (handles, transfer
params, sync/async ops, polling/watchdog hook); `fbl_spi_renesas_csih.*`
implements it on RH850 CSIH (`g_FblSpiRenesasCsih`). Used by the TJA1145
transceiver path (`_Spi.h`) and any SPI-attached peripheral.

## Key files

`FblSpi_VectorIf/fbl_spi_if.h`, `_Template/_fbl_spi_if_cfg.h`;
`FblSpi_RenesasCsih/fbl_spi_renesas_csih.c|h|_inc.h`,
`_Template/_fbl_spi_renesas_csih_cfg.*`; integration
`Demo/*/Appl/Source/fbl_spi_renesas_csih_cfg.c`,
`Include/fbl_spi_if_cfg.h|fbl_spi_renesas_csih_cfg.h`.

## Public API (interface ops)

```c
typedef tFblResult (*tFblSpiInitFct)(FBL_SPI_HANDLE_TYPE_ONLY);
typedef tFblResult (*tFblSpiTransferSyncFct)(... tFblSpiTransferParam ...);
typedef tFblResult (*tFblSpiTransferAsyncFct)(...);
typedef tFblSpiTransferStatus (*tFblSpiGetTransferStatusFct)(...);
typedef tFblResult (*tFblSpiCancelFct)(...);
typedef void (*tFblSpiPollingFct)(void);   /* watchdog/poll hook */
extern tFblSpiIf g_FblSpiRenesasCsih;      /* backend instance */
```

## Usage

Select the backend instance, `Init`, then `TransferSync` (simple) or
`TransferAsync` + `GetTransferStatus`, feeding `tFblSpiPollingFct` from the
FBL task for watchdog/RCR-RP timing.

## Converted documentation

- [TR FBL SPI driver](./technical-reference-drvspi/)

[Back to top](#top)
