---
UID: NF:miniport.WRITE_REGISTER_ULONG64
title: WRITE_REGISTER_ULONG64 function
author: windows-driver-content
description: The WRITE_REGISTER_ULONG64 function writes a ULONG64 value to the specified address.
old-location: wdf\write_register_ulong64.htm
old-project: wdf
ms.assetid: 50C407F2-657F-451F-8A6B-BEEB533D89DE
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.write_register_ulong64, WRITE_REGISTER_ULONG64 function, umdf.write_register_ulong64, wudfddi_hwaccess/WRITE_REGISTER_ULONG64, WRITE_REGISTER_ULONG64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: miniport.h
req.include-header: Wdm.h, Miniport.h, Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: 64-bit Windows
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfddi_hwaccess.h
apiname:
-	WRITE_REGISTER_ULONG64
product: Windows
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---


# WRITE_REGISTER_ULONG64 function
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WRITE_REGISTER_ULONG64</b> function writes a ULONG64 value to the specified address.

## Syntax

````
void WRITE_REGISTER_ULONG64(
  _In_ IWDFDevice3 *pDevice,
  _In_ PULONG64    Register,
  _In_ ULONG       Value
);
````

## Parameters

`Register`

A pointer to the register, which must be a mapped range in memory space.

`Value`

Specifies a ULONG64 value to write to the register.


## Return Value

This function does not return a value.

## Remarks

For more information, see <a href="https://msdn.microsoft.com/A0640E60-B0DF-4CAD-B292-CC1875EF7F7D">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | 64-bit Windows  |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | miniport.h (include Wdm.h, Miniport.h, Wudfwdm.h) |
| **Library** | NtosKrnl.exe |