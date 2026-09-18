---
title: "Technical Reference: GM bootloader updater"
description: "Converted TR GM specifics v1.0"
---

> **Auto-converted from `Doc/TechnicalReferences/TechnicalReference_FBL_Updater_GM.pdf`** (11 pages).
>
> Text was extracted automatically. Layout, tables, figures and
> vector diagrams are best viewed in the original PDF linked below.
> Original: `Doc/TechnicalReferences/TechnicalReference_FBL_Updater_GM.pdf`

## Document outline (from PDF bookmarks)

- 1 Introduction — p. 5
- 2 Theory of Operation — p. 6
- 3 Getting Started — p. 7
  - 3.1 Integration — p. 7
  - 3.2 Mapping — p. 7
  - 3.3 Configuration — p. 8
    - 3.3.1 GENy as Generator — p. 8
    - 3.3.2 Da Vinci Configurator 5 — p. 9
- 4 Glossary and Abbreviations — p. 10
  - 4.1 Glossary — p. 10
  - 4.2 Abbreviations — p. 10
- 5 Contact — p. 11

## Extracted content

### Page 1 of 11

*[Page contains 1 embedded image(s); see original PDF for figures.]*

GM Bootloader Updater
Technical Reference

GM Specifics
Version 1.0


Authors
Sebastian Loos
Status
Released

### Page 2 of 11

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Technical Reference GM Bootloader Updater
© 2016 Vector Informatik GmbH
Version 1.0
2
based on template version 6.0.1
Document Information
History
Author
Date
Version
Remarks
Sebastian Loos
2016-07-27
0.1
Initial Version
Sebastian Loos
2016-12-13
1.0
Release
Reference Documents
No.
Source
Title
Version
[1]
Vector
TechnicalReference_FBL_Updater.pdf
1.00.00
[2]
Vector
TechnicalReference_FBL_<HW>.pdf

### Page 3 of 11

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Technical Reference GM Bootloader Updater
© 2016 Vector Informatik GmbH
Version 1.0
3
based on template version 6.0.1
Contents
1
Introduction .................................................................................................................... 5
2
Theory of Operation ....................................................................................................... 6
3
Getting Started ............................................................................................................... 7
3.1
Integration ................................................................................................................ 7
3.2
Mapping ................................................................................................................... 7
3.3
Configuration ............................................................................................................ 8
3.3.1
GENy as Generator ......................................................................................... 8
3.3.2
Da Vinci Configurator 5 ................................................................................... 9
4
Glossary and Abbreviations ........................................................................................ 10
4.1
Glossary ................................................................................................................. 10
4.2
Abbreviations ......................................................................................................... 10
5
Contact.......................................................................................................................... 11

### Page 4 of 11

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Technical Reference GM Bootloader Updater
© 2016 Vector Informatik GmbH
Version 1.0
4
based on template version 6.0.1
Illustrations
Figure 2-1
Download Process with Invalidation of the Updater .................................... 6
Figure 3-1
Example Mapping for a MPC derivative ...................................................... 7
Figure 3-2
Flash Block Table adaptions ....................................................................... 8
Figure 3-3
Presence Pattern Address .......................................................................... 8
Figure 3-4
Flash Block Table adaptions ....................................................................... 9
Figure 3-5
Presence Pattern Address .......................................................................... 9

Tables
Table 3-1
GM-specific files ......................................................................................... 7

### Page 5 of 11

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Technical Reference GM Bootloader Updater
© 2016 Vector Informatik GmbH
Version 1.0
5
based on template version 6.0.1
1
Introduction
This document covers the GM-specific particularities of the Bootloader Updater. You will
find a general description of the Bootloader Updater in [1]. Please check also for a
document describing the hardware specifics (if available) [2].

### Page 6 of 11

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Technical Reference GM Bootloader Updater
© 2016 Vector Informatik GmbH
Version 1.0
6
based on template version 6.0.1
2
Theory of Operation
The Updater is a component that is downloaded to the ECU like a regular application. The
FBL does not have any knowledge about the Updater so that from the FBL’s point of view
this process is completely transparent. There is no specific handling implemented in the
FBL. I.e. the Updater has to pass the usual validation process like for any application
download.
For production purpose, the updater requires the typical GM specific container including
GM signed header just as any application would. For a detailed description of the update
process see [1]. In Figure 2-1 the typical update process of a GM FBL is shown.

Figure 2-1
Download Process with Invalidation of the Updater
The GM Updater does not transmit or receive messages during the update process.
FBL
Appl
GB6002 Header
FBL
Appl
Updater
New
FBL
FBL
Appl
Updater
New
FBL
New FBL
FBL
Appl
Updater
New
FBL
PP
PP
PP
INVALID
FBL
Appl
GB6002 Header
1. Before Update
5. Download of
(new) Application
2. After Download
of the Updater
3. Update of the
FBL
4. Invalidation of
the FBL
New FBL
New FBL
GB6002 Header
GB6002 Header
GB6002 Header
PP
PP

