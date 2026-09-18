---
title: "Issue report CBD1500635"
description: "Converted issue report 30 pages"
---

> **Auto-converted from `Doc/DeliveryInformation/IssueReport_CBD1500635.pdf`** (30 pages).
>
> Text was extracted automatically. Layout, tables, figures and
> vector diagrams are best viewed in the original PDF linked below.
> Original: `Doc/DeliveryInformation/IssueReport_CBD1500635.pdf`

## Document outline (from PDF bookmarks)

- ESCAN00090572 (Wrong documentation for ApplFblCanBusOff()) — p. 4
- ESCAN00092116 (Long runtime of flash library functions can delay the Rx frame processing) — p. 5
- ESCAN00095101 (Tester connection shall not be fixed in default session) — p. 6
- ESCAN00096082 (GB6002 V1.4.2 defines P2* back to 5000ms) — p. 7
- ESCAN00078508 ([depends on derivative] Illegal flash block table configuration cause unintended block erase) — p. 9
- ESCAN00081436 (Using FlashDriver_SetResetVector() might cause exception) — p. 10
- ESCAN00086590 (Obsolete generated code in WrapNv_cfg.c does not compile) — p. 11
- ESCAN00090094 (FblCanWakeup() does not allow to enable Can clock again) — p. 12
- ESCAN00090391 (GM: Calibration header cannot be generated in a way, so that all data bytes can be used) — p. 14
- ESCAN00091938 (Merging does not work) — p. 15
- ESCAN00094695 (Array gRemainderBuffer is not explicit aligned) — p. 15
- ESCAN00095072 (ApplFblSetModulePresence() Cannot write presence pattern to multiple memory devices with different erased values) — p. 16
- ESCAN00095107 (Compile error of generated C-structure) — p. 17
- ESCAN00095356 (Stream output: Erroneous data overflow indicated) — p. 18
- ESCAN00095625 (External Generator errors "BitOrder could not be resolved") — p. 19
- ESCAN00083332 (Compiler warning: Wrong spelling of include SecM_Inc.h in SecM_Par.*) — p. 20
- ESCAN00089241 (Compiler warning: multiple warnings) — p. 21
- ESCAN00089424 (Compiler warning: dead assignment to "returnValue" eliminated) — p. 22
- ESCAN00089425 (Compiler warning: missing braces around initializer) — p. 23
- ESCAN00090113 (Compiler Warning: Result of function-call is ignored) — p. 24
- ESCAN00090114 (Compiler Warning: Assignment in condition) — p. 25
- ESCAN00093014 (Compiler warning: ctc W560: possible truncation at implicit conversion to type "unsigned short int") — p. 26
- ESCAN00094172 (Compiler warning: undefined preprocessor define) — p. 27

## Extracted content

### Page 1 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
1
License Number
Customer
CBD1500635
Nexteer Automotive Corporation
Package: FBL Gm SLP6
Maintenance Expiry Date
2016-02-01
SIP Delivery Date
SIP Version
2017-07-28
06.04.03
SLP
Delivery Number
FBL Gm SLP6
D03
Report Creation Date
2017-07-27
Contact
In case of questions or the need for an update of the basic software delivery, please contact
fblsupport@us.vector.com or your Vector contact person.
Table of Contents
1.
Introduction
1.1 Resolving Issues
1.2 Issue Classification
2.
New Issues
2.1 Safety Relevant Issues: 0
2.2 Runtime Issues without Workaround: 0
2.3 Runtime Issues with Workaround: 4
2.4 Not Released Functionality: 0
2.5 Apparent Issues: 11
2.6 Compiler Warnings: 8
3.
New Issues for Information: 0
4.
Report Legend
5.
Quality Management Contact

