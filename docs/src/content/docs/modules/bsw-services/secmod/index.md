---
title: Security module (SecMod)
description: HIS security module — verification, SHA-256, RSA, CRC
---

<span class="origin-vector">Vector-provided</span> + <span class="origin-thirdparty">cryptovision actCLibrary</span> · `BSW/SecMod/`

## Purpose

Verifies downloaded data: HIS `SecM` API, verification classes
(`CCC`/`DDD`/vendor), hash (SHA-256) and RSA verification (`ESLib_*`),
CRC helpers, workspaces. `SecM_cfg.h` / `SecMPar.*` come from GENy
(`Demo/*/Appl/GenData`).

## Key files

`Sec.c|h`, `SecM.h`, `SecM_Inc.h`, `Sec_Inc.h`, `Sec_Types.h`,
`Sec_Workspace.h`, `Sec_Crc.h`, `Sec_Verification.c|h`,
`Sec_VerificationLib.c|h`, `Sec_WorkspaceLib.c`,
`ESLib*.c|h` (SHA-256, RSA V15 verify, RNG, ASN.1, version),
`act*.c|h` (big-number / RSA / SHA-2 core, cryptovision),
`_SecMPar.h`, `_SecM_cfg.h` templates.

## Public API (selection)

```c
SecM_StatusType SecM_InitPowerOn(SecM_InitType initParam);
void SecM_Task(void);
SecM_StatusType SecM_InitVerification(SecM_VerifyParamType *);
SecM_StatusType SecM_Verification(SecM_VerifyDataType *, SecM_VerifyResultType *);
SecM_StatusType SecM_VerifyHashSha256(...);
SecM_StatusType SecM_VerifyClassCCC / SecM_VerifyClassDDD / SecM_VerificationClassVendor(...);
SecM_WordType SecM_GetInteger(...);  void SecM_SetInteger(...);
```

## Usage

```c
SecM_InitPowerOn(init);
SecM_InitVerification(&verifyParam);
/* feed segments */
SecM_Verification(&data, &result);
SecM_Task();  /* async completion where configured */
```

Keys: demo-only `Misc/DemoKey_2048/rsakeys_2048.txt` — never production.
See [demo keys note](../../../general/txt-docs/demo-rsa-keys-note/).

## Dependencies

FBL memory/diagnostics call into `SecM`; workspace sizes from `SecM_cfg.h`;
watchdog via `actWatchdog.h`. No NV dependency directly.

[Back to top](#top)
