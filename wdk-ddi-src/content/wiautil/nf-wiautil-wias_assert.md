---
UID: NF:wiautil.WIAS_ASSERT
title: WIAS_ASSERT macro
author: windows-driver-content
description: The WIAS_ASSERT macro writes a diagnostic message to the Wiatrace.log file.
old-location: image\wias_assert.htm
old-project: Image
ms.assetid: 74dac8e1-a909-4c22-a650-af8a43421c5c
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IWiaLog_91198444-77d8-4f41-957b-de4c3262988a.xml, image.wias_assert, wiamdef/WIAS_ASSERT, WIAS_ASSERT macro [Imaging Devices], WIAS_ASSERT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wiautil.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wiamdef.h
apiname:
-	WIAS_ASSERT
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# WIAS_ASSERT function
The WIAS_ASSERT macro writes a diagnostic message to the <i>Wiatrace.log</i> file.

## Syntax

````
VOID WIAS_ASSERT(
   HInst      HInst,
   Expression Expression
);
````

## Parameters

`x`

TBD

`y`

TBD


## Return Value

None

## Remarks

The WIAS_ASSERT macro is used to debug WIA drivers. It is used to test that a certain condition is met. If the <i>Expression</i> parameter evaluates to <b>TRUE</b>, this macro does nothing. If <i>Expression</i> evaluates to <b>FALSE</b>, the macro prints an error string to the <i>Wiatrace.log</i> diagnostic log file. This error message will contain the name and path to the calling driver and the line number in the driver source code where the WIAS_ASSERT macro failed.

The WIAS_ASSERT macro is available in Windows Vista and later versions of the operating system. This macro is the recommended way to implement WIA assertions on Windows Vista. WIAS_ASSERT allows error messages to be written to the log file (<i>Wiatrace.log</i>). The <i>Wiatrace.log</i> file is only available in Windows Vista, and later versions of the operating system. The utility used to view the contents of this log file is WiaTrcVw.exe.

To enable asserts in free builds, drivers must define the WIA_DEBUG macro by adding <code>#define WIA_DEBUG</code> to the driver's source code; this must be done before including any of the WIA headers. Asserts are enabled by default in checked and debug builds of the operating system.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** | wiautil.h |

## See Also

<a href="..\wiautil\nf-wiautil-wias_hresult.md">WIAS_HRESULT</a>



<a href="..\wiautil\nf-wiautil-wias_error.md">WIAS_ERROR</a>



<a href="..\wiautil\nf-wiautil-wias_trace.md">WIAS_TRACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20WIAS_ASSERT macro%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>