### Page 2 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
2
1. Introduction
1.1 Resolving Issues
Reported issues are not automatically fixed with the next update delivery.
If a reported issue shall be fixed, please contact Vector agree on the issues that can be fixed with
upcoming deliveries.
Please note that Vector may fix issues without explicit request.
1.2 Issue Classification
This Issue Report provides issues that have been detected since the last report. The issues have
been classified to facilitate the assessment of their impact:
The chapter 'New Issues' lists issues that have been detected since the last report and which could
not be excluded based on the use-case defined in the questionnaire. The issues are classified as
follows:
- 
Safety Related Issues: Safety related issues have impact on the functional safety of the
software module.  If this issue interferes with the functional safety concept of the ECU, this
module (or module configuration) must not be used for serial production in a safety-related
project. The effect of the issue to the ECU functionality and functional safety has to be
analyzed by the user as the software usage and its configuration is not known by Vector. The
risk of change has also to be taken into account.
- 
Runtime Issues without Workaround: Runtime issues without a workaround require an
update of the software delivery in case the issue affects the ECU overall functionality. The
effect of an issue to the ECU functionality has to be analyzed by the customer as the software
usage and its configuration is not known by Vector. The risk of change has also to be taken
into account.
- 
Runtime Issues with Workaround: It is not recommended to update a delivery due to a
runtime issue with a documented workaround. The effect of an issue to the ECU functionality
has to be analyzed by the user as the software usage and its configuration is not known by
Vector. The risk of change has also to be taken into account.
- 
Not Released Functionality: Not released functionalities (BETA) are either complete
software modules or features in the software module that have not yet passed a complete
development cycle (they are e.g. not or only partly tested). If a BETA issue ticket affects a
complete software module, the software module must not be used for serial production. If a
BETA issue ticket affects a feature in the software module, the user has to ensure that all
BETA features are disabled as indicated for the serial production release of the ECU.
- 
Apparent Issues: Apparent issues are detected immediately when using the software
module. If an issue does not show up while working with the software module, the ECU
project is not affected by the issue. Apparent issues may or may not have workarounds.
- 
Compiler Warnings: As a service we also provide the known compiler warnings. The
occurrence of a compiler warning may depend on the used software module configuration and
compiler settings.
The chapter 'New Issues for Information' lists issues that are not relevant for the use-case that
has been documented in the questionnaire provided to Vector. The issues may, however, be
relevant for other use-cases. Additionally, issues that have been accepted or are tolerated by the
OEM (as defined in the questionnaire) are reported here.

### Page 3 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
3
2. New Issues
2.1 Safety Relevant Issues
Safety related issues have impact on the functional safety of the software module.  If this issue
interferes with the functional safety concept of the ECU, this module (or module configuration)
must not be used for serial production in a safety-related project.
The effect of the issue to the ECU functionality and functional safety has to be analyzed by the
user as the software usage and its configuration is not known by Vector. The risk of change has
also to be taken into account.
No issue to be reported.
2.2 Runtime Issues without Workaround
Runtime issues without a workaround require an update of the software delivery in case the issue
affects the ECU overall functionality. The effect of an issue to the ECU functionality has to be
analyzed by the customer as the software usage and its configuration is not known by Vector. The
risk of change has also to be taken into account.
No issue to be reported.
2.3 Runtime Issues with Workaround
It is not recommended to update a delivery due to a runtime issue with a documented
workaround. The effect of an issue to the ECU functionality has to be analyzed by the user as the
software usage and its configuration is not known by Vector. The risk of change has also to be
taken into account.
Index
ESCAN00090572
Wrong documentation for ApplFblCanBusOff()
FBL_TechRef_Gm@Doc_TechRef
ESCAN00092116
Long runtime of flash library functions can delay the Rx frame processing
FblDrvFlash_Rh850Rv40His@Impl_Base
ESCAN00095101
Tester connection shall not be fixed in default session
FblDiag_14229_Gm@Implementation
ESCAN00096082
GB6002 V1.4.2 defines P2* back to 5000ms
FBL_Gm_SLP6@Preconfig

### Page 4 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
4
ESCAN00090572
Wrong documentation for ApplFblCanBusOff()
Component@Subcomponent:
FBL_TechRef_Gm@Doc_TechRef
First affected version:
6.00.00
Fixed in versions:
6.03.00
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Bootloader does not recover from bus-off
When does this happen:
-------------------------------------------------------------------
When bootloader enters bus-off and there is no recover strategy implemented in
ApplFblCanBusOff()
Issue can be caused by wrong information in documentation in the API description of
ApplFblCanBusOff().
"No action is required in order to recover."
This statement is wrong. The user must implement a recover strategy in ApplFblCanBusOff().
In which configuration does this happen:
-------------------------------------------------------------------
All