### Page 7 of 11

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Technical Reference GM Bootloader Updater
© 2016 Vector Informatik GmbH
Version 1.0
7
based on template version 6.0.1
3
Getting Started
3.1
Integration
The OEM-specific files may have to be customized for your application. The files are found
in the FblUpd\_Template folder. You should copy these files to your Bootloader Updater
project folder, and rename them, removing the leading underscore from the filename.

File
Description
_upd_oem_ap.c
Callbacks for invalidating the Presence
Pattern (Programmed State Indicator) after a
successful update.
_upd_oem_ap.h

_upd_oem_cfg.h
Configuration values
Table 3-1
GM-specific files
3.2
Mapping
On some hardware platforms, and if the Updater shall be reset safe, there may be some
restrictions to the mapping.

Figure 3-1
Example Mapping for a MPC derivative
It is required by the GB6002 that the Plain Header is located in the beginning of the
application. Unfortunately this is often the region where some magic words are expected
by the hardware. These magic words are usually located at the start of a flash block and
interfere with the location of the Plain Header. Mostly at least one magic word is necessary
for a reset safe updater.
Affected platforms are e.g.:
128KB
32KB
0x0000 0000
16KB
RCHW1
0x0000 8000
16KB
RCHW2
FBL
0x0000 C000
RCHW0
32KB
RCHW3
0x0001 0000
32KB
0x0001 8000
Updater
GB6002 Header
RCHW4
New FBL

### Page 8 of 11

*[Page contains 4 embedded image(s); see original PDF for figures.]*

Technical Reference GM Bootloader Updater
© 2016 Vector Informatik GmbH
Version 1.0
8
based on template version 6.0.1
 Tricore Aurix (BMHD)
 MPC (RCHW)
 …
Check [2] for some details.
In Figure 3-1 an example for such restrictions on a MPC platform are shown: Because the
FBL usually covers most of the flash area below address 0x10000, the application starts
from 0x10000. It is required that the Plain Header is placed at the beginning of the
application flash area. This leaves only the RCHW at 0x18000 for use by the updater.
3.3
Configuration
If you use multiple memory drivers, make sure that the right value (the same as is used in
the bootloader project) for FBL_PP_SEGMENT_SIZE is set.
If you define more than one logical block in the logical block table of the updater, you have
to adapt FBL_UPD_LBT_NR_OF_UPDATER.


Note
Please check the files for “TODO by customer” tags.


Depending on the used configuration tool, please follow the appropriate sub-paragraph:
3.3.1
GENy as Generator
In the flash block table, (fbl_apfb.c), the flash blocks are specified in which the (new)
Bootloader resides. In the logical block table (fbl_mtab.c) the location of the presence
pattern of the updater is defined.
Create a GENy Configuration, comparable to the Bootloaders configuration. If you re-use
the Bootloaders configuration, you have to make these changes:
1. Change the settings of the flash blocks in which the Bootloader resides from
“Protected” to “Flash” (see Figure 3-2).

Figure 3-2 Flash Block Table adaptions
2. Make sure, the same address for the Presence Pattern as used in the Bootloader
Project is set (see Figure 3-3).

Figure 3-3 Presence Pattern Address

### Page 9 of 11

*[Page contains 3 embedded image(s); see original PDF for figures.]*

Technical Reference GM Bootloader Updater
© 2016 Vector Informatik GmbH
Version 1.0
9
based on template version 6.0.1
3.3.2
Da Vinci Configurator 5
In the flash block table, (Fbl_Fbt.c), the flash blocks are specified in which the (new)
Bootloader resides. In the logical block table (Fbl_Lbt.c) the location of the presence
pattern of the updater is defined.
Create a GENy Configuration, comparable to the Bootloaders configuration. If you re-use
the Bootloaders configuration, you have to make these changes:
Change the settings of the flash blocks in which the Bootloader resides from “Protected” to
“Flash” (see Figure 3-4).

Figure 3-4
Flash Block Table adaptions
Make sure, the same address for the Presence Pattern as used in the Bootloader Project
is set (see Figure 3-5).

Figure 3-5
Presence Pattern Address

### Page 10 of 11

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Technical Reference GM Bootloader Updater
© 2016 Vector Informatik GmbH
Version 1.0
10
based on template version 6.0.1
4
Glossary and Abbreviations
4.1
Glossary
Term
Description


4.2
Abbreviations
Abbreviation
Description

### Page 11 of 11

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Technical Reference GM Bootloader Updater
© 2016 Vector Informatik GmbH
Version 1.0
11
based on template version 6.0.1
5
Contact
Visit our website for more information on

> News
> Products
> Demo software
> Support
> Training data
> Addresses

www.vector.com

---
[Back to top](#top)