---
title: "Issue report XML (structure)"
description: "Structural rendering of IssueReport CBD1500635 XML"
---
> **Auto-converted from `Doc/DeliveryInformation/IssueReport_CBD1500635.xml`.**
> Approx. issue entries: 48. Full data remains in the original XML.

## Element structure (truncated)

- **issueReport**
  - **schemaVersion**: 1
  - **reportData**
    - **title**: Open Issues in 'CBD1500635'
    - **reportCreationDate**: 2017-07-27
    - **reportIdentifier**: CBD1500635-D03-2017-07-27-16:13:37
  - **license**
    - **licenseNumber**: CBD1500635
    - **customer**: Nexteer Automotive Corporation
Package: FBL Gm SLP6
    - **vectorContactEmail**: fblsupport@us.vector.com
    - **maintenanceExpiryDate**: 2016-02-01
  - **deliveries**
    - **delivery**
      - **releaseNumber**: D03
      - **deliveryDate**: 2017-07-28
      - **slp**: FBL Gm SLP6
      - **sip**: 06.04.03
  - **issues**
    - **issue**
      - **identifier**: ESCAN00092116
      - **package**: FblDrvFlash_Rh850Rv40His
      - **subpackage**: Impl_Base
      - **severity**: Medium
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: Long runtime of flash library functions can delay the Rx frame processing
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
Flash library operations might be very runtime consuming.
This might delay the processing of a Rx frame tha
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
Driving the system with a higher clock also speed up the flash operations and reduces their runtime.
(verified with R7F7
      - **firstAffectedVersion**: 1.06.00
      - **versionsFixed**
    - **issue**
      - **identifier**: ESCAN00096082
      - **package**: FBL_Gm_SLP6
      - **subpackage**: Preconfig
      - **severity**: Medium
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: GB6002 V1.4.2 defines P2* back to 5000ms
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
A) GB6002 versions < V1.3 and GB6002 versions >= V1.4.2 define P2* to 5000 
b) GB6002 versions >= V1.3 and 
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
GENy based environment:
- Overwrite FBL_DIAG_TIME_P3MAX within GENy FblDrvCan_XXX -> User Config File loaded file (typic
      - **firstAffectedVersion**: 1.03.02
      - **versionsFixed**: 1.05.12
    - **issue**
      - **identifier**: ESCAN00090572
      - **package**: FBL_TechRef_Gm
      - **subpackage**: Doc_TechRef
      - **severity**: Medium
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: Wrong documentation for ApplFblCanBusOff()
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
Bootloader  does not recover from bus-off


When does this happen:
----------------------------------------
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
Implement bus-off recovery strategy in ApplFblCanBusOff().


Resolution:
-----------------------------------------------
      - **firstAffectedVersion**: 6.00.00
      - **versionsFixed**: 6.03.00
    - **issue**
      - **identifier**: ESCAN00095101
      - **package**: FblDiag_14229_Gm
      - **subpackage**: Implementation
      - **severity**: Medium
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: Tester connection shall not be fixed in default session
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
Tester connection is fixed once communication happens in default session.
This is unintended, instead teste
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
Set this macro (e.g. in MandatoryDeliveryPreconfig.cfg, content generated to fbl_cfg.h):

#define  FBL_DIAG_ENABLE_GM_RE
      - **firstAffectedVersion**: 4.01.03
      - **versionsFixed**: 4.03.01
    - **issue**
      - **identifier**: ESCAN00081436
      - **package**: FblDrvFlash_Rh850Rv40His
      - **subpackage**: Impl_Base
      - **severity**: Low
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: Using FlashDriver_SetResetVector() might cause exception
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
When using FlashDriver_SetResetVector() an exception occurs.

When does this happen:
----------------------
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
 Either manually handle memDrvDeviceActive in the updater or locate any code referenced by FblLookForWatchdog() in RAM


      - **firstAffectedVersion**: 1.02.00
      - **versionsFixed**
    - **issue**
      - **identifier**: ESCAN00091938
      - **package**: FblTool_Hexeditor_Hexview
      - **subpackage**: Application_Exe
      - **severity**: Low
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: Merging does not work
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
Merging two files does not work.


When does this happen:
-------------------------------------------------
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
Specify an offset of zero.

Resolution:
-------------------------------------------------------------------
The describe
      - **firstAffectedVersion**: 1.05.00
      - **versionsFixed**
    - **issue**
      - **identifier**: ESCAN00095356
      - **package**: FblLib_Mem
      - **subpackage**: Implementation
      - **severity**: Low
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: Stream output: Erroneous data overflow indicated
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
Download reports an error, typically NRC 0x71 (TransferDataSuspended).
In case of a UDS download sequence t
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
Any of the following workarounds can be applied:

- Disable additional run-time checks (FBL_DISABLE_SYSTEM_CHECK)
- Do n
      - **firstAffectedVersion**: 3.00.00
      - **versionsFixed**: 4.02.01
    - **issue**
      - **identifier**: ESCAN00086590
      - **package**: SysService_WrapperNv
      - **subpackage**: GenTool_Geny
      - **severity**: Low
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: Obsolete generated code in WrapNv_cfg.c does not compile
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
Obsolete generated code in WrapNv_cfg.c does not compile, file should no longer be generated.


When does t
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
The C file is not needed. Do not compile this file and try to link it to your bootloader.


Resolution:
----------------
      - **firstAffectedVersion**: 1.00.00
      - **versionsFixed**
    - **issue**
      - **identifier**: ESCAN00095625
      - **package**: GenTool_GenyVcfgNameDecorator
      - **subpackage**: GenTool_Geny
      - **severity**: Low
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: External Generator errors "BitOrder could not be resolved"
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
External Generators throw an error like: "BitOrder could not be resolved".


When does this happen:
-------
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
Create or patch the Board_preo.arxml (within <SIP>\external\Generators\Components\_Boards\Canoeemu\bswmd) and add a prec
      - **firstAffectedVersion**: 2.16.00
      - **versionsFixed**
    - **issue**
      - **identifier**: ESCAN00094695
      - **package**: FblLib_Mem
      - **subpackage**: Implementation
      - **severity**: Low
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: Array gRemainderBuffer is not explicit aligned
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
The program flow hit an assertion in FlashDriver_WriteToFlash() (fbl_flio.c). This assertion asserts the co
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
Align variable gRemainderBuffer from fbl_mem.c to a 32-bit boundary.

Resolution:
--------------------------------------
      - **firstAffectedVersion**: 1.00.00
      - **versionsFixed**: 4.02.01
    - **issue**
      - **identifier**: ESCAN00090391
      - **package**: FblTool_Hexeditor_Hexview
      - **subpackage**: Application_Exe
      - **severity**: Low
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: GM: Calibration header cannot be generated in a way, so that all data bytes can be used
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
Wrong calibration headers are generated.

GM SLP5, SLP6     (XML based header generation): 
* The calibrati
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
Leave at minimum the smallest multiple of ALIGN_SEG_SIZE (compare issue description) greater equal 14 empty at start of 
      - **firstAffectedVersion**: 1.05.00
      - **versionsFixed**: 1.11.00
    - **issue**
      - **identifier**: ESCAN00095072
      - **package**: FblKbApi
      - **subpackage**: Implementation
      - **severity**: Low
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: ApplFblSetModulePresence() Cannot write presence pattern to multiple memory devices with different erased values
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
ApplFblSetModulePresence() errantly returns kFblFailed when it has written a valid presence pattern. Downlo
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
ApplFblSetModulePresence() has to be adapted according to the erased code.


Resolution:
-------------------------------
      - **firstAffectedVersion**: 1.00.00
      - **versionsFixed**
    - **issue**
      - **identifier**: ESCAN00078508
      - **package**: FblDrvFlash_Rh850Rv40His
      - **subpackage**: Impl_Base
      - **severity**: Low
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: [depends on derivative] Illegal flash block table configuration cause unintended block erase
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
If the code flash contains gaps where no flash exists and the user configure a flash block in this area, th
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
Well configured flash block table, which corresponds to the real flash block structure.


Resolution:
------------------
      - **firstAffectedVersion**: 0.90.00
      - **versionsFixed**
    - **issue**
      - **identifier**: ESCAN00090094
      - **package**: FblDrvCan_Rh850RscanCrx
      - **subpackage**: Implementation
      - **severity**: Low
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: FblCanWakeup() does not allow to enable Can clock again
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
After call to FblCanSleep and wakup call to FblCanWakeUp, no CAN communicaton is possible any more.

When d
      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------
1. Replace calls to FblCanWakeUp() by calls to ApplFblCanWakeUp() in user callback context.
2. Add code to ApplFblCanWak
      - **firstAffectedVersion**: 1.02.00
      - **versionsFixed**
    - **issue**
      - **identifier**: ESCAN00095107
      - **package**: FblTool_Hexeditor_Hexview
      - **subpackage**: Application_Exe
      - **severity**: Low
      - **issueClass**: Issue in a released product
      - **safetyRelevant**: false
      - **headline**: Compile error of generated C-structure
      - **problemDescription**: What happens (symptoms):
-------------------------------------------------------------------
on C-File export Hexview generates

typedef struct _tFblUpdateBlkInfo
{
   FBL_ADDR_TYPE     blockAddress;

      - **resolutionDescription**: Workaround:
-------------------------------------------------------------------

replace
   V_MEMROM0 V_MEMROM1  vuint8 V_MEMROM2 * V_MEMROM1 V_MEMROM2 blockSource;
by
   V_MEMROM1 vuint8 V_MEMROM2 V_
      - **firstAffectedVersion**: 1.05.00
      - **versionsFixed**
    - **issue**
      - **identifier**: ESCAN00090114
      - **package**: SysService_CryptoCv
      - **subpackage**: Impl_actCLib
      - **severity**: Low
      - **issueClass**: Warning in a released product
      - **safetyRelevant**: false
      - **headline**: Compiler Warning: Assignment in condition
      - **problemDescription**: What happens (symptoms):
---------

---
[Back to top](#top)