Resolution Description:
Workaround:
-------------------------------------------------------------------
Implement bus-off recovery strategy in ApplFblCanBusOff().
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 5 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
5
ESCAN00092116
Long runtime of flash library functions can delay the
Rx frame processing
Component@Subcomponent:
FblDrvFlash_Rh850Rv40His@Impl_Base
First affected version:
1.06.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Flash library operations might be very runtime consuming.
This might delay the processing of a Rx frame that long, that the corresponding CAN mailbox has
already been overwritten with the following Rx frame assigned to the mailbox.
The download will abort with a NRC 0x73 (WrongBlockSequenceCounter).
When does this happen:
-------------------------------------------------------------------
During the flash routines of the flash library.
In which configuration does this happen:
-------------------------------------------------------------------
-Usage of pipelined programming/early acknowledge
-So far the behavior has only been detected on F1H and F1K derivatives

Resolution Description:
Workaround:
-------------------------------------------------------------------
Driving the system with a higher clock also speed up the flash operations and reduces their
runtime.
(verified with R7F7015032+R7F7015874AFP @ 120MHz)
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 6 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
6
ESCAN00095101
Tester connection shall not be fixed in default
session
Component@Subcomponent:
FblDiag_14229_Gm@Implementation
First affected version:
4.01.03
Fixed in versions:
4.03.01
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Tester connection is fixed once communication happens in default session.
This is unintended, instead tester connection shall stay flexible in default session.
When does this happen:
-------------------------------------------------------------------
When tester communicates with Fbl in default session.
In which configuration does this happen:
-------------------------------------------------------------------
If FBL_DIAG_ENABLE_GM_RESET_TESTER_IN_DEF_SESSION is not set.

Resolution Description:
Workaround:
-------------------------------------------------------------------
Set this macro (e.g. in MandatoryDeliveryPreconfig.cfg, content generated to fbl_cfg.h):
#define FBL_DIAG_ENABLE_GM_RESET_TESTER_IN_DEF_SESSION
In order to check the configuration is OK:
- Before adding the above macro to configuration, verify, that tester is fixed in default session.
 so e.g. communication is not possible to tester F2 after communicating with tester F3 to the Fbl
after reset
- After adding the macro, verify communication in default session is possible to different testers
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 7 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
7
ESCAN00096082
GB6002 V1.4.2 defines P2* back to 5000ms
Component@Subcomponent:
FBL_Gm_SLP6@Preconfig
First affected version:
1.03.02
Fixed in versions:
1.05.12
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
A) GB6002 versions < V1.3 and GB6002 versions >= V1.4.2 define P2* to 5000
b) GB6002 versions >= V1.3 and GB6002 versions < V1.4.2 define P2* to 30000
Some deliveries prepared for V1.4.2 still use intermediate variant b), but should use a)
When does this happen:
-------------------------------------------------------------------
At configuration time.
In which configuration does this happen:
-------------------------------------------------------------------
Always

Resolution Description:
Workaround:
-------------------------------------------------------------------
GENy based environment:
- Overwrite FBL_DIAG_TIME_P3MAX within GENy FblDrvCan_XXX -> User Config File loaded file
(typically MandatoryDeliveryPreconfig.cfg)
Da Vinci Configurator based environment:
- Change the value "Fbl->FblGeneral->P2* Server" in configuration to 5000ms
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.
2.4 Not Released Functionality
Not released functionalities (BETA) are either complete software modules or features in the
software module that have not yet passed a complete development cycle (they are e.g. not or
only partly tested). If a BETA issue ticket affects a complete software module, the software
module must not be used for serial production. If a BETA issue ticket affects a feature in the
software module, the user has to ensure that all BETA features are disabled as indicated for the
serial production release of the ECU.
No issue to be reported.

