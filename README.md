# Flash Bootloader RH850 GM (SLP6)

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Language: C](https://img.shields.io/badge/language-C-blue.svg)
![Platform: RH850](https://img.shields.io/badge/platform-Renesas_RH850-red.svg)
![SIP: 06.04.03](https://img.shields.io/badge/SIP-06.04.03-orange.svg)
![Docs: Astro Starlight](https://img.shields.io/badge/docs-Astro_Starlight-663399.svg)

GM SLP6 flash bootloader for the Renesas RH850 (P1M R7F701363): UDS over CAN,
secure verification (SHA-256 / RSA), LZMA decompression, GM containers, NV
wrapper, TJA1145 transceiver support and an in-field bootloader updater —
delivered as a Vector Software Integration Package (SIP `06.04.03`,
serial `CBD1500635`, GHS `2015.1.7`).

> **Docs site:** source in [`docs/`](docs/) (Astro Starlight). Enable GitHub
> Pages with GitHub Actions as source and add your own build workflow (see
> [Documentation](#documentation)), or preview locally with
> `cd docs && npm ci && npm run dev`. No username or repo name is hard-coded
> anywhere in this repo, so forks work unchanged.

## Table of contents

- [Features](#features)
- [AUTOSAR layers](#autosar-layers)
- [Modules](#modules)
- [Repository structure](#repository-structure)
- [Documentation](#documentation)
- [Getting started](#getting-started)
- [Usage](#usage)
- [Vector vs. custom vs. third-party](#vector-vs-custom-vs-third-party)
- [License](#license)
- [Disclaimer](#disclaimer)

## Features

- **GM SLP6 bootloader** on RH850 P1M — diagnostics, memory and CAN stack in
  `BSW/Fbl`.
- **UDS (ISO 14229) over CAN** — diag core + OEM layer, transport (`fbl_tp`)
  and communication wrapper (`fbl_cw`).
- **Security** — HIS SecMod verification, ESLib SHA-256/RSA, CRC helpers
  (demo RSA-2048 keys in `Misc/DemoKey_2048`, demo use only).
- **GM containers & compression** — programmable-file creation flow and LZMA
  decompression (`BSW/Cmpr_Lzma`).
- **NV + transceiver + SPI** — `WrapNv` (FEE / no-NV), TJA1145 driver, CSIH
  SPI backend.
- **Updater** — in-field FBL update (`BSW/FblUpd`, `Demo/DemoUpdater`).
- **Tooling** — GENy/DaVinci plugins, PES Makesupport + GHS build, HexView,
  HdrGen, vFlash template.

## AUTOSAR layers

| Layer | Folders | Role |
|---|---|---|
| Application Software (ASW) | `Demo/DemoAppl`, `Demo/DemoUpdater/Appl` | Demo app, GM header containers (`ApplHdr_*`) |
| Complex Device Drivers (CDD) | `BSW/Fbl`, `BSW/FblUpd` | Bootloader behaviour outside the standard stack |
| BSW Services | `BSW/Fbl` (diag/mem), `BSW/SecMod`, `BSW/Cmpr_Lzma`, `BSW/FblUpd` | UDS, verification, decompression, update |
| ECU Abstraction | `BSW/WrapNv`, `BSW/FblCanTrcv_Tja1145`, `BSW/FblSpi_VectorIf` | NV wrapper, transceiver, SPI interface |
| MCAL | `BSW/Flash/FlashLib`, `BSW/FblSpi_RenesasCsih`, `BSW/Fbl/*hw*` | Renesas FCL, CSIH driver, CAN/RSCAN glue |
| Integration / generated | `Demo/*/Appl/GenData`, `Demo/*/Config`, `BSW/*/_Template`, `BSW/FblAsrStubs`, `BSW/_Common` | GENy outputs, copy-templates, AUTOSAR stubs |
| Tools & config | `Generators`, `MakeSupport`, `Misc`, `FlashTool` | GENy plugins, Makesupport+GHS, HexView/HdrGen, vFlash |

Layer pages in the docs: `docs/src/content/docs/layers/`
([overview](docs/src/content/docs/autosar-layers.md)).

## Modules

| Module | Layer | Origin | Sources |
|---|---|---|---|
| FBL core (GM SLP6) | BSW Services / CDD | Vector-provided | `BSW/Fbl` |
| Security module (SecMod + ESLib) | BSW Services | Vector-provided (+ cryptovision `act*`) | `BSW/SecMod` |
| LZMA compression | BSW Services | Vector-provided | `BSW/Cmpr_Lzma` |
| FBL updater | BSW Services / CDD | Vector-provided | `BSW/FblUpd` |
| NV wrapper (WrapNv) | ECU Abstraction | Vector-provided | `BSW/WrapNv` |
| SPI (VectorIf + Renesas CSIH) | ECU Abstraction / MCAL | Vector-provided | `BSW/FblSpi_VectorIf`, `BSW/FblSpi_RenesasCsih` |
| CAN transceiver TJA1145 | ECU Abstraction | Vector-provided | `BSW/FblCanTrcv_Tja1145` |
| Flash driver + Renesas FCL | MCAL | Vector-provided + Renesas | `BSW/Flash` |
| AUTOSAR stubs | Integration | Vector-provided, customised | `BSW/FblAsrStubs` |
| Common + GenData | Integration | Vector-provided, customised | `BSW/_Common`, `Demo/*/Appl/GenData` |
| Demo apps | ASW | Vector-provided, customised | `Demo/DemoFbl`, `Demo/DemoAppl`, `Demo/DemoUpdater`, `Demo/Demo_Fee`, `Demo/Demo_Tja1145` |
| Generators (GENy/DaVinci) | Tools | Vector-provided | `Generators/Components` |
| Build support | Tools | Vector-provided + GNU/Cygwin | `MakeSupport` |
| Misc tools & keys | Tools | Vector-provided | `Misc` |
| Flash tool (vFlash) | Tools | Vector-provided | `FlashTool` |

Each module has a factual page under `docs/src/content/docs/modules/` with
purpose, key files, public API, usage, dependencies and converted-PDF links.
The [`sip/`](docs/src/content/docs/sip/) section adds the delivery view
(serial `CBD1500635`) on top of the same modules.

## Repository structure

```text
BSW/                  # bootloader + BSW (see Modules table)
  Fbl/  FblUpd/  SecMod/  WrapNv/  Cmpr_Lzma/  Flash/
  FblCanTrcv_Tja1145/  FblSpi_RenesasCsih/  FblSpi_VectorIf/
  FblAsrStubs/  _Common/  (+ per-module _Template/)
Demo/                 # DemoFbl / DemoAppl (+ApplHdr_* GM containers) /
                      # DemoUpdater / Demo_Fee / Demo_Tja1145
Doc/                  # SIP docs (all converted — see Documentation)
  TechnicalReferences/ ApplicationNotes/ UserManuals/ DeliveryInformation/
Generators/Components # GENy/DaVinci plugins + _Schemes/*.arxml
MakeSupport/          # PES Makesupport 3.13 + GNU/Cygwin cmd tools
Misc/                 # HexView, HdrGen, Cmpr_Lzma tools, DemoKey_2048, Config
FlashTool/            # vFlash template installer + seedkey bundle
docs/                 # Astro Starlight documentation site
.github/              # Dependabot updates + Markdown link-check script
LICENSE               # MIT (+ third-party notice, see License)
```

<details>
<summary><strong>Build system (click to expand)</strong></summary>

- Vector PES Makesupport `3.13` + Green Hills `2015.1.7` for RH850.
- Per-project makefiles: `BSW/Flash/Build/Makefile*`,
  `Demo/*/Appl/Makefile*` (+ `b.bat`/`m.bat` wrappers).
- `BSW/Flash/Build/MkFlashRom.bat <driver.hex>` regenerates
  `BSW/Flash/FlashRom.c` via `Misc/HexView/hexview.exe`.
- `GenData` (`v_cfg.h`, `fbl_cfg.h`, `fbl_mtab.*`, …) is GENy output for
  serial `CBD1500635` — regenerate, don't hand-edit.

</details>

<details>
<summary><strong>Doc inventory (click to expand)</strong></summary>

- `Doc/TechnicalReferences/` — 9 PDFs (FBL GM SLP6, containers, compression,
  RH850, updater ×2, NV wrapper, CmprLzma, SPI).
- `Doc/ApplicationNotes/` — 2 PDFs (FEE sharing `AN-ISC-8-1173`, custom flash
  drivers `AN-ISC-8-1188`).
- `Doc/UserManuals/` — `UserManual_FlashBootloader.pdf`.
- `Doc/DeliveryInformation/` — readme / test / issue PDFs, license addendum
  PDF, `DeliveryDescription_*.html`, `IssueReport_*.xml`.
- `Misc/HexView/ReferenceManual_HexView.pdf`.
- No `.doc`/`.docx` files exist in the tree. Every PDF above plus the
  delivery HTML/XML and key `.txt` notes were converted to Markdown (see
  [Documentation](#documentation)).

</details>

## Documentation

- **Docs site source:** [`docs/`](docs/) — Astro Starlight. Start at
  [`docs/src/content/docs/index.md`](docs/src/content/docs/index.md).
- **Converted documents:** module TRs under
  [`docs/src/content/docs/modules/`](docs/src/content/docs/modules/)
  (`<layer>/<module>/technical-reference-*.md`), general docs under
  [`docs/src/content/docs/general/`](docs/src/content/docs/general/)
  (`delivery/`, `app-notes/`, `user-manuals/`, `tools/`, `txt-docs/`), SIP
  view under [`docs/src/content/docs/sip/`](docs/src/content/docs/sip/).
- **Publish:** enable GitHub Pages with “GitHub Actions” as source and add
  your own workflow that builds `docs/` (`npm ci && npm run build`) and
  deploys `docs/dist`. The site base is read from the `PAGES_BASE` env var,
  so set it to `/<repository-name>/` in the workflow — no hard-coded names
  needed. Local preview: `cd docs && npm ci && npm run dev`
  (`npm run build` → `docs/dist/`).
- **Originals** stay in `Doc/` and `Misc/HexView/`; each converted page links
  back to its source PDF.

## Getting started

### Prerequisites

- **Hardware:** Renesas RH850 P1M (e.g. R7F701363, RV40 flash).
- **Compiler:** Green Hills `2015.1.7` (per `BSW/Fbl/v_ver.h`, `v_cfg.h`).
- **Host:** the shipped `MakeSupport/cmd` Cygwin tools, `HexView`, GENy/DaVinci
  plugins; Node.js `>= 20` only for the docs site.

### Build the flash driver

```bat
cd BSW\Flash\Build
MkFlashRom.bat <your-driver.hex>
```

### Build a demo

```bat
cd Demo\DemoFbl\Appl
m.bat
```

(`Demo/DemoAppl`, `Demo/DemoUpdater` follow the same Makesupport flow;
generated config in `Appl/GenData`, handwritten hooks in `Appl/Source`.)

## Usage

- Program the bootloader + `ApplHdr_*` GM containers (see
  `Demo/DemoAppl/Appl/ApplHdr_*/Gen_All.bat` and the containers TR in the
  docs), then run UDS download over CAN.
- Verify against the converted
  [test report](docs/src/content/docs/general/delivery/test-report-cbd1500635.md).
- `Misc/FblUpd/FblUpd_Prepare.bat` + `Demo/DemoUpdater` cover updater flows;
  `FlashTool/vFlashTemplateInstaller_GM_SLP6.exe` covers PC-side flashing.

## Vector vs. custom vs. third-party

- **Vector-provided:** `BSW/Fbl`, `SecMod` (except `act*`), `WrapNv`,
  `Cmpr_Lzma` wrapper, `flashdrv`, `FblUpd`, transceiver/SPI wrappers,
  `FblAsrStubs`, `_Common`, demo templates, `Generators`, `Doc`,
  `Misc/HexView`, Makesupport — Vector Informatik copyright, Vector license
  conditions (see delivery addendum in the docs).
- **Custom / integration-owned:** handwritten code derived from `_Template`
  (`fbl_ap*`, `upd_*`, `WrapNv_Cfg`, `startup.c`, …), container scripts,
  plus `docs/`, `.github/` and this README — MIT (see [License](#license)).
- **Third-party:** `BSW/Flash/FlashLib` (Renesas FCL, Renesas-only, “AS IS”),
  `BSW/SecMod/act*` (cryptovision actCLibrary), `MakeSupport/cmd`
  (GNU/Cygwin GPL/LGPL). The header inside each file wins; see
  [`docs/src/content/docs/vector-vs-custom.md`](docs/src/content/docs/vector-vs-custom.md).

## License

MIT — see [`LICENSE`](LICENSE). The MIT text covers the documentation and
integration artefacts in this repository; files carrying Vector, Renesas,
cryptovision or GNU copyright/license headers remain under those terms
(detail in `LICENSE` and above).

## Disclaimer

Some files are provided “as is” without warranty — see
[`Misc/HexView/disclaimer.txt`](Misc/HexView/disclaimer.txt), the Renesas
disclaimer in `BSW/Flash/FlashLib/r_fcl.h`, and the delivery addendum.
Demo RSA keys (`Misc/DemoKey_2048/rsakeys_2048.txt`) must not be used in
production.

---

*Conventions: no username or repository name is hard-coded in docs, README
or workflows, so forks stay compatible. The whole tree is SIP delivery
`CBD1500635`; `docs/.../sip/` is a delivery view over the same modules.*
