---
title: Modules
description: All software modules grouped by AUTOSAR layer
---

| Module | Layer | Origin | Page |
|---|---|---|---|
| FBL core (GM SLP6) | BSW Services / CDD | <span class="origin-vector">Vector-provided</span> | [fbl](./bsw-services/fbl/) |
| Security module (SecMod + ESLib) | BSW Services | <span class="origin-vector">Vector-provided</span> + cryptovision | [secmod](./bsw-services/secmod/) |
| LZMA compression | BSW Services | <span class="origin-vector">Vector-provided</span> | [cmpr-lzma](./bsw-services/cmpr-lzma/) |
| FBL updater | BSW Services / CDD | <span class="origin-vector">Vector-provided</span> | [updater](./bsw-services/updater/) |
| NV wrapper (WrapNv) | ECU Abstraction | <span class="origin-vector">Vector-provided</span> | [wrapnv](./ecu-abstraction/wrapnv/) |
| SPI (VectorIf + Renesas CSIH) | ECU Abstraction / MCAL | <span class="origin-vector">Vector-provided</span> | [spi](./ecu-abstraction/spi/) |
| CAN transceiver TJA1145 | ECU Abstraction | <span class="origin-vector">Vector-provided</span> | [can-trcv](./ecu-abstraction/can-trcv/) |
| Flash driver + Renesas FCL | MCAL | <span class="origin-vector">Vector-provided</span> + Renesas | [flash](./mcal/flash/) |
| AUTOSAR stubs | Integration | <span class="origin-vector">Vector-provided</span> customised | [asr-stubs](./integration/asr-stubs/) |
| Common + GenData | Integration | <span class="origin-vector">Vector-provided</span> customised | [common-gendata](./integration/common-gendata/) |
| Demo apps | ASW | <span class="origin-vector">Vector-provided</span> customised | [demo](./asw/demo/) |
| Generators (GENy/DaVinci) | Tools | <span class="origin-vector">Vector-provided</span> | [generators](./tools/generators/) |
| MakeSupport / build | Tools | <span class="origin-vector">Vector-provided</span> + GNU | [makesupport](./tools/makesupport/) |
| Misc tools (HexView/HdrGen/keys) | Tools | <span class="origin-vector">Vector-provided</span> | [misc](./tools/misc/) |
| Flash tool (vFlash) | Tools | <span class="origin-vector">Vector-provided</span> | [flashtool](./tools/flashtool/) |

Each module page states purpose, origin, key files, public API, usage,
dependencies and links to converted documentation. Source links use
repo-relative paths (e.g. `BSW/Fbl/fbl_main.c`) so forks keep working.

[Back to top](#top)