### Page 8 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
8
2.5 Apparent Issues
Apparent issues are detected immediately when using the software module. If an issue does not
show up while working with the software module, the ECU project is not affected by the issue.
Apparent issues may or may not have workarounds.
Index
ESCAN00078508
[depends on derivative] Illegal flash block table configuration cause
unintended block erase
FblDrvFlash_Rh850Rv40His@Impl_Base
ESCAN00081436
Using FlashDriver_SetResetVector() might cause exception
FblDrvFlash_Rh850Rv40His@Impl_Base
ESCAN00086590
Obsolete generated code in WrapNv_cfg.c does not compile
SysService_WrapperNv@GenTool_Geny
ESCAN00090094
FblCanWakeup() does not allow to enable Can clock again
FblDrvCan_Rh850RscanCrx@Implementation
ESCAN00090391
GM: Calibration header cannot be generated in a way, so that all data bytes
can be used
FblTool_Hexeditor_Hexview@Application_Exe
ESCAN00091938
Merging does not work
FblTool_Hexeditor_Hexview@Application_Exe
ESCAN00094695
Array gRemainderBuffer is not explicit aligned
FblLib_Mem@Implementation
ESCAN00095072
ApplFblSetModulePresence() Cannot write presence pattern to multiple
memory devices with different erased values
FblKbApi@Implementation
ESCAN00095107
Compile error of generated C-structure
FblTool_Hexeditor_Hexview@Application_Exe
ESCAN00095356
Stream output: Erroneous data overflow indicated
FblLib_Mem@Implementation
ESCAN00095625
External Generator errors "BitOrder could not be resolved"
GenTool_GenyVcfgNameDecorator@GenTool_Geny

### Page 9 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
9
ESCAN00078508
[depends on derivative] Illegal flash block table
configuration cause unintended block erase
Component@Subcomponent:
FblDrvFlash_Rh850Rv40His@Impl_Base
First affected version:
0.90.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
If the code flash contains gaps where no flash exists and the user configure a flash block in this
area, the flash driver will erase the next valid flash block (first block with start address bigger than
the illegal configured block).
When does this happen:
-------------------------------------------------------------------
Always and immediately
In which configuration does this happen:
-------------------------------------------------------------------
all configurations, but not all derivatives
Note: The gap between user area and extended user area is not relevant. Until now, no known
derivative is affected by this issue!

Resolution Description:
Workaround:
-------------------------------------------------------------------
Well configured flash block table, which corresponds to the real flash block structure.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 10 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
10
ESCAN00081436
Using FlashDriver_SetResetVector() might cause
exception
Component@Subcomponent:
FblDrvFlash_Rh850Rv40His@Impl_Base
First affected version:
1.02.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
When using FlashDriver_SetResetVector() an exception occurs.
When does this happen:
-------------------------------------------------------------------
When code called from wdTriggerFct (typically FblLookForWatchdog()) is not located in RAM.
This may apply e.g. to the Communication Wrapper task functions.
In which configuration does this happen:
-------------------------------------------------------------------
if FLASH_ENABLE_SET_RESETVECTOR_API is enabled.

Resolution Description:
Workaround:
-------------------------------------------------------------------
 Either manually handle memDrvDeviceActive in the updater or locate any code referenced by
FblLookForWatchdog() in RAM
Resolution:
-------------------------------------------------------------------
None.

### Page 11 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
11
ESCAN00086590
Obsolete generated code in WrapNv_cfg.c does not
compile
Component@Subcomponent:
SysService_WrapperNv@GenTool_Geny
First affected version:
1.00.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Obsolete generated code in WrapNv_cfg.c does not compile, file should no longer be generated.
When does this happen:
-------------------------------------------------------------------
Always and immediately
In which configuration does this happen:
-------------------------------------------------------------------
Any configuration

Resolution Description:
Workaround:
-------------------------------------------------------------------
The C file is not needed. Do not compile this file and try to link it to your bootloader.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 12 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
12
ESCAN00090094
FblCanWakeup() does not allow to enable Can clock
again
Component@Subcomponent:
FblDrvCan_Rh850RscanCrx@Implementation
First affected version:
1.02.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
After call to FblCanSleep and wakup call to FblCanWakeUp, no CAN communicaton is possible any
more.
When does this happen:
-------------------------------------------------------------------
When waking up again via FblCanWakeUp.
In which configuration does this happen:
-------------------------------------------------------------------
Configurations that support Can low power mode (FBL_ENABLE_SLEEPMODE defined).

Resolution Description:

