---
UID: NF:wiautil.WIAS_LTRACE
title: WIAS_LTRACE macro
author: windows-driver-content
description: The WIAS_LTRACE macro is obsolete for Windows Vista and later. It is recommended that the WIAS_TRACE macro be used instead.The WIAS_LTRACE macro writes a diagnostic WIA_TRACE message to the log file.
old-location: image\wias_ltrace.htm
old-project: Image
ms.assetid: 513fd718-3d35-4a7b-be28-b002a8108e86
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IWiaLog_bb7ae826-5b43-47c1-bf94-bd491d8b91a7.xml, WIAS_LTRACE, wiamdef/WIAS_LTRACE, WIAS_LTRACE macro [Imaging Devices], image.wias_ltrace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me, Windows XP, and later versions of the operating system. Obsolete for Windows Vista and later. Use WIAS_TRACE instead.
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
-	WIAS_LTRACE
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# WIAS_LTRACE function
The WIAS_LTRACE macro is obsolete for Windows Vista and later. It is recommended that the <a href="..\wiautil\nf-wiautil-wias_trace.md">WIAS_TRACE</a> macro be used instead.

The WIAS_LTRACE macro writes a diagnostic WIA_TRACE message to the log file.

## Syntax

````
WIAS_LTRACE( WIAS_LTRACE(
         IWiaLog   *pIWiaLog,
         INT       ResourceID,
         INT       DetailLevel,
   const CHAR      *format_string
);
````

## Parameters

`x`

TBD

`y`

TBD

`z`

TBD

`params`

TBD


## Return Value

None

## Remarks

The following is an example of how the macro can be used:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WIAS_LTRACE(g_pIWiaLog, WIALOG_NO_RESOURCE_ID, WIALOG_LEVEL2,
  ("MyClass::MyMethod, This is my text and my lValue = %d", lValue));</pre>
</td>
</tr>
</table></span></div>
The WIAS_LTRACE macro is not recommended for Windows Vista, because it does not record its output to the <i>Wiatrace.log </i>diagnostic Log file. It is recommended that the <a href="..\wiautil\nf-wiautil-wias_trace.md">WIAS_TRACE</a> macro be used instead.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me, Windows XP, and later versions of the operating system. Obsolete for Windows Vista and later. Use WIAS_TRACE instead.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** | wiautil.h |

## See Also

<a href="..\wiautil\nf-wiautil-wias_lhresult.md">WIAS_LHRESULT</a>



<a href="..\wiautil\nf-wiautil-wias_lerror.md">WIAS_LERROR</a>



<a href="..\wiautil\nf-wiautil-wias_lwarning.md">WIAS_LWARNING</a>



<a href="..\wiautil\nf-wiautil-wias_trace.md">WIAS_TRACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20WIAS_LTRACE macro%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>