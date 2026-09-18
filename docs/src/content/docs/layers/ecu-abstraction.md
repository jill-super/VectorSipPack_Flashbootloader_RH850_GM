---
title: ECU Abstraction
description: NV, transceiver and SPI abstractions
---

- [NV wrapper](../modules/ecu-abstraction/wrapnv/) — `WrapNv_*Sync/Async`,
  FEE / no-NV use cases
- [CAN transceiver TJA1145](../modules/ecu-abstraction/can-trcv/) —
  `FblCanTrcvTja1145{Init,NormalMode,SleepMode,Deinit}`
- [SPI abstraction + driver](../modules/ecu-abstraction/spi/) —
  `fbl_spi_if.h` interface, Renesas CSIH backend
- Converted reading: [NV wrapper TR](../modules/ecu-abstraction/wrapnv/technical-reference-nvwrapper/),
  [SPI TR](../modules/ecu-abstraction/spi/technical-reference-drvspi/),
  [AN-ISC-8-1173](../general/app-notes/an-isc-8-1173-share-fee-blocks/)

[Back to top](#top)