### Page 13 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
13
ESCAN00090094
FblCanWakeup() does not allow to enable Can clock
again
Workaround:
-------------------------------------------------------------------
1. Replace calls to FblCanWakeUp() by calls to ApplFblCanWakeUp() in user callback context.
2. Add code to ApplFblCanWakeUp() to wake up again:
void ApplFblCanWakeUp( void )
{
 /* Clear error flags */
 Can->ChCtrl[kFblCanChannel].EF &= FblInvert32Bit(kCanEfMask);
 /* Clear rx full pending buffers 0 - 31*/
 Can->CRBRCF[0] = 0;
 /* Set channel reset mode (currently in stop or reset mode) */
 CanLL_ModeReq_Phys(kFblCanChannel,kCanResetMode);
 while ((!CanLL_ModeCheck_Phys(kFblCanChannel,kCanResetMode)))
 {
 ;
 }
 /* Switch to operation mode (and wait till it is reached) */
 CanLL_ModeReq_Phys(kFblCanChannel,kCanOperationMode);
 while (!CanLL_ModeCheck_Phys(kFblCanChannel,kCanOperationModeCheck))
 {
 ;
 }
}
3. Define these macros so that they are available within ApplFblCanWakeUp():
 /**< Requests a on a physical channel */
#define CanLL_ModeReq_Phys(pch,mode) (Can->ChCtrl[pch].CR = ((Can->ChCtrl[pch].CR &
kCanModeMask) | (mode)))
#define CanLL_ModeCheck_Phys(pch,mode) ((Can->ChCtrl[pch].SR & kCanModeBits) == ((mode)
& kCanModeBits))
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 14 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
14
ESCAN00090391
GM: Calibration header cannot be generated in a
way, so that all data bytes can be used
Component@Subcomponent:
FblTool_Hexeditor_Hexview@Application_Exe
First affected version:
1.05.00
Fixed in versions:
1.11.00
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Wrong calibration headers are generated.
GM SLP5, SLP6 (XML based header generation):
* The calibration file header is placed before the expeced (and configured) location, if not more
than really necessary bytes (0x14) are left empty.

GM SLP4 (BAT - file based header generation):
* The calibration header overwrites existing data bytes, if not more than really necessary bytes
(0x14) are left empty.
When does this happen:
-------------------------------------------------------------------
At calibration file header generation time.
Hexview alignment value (through parameter /AD:XX) is chosen according to the (flash) memories
write segment size (ALIGN_SEG_SIZE).
This does not happen, if the amount of bytes left empty is high enough. The number is high
enough, if it is at minimum the smallest multiple of ALIGN_SEG_SIZE greater equal 14.
If less is left empty, the issue occurs.
E.g. the issue occurs:
* if SEG_SIZE = 4 is and only 14 bytes are left empty (16 bytes need to be left empty).
* if SEG_SIZE = 64 is and only 14 bytes are left empty (64 bytes need to be left empty).
In which configuration does this happen:
-------------------------------------------------------------------
If the memories write segment size and thus required alignment value is larger 2 (for internal
flash this is e.g. flashdrv.h: FLASH_SEGMENT_SIZE).

Resolution Description:
Workaround:
-------------------------------------------------------------------
Leave at minimum the smallest multiple of ALIGN_SEG_SIZE (compare issue description) greater
equal 14 empty at start of file.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.
The resolution allows to do correct fill using /GMAL=X feature. However, data bytes are not
possible to be correctly aligned.

### Page 15 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
15
ESCAN00091938
Merging does not work
Component@Subcomponent:
FblTool_Hexeditor_Hexview@Application_Exe
First affected version:
1.05.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Merging two files does not work.
When does this happen:
-------------------------------------------------------------------
When merging two files using command line option /MT or /MO without an offset but with a range.
In which configuration does this happen:
-------------------------------------------------------------------
In all configuration.

Resolution Description:
Workaround:
-------------------------------------------------------------------
Specify an offset of zero.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.
ESCAN00094695
Array gRemainderBuffer is not explicit aligned
Component@Subcomponent:
FblLib_Mem@Implementation
First affected version:
1.00.00
Fixed in versions:
4.02.01
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
The program flow hit an assertion in FlashDriver_WriteToFlash() (fbl_flio.c). This assertion asserts
the correct alignment of the write buffer.
When does this happen:
-------------------------------------------------------------------
This happens for example whenever a file with a non-aligned length is to be programmed.
In which configuration does this happen:
-------------------------------------------------------------------
Always in the case the compiler/ linker does not align objects the used flash memory.

Resolution Description:
Workaround:
-------------------------------------------------------------------
Align variable gRemainderBuffer from fbl_mem.c to a 32-bit boundary.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 16 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
16
ESCAN00095072
ApplFblSetModulePresence() Cannot write presence
pattern to multiple memory devices with different
erased values
Component@Subcomponent:
FblKbApi@Implementation
First affected version:
1.00.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
ApplFblSetModulePresence() errantly returns kFblFailed when it has written a valid presence
pattern. Download will be halted.
When does this happen:
-------------------------------------------------------------------
During the validation of a block of memory down loaded to secondary device type with a different
erased value than primary memory
In which configuration does this happen:
-------------------------------------------------------------------
FBL_ENABLE_PRESENCE_PATTERN
 AND
FBL_ENABLE_MULTIPLE_MEM_DEVICES
 AND
FBL_FLASH_DELETED is a different value than the deleted value of the secondary device driver.

Resolution Description:
Workaround:
-------------------------------------------------------------------
ApplFblSetModulePresence() has to be adapted according to the erased code.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 17 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
17
ESCAN00095107
Compile error of generated C-structure
Component@Subcomponent:
FblTool_Hexeditor_Hexview@Application_Exe
First affected version:
1.05.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
on C-File export Hexview generates
typedef struct _tFblUpdateBlkInfo
{
 FBL_ADDR_TYPE blockAddress;
 FBL_MEMSIZE_TYPE blockLength;
 V_MEMROM0 V_MEMROM1 vuint8 V_MEMROM2 * V_MEMROM1 V_MEMROM2 blockSource;
} tFblUpdateBlkInfo;
this may lead to compiler errors on platforms where V_MEMROM2 is defined to "const" because a
const inside a struct is not allowed.
When does this happen:
-------------------------------------------------------------------
on C-file export
In which configuration does this happen:
-------------------------------------------------------------------
if V_MEMROM2 is defined to "const" and C-File export is used

Resolution Description:
Workaround:
-------------------------------------------------------------------
replace
 V_MEMROM0 V_MEMROM1 vuint8 V_MEMROM2 * V_MEMROM1 V_MEMROM2 blockSource;
by
 V_MEMROM1 vuint8 V_MEMROM2 V_MEMROM3 * blockSource;
manually
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 18 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
18
ESCAN00095356
Stream output: Erroneous data overflow indicated
Component@Subcomponent:
FblLib_Mem@Implementation
First affected version:
3.00.00
Fixed in versions:
4.02.01
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Download reports an error, typically NRC 0x71 (TransferDataSuspended).
In case of a UDS download sequence this negative response occurs on a TransferData request.
When does this happen:
-------------------------------------------------------------------
When downloading data which is passed to the stream output processing, e.g. delta download.
Additionally the input length has to be larger than the announced output length, which is expected
to be produced by the processing operation.
In which configuration does this happen:
-------------------------------------------------------------------
When all of the following applies:
- Additional run-time checks are enabled (FBL_ENABLE_SYSTEM_CHECK)
- Stream output processing is enabled (FBL_MEM_ENABLE_STREAM_OUTPUT)
- Processed data length is not enabled (FBL_DISABLE_PROCESSED_DATA_LENGTH)

Resolution Description:
Workaround:
-------------------------------------------------------------------
Any of the following workarounds can be applied:
- Disable additional run-time checks (FBL_DISABLE_SYSTEM_CHECK)
- Do not download delta images which are larger than the actual target image
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 19 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
19
ESCAN00095625
External Generator errors "BitOrder could not be
resolved"
Component@Subcomponent:
GenTool_GenyVcfgNameDecorator@GenTool_Geny
First affected version:
2.16.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
External Generators throw an error like: "BitOrder could not be resolved".
When does this happen:
-------------------------------------------------------------------
During generation time with external generators like e.g. DrvEep_XXspi01Asr
In which configuration does this happen:
-------------------------------------------------------------------
In all configurations with external generators that needs the BoardBitOrder Parameter.

Resolution Description:
Workaround:
-------------------------------------------------------------------
Create or patch the Board_preo.arxml (within <SIP>\external\Generators\Components\_Boards
\Canoeemu\bswmd) and add a preconfiguration of the parameter BoardBitOrder with the
according value for your platform.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.
2.6 Compiler Warnings
As a service we also provide the known compiler warnings. The occurrence of a compiler warning
may depend on the used software module configuration and compiler settings.
Index
ESCAN00083332
Compiler warning: Wrong spelling of include SecM_Inc.h in SecM_Par.*
SysService_SecModHis@GenTool_Geny
ESCAN00089241
Compiler warning: multiple warnings
SysService_CryptoCv@Impl_actCLib
ESCAN00089424
Compiler warning: dead assignment to "returnValue" eliminated
SysService_CryptoCv@Impl_ESLib
ESCAN00089425
Compiler warning: missing braces around initializer
SysService_CryptoCv@Impl_ESLib
ESCAN00090113
Compiler Warning: Result of function-call is ignored
SysService_CryptoCv@Impl_ESLib
ESCAN00090114
Compiler Warning: Assignment in condition
SysService_CryptoCv@Impl_actCLib
ESCAN00093014
Compiler warning: ctc W560: possible truncation at implicit conversion to type
"unsigned short int"
FblDiag_SecHdr_Gm@Implementation
ESCAN00094172
Compiler warning: undefined preprocessor define
SysService_WrapperNv@Implementation

### Page 20 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
20
ESCAN00083332
Compiler warning: Wrong spelling of include
SecM_Inc.h in SecM_Par.*
Component@Subcomponent:
SysService_SecModHis@GenTool_Geny
First affected version:
1.03.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Compiler warns for a differently spelled file name.
When does this happen:
-------------------------------------------------------------------
The warning is issued by the compiler during compilation of the code in case the configuration is
as described below.
In which configuration does this happen:
-------------------------------------------------------------------
Any configuration that checks the case of includes.

Resolution Description:
Workaround:
-------------------------------------------------------------------
If your operating system has case sensitive file names you can create a SecM_inc.h which includes
a SecM_Inc.h.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 21 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
21
ESCAN00089241
Compiler warning: multiple warnings
Component@Subcomponent:
SysService_CryptoCv@Impl_actCLib
First affected version:
1.00.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
- Compiler warns for possible loss of data: Check if cast is missing and if there is really a data loss
due to an implicit/explicit cast on the target platform
- Compiler warns for ambiguous code, parentheses recommended.
When does this happen:
-------------------------------------------------------------------
The warning is issued by the compiler during compilation of the code in case the configuration is
as described below.
In which configuration does this happen:
-------------------------------------------------------------------
Always.

Resolution Description:
Workaround:
-------------------------------------------------------------------
No workaround available.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 22 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
22
ESCAN00089424
Compiler warning: dead assignment to
"returnValue" eliminated
Component@Subcomponent:
SysService_CryptoCv@Impl_ESLib
First affected version:
1.00.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Compiling file: ../../../BSW/SecMod/ESLib_RSA_V15_Ver_SHA256.c
ctc W588: ["../../../BSW/SecMod/ESLib_RSA_V15_Ver_SHA256.c" 193/17] dead assignment to
"returnValue" eliminated
ctc W588: ["../../../BSW/SecMod/ESLib_RSA_V15_Ver_SHA256.c" 358/17] dead assignment to
"returnValue" eliminated
When does this happen:
-------------------------------------------------------------------
The warning is issued by the compiler during compilation of the code in case the configuration is
as described below.
In which configuration does this happen:
-------------------------------------------------------------------
- Signature verification using RSASSA-PKCS1-v1_5 is used

Resolution Description:
Workaround:
-------------------------------------------------------------------
No workaround available.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 23 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
23
ESCAN00089425
Compiler warning: missing braces around initializer
Component@Subcomponent:
SysService_CryptoCv@Impl_ESLib
First affected version:
1.01.01
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Compiling file: ../../../BSW/SecMod/ESLib_version.c
ctc W542: ["../../../BSW/SecMod/ESLib_version.c" 73/4] missing braces around initializer
When does this happen:
-------------------------------------------------------------------
The warning is issued by the compiler during compilation of the code in case the configuration is
as described below.
In which configuration does this happen:
-------------------------------------------------------------------
In all configurations.

Resolution Description:
Workaround:
-------------------------------------------------------------------
Since ESLib_version.c is only used for component testing, it can be excluded from the build for
integration.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 24 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
24
ESCAN00090113
Compiler Warning: Result of function-call is ignored
Component@Subcomponent:
SysService_CryptoCv@Impl_ESLib
First affected version:
1.00.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Compiling file: ../../../BSW/SecMod/ESLib_SHA256.c
../../../BSW/SecMod\ESLib_SHA256.c(71): WARNING C1420: Result of function-call is ignored
../../../BSW/SecMod\ESLib_SHA256.c(180): WARNING C1420: Result of function-call is ignored
When does this happen:
-------------------------------------------------------------------
The warning is issued by the compiler during compilation of the code in case the configuration is
as described below.
In which configuration does this happen:
-------------------------------------------------------------------
in all configurations


Resolution Description:
Workaround:
-------------------------------------------------------------------
No workaround available.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 25 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
25
ESCAN00090114
Compiler Warning: Assignment in condition
Component@Subcomponent:
SysService_CryptoCv@Impl_actCLib
First affected version:
1.00.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Compiling file: ../../../BSW/SecMod/actBNReduce.c
../../../BSW/SecMod\actBNReduce.c(117): WARNING C5909: Assignment in condition
Compiling file: ../../../BSW/SecMod/actBigNum.c
../../../BSW/SecMod\actBigNum.c(234): WARNING C5909: Assignment in condition
When does this happen:
-------------------------------------------------------------------
The warning is issued by the compiler during compilation of the code in case the configuration is
as described below.
In which configuration does this happen:
-------------------------------------------------------------------
in all configurations

Resolution Description:
Workaround:
-------------------------------------------------------------------
No workaround available.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 26 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
26
ESCAN00093014
Compiler warning: ctc W560: possible truncation at
implicit conversion to type "unsigned short int"
Component@Subcomponent:
FblDiag_SecHdr_Gm@Implementation
First affected version:
2.00.00
Fixed in versions:
3.03.00
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Compiler warning: ctc W560: possible truncation at implicit conversion to type "unsigned short int"
When does this happen:
-------------------------------------------------------------------
The warning is issued by the compiler during compilation of the code in case the configuration is
as described below.
In which configuration does this happen:
-------------------------------------------------------------------
in every configuration

Resolution Description:
Workaround:
-------------------------------------------------------------------
No workaround available.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 27 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
27
ESCAN00094172
Compiler warning: undefined preprocessor define
Component@Subcomponent:
SysService_WrapperNv@Implementation
First affected version:
2.00.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Compiler warns for an undefined preprocessor define (FEE_FSS_CONTROL_API).
When does this happen:
-------------------------------------------------------------------
The warning is issued by the compiler during compilation of the code in case the configuration is
as described below.
In which configuration does this happen:
-------------------------------------------------------------------
In projects were not the Vector Autosar FEE is used.

Resolution Description:
Workaround:
-------------------------------------------------------------------
Add the following line to the config file (WrapNv_Cfg.h):
#define FEE_FSS_CONTROL_API STD_OFF
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

### Page 28 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
28
3. New Issues for Information
Issues which should not have an effect on the usage of the license as the issues are relevant for
use cases other than those defined in the questionnaire. The list contains issues that have been
detected since the last report.
Issues listed in this section are not relevant for the use case that has been documented in the
questionnaire provided to Vector. However, the issues may be relevant for other use cases.  Also
issues that have been accepted or are tolerated by the OEM (as defined in the questionnaire) are
reported here.
No issue to be reported.

### Page 29 of 30

*[Page contains 3 embedded image(s); see original PDF for figures.]*

Issue Report
29
4. Report Legend

### Page 30 of 30

*[Page contains 1 embedded image(s); see original PDF for figures.]*

Issue Report
30
5. Quality Management Contact
Quality Management
Productline Embedded Software (PES)

Vector Informatik GmbH
Ingersheimer Str. 24
D-70499 Stuttgart

Phone: +49 711 80670-3700
Fax: +49 711 80670-399
eMail: QualityPES@vector.com

---
[Back to top](#top